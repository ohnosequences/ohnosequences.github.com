---
layout: post
title: "typed property graphs in Java"
date: 2014-05-18 20:53
author: Eduardo Pareja-Tobes
comments: false
categories: [Java, graphs, libraries]
---

[Property graphs](https://github.com/tinkerpop/blueprints/wiki/Property-Graph-Model) form a flexible simple model which can encompass the data and query capabilities of most of the existing graph database technologies. The [Blueprints](https://github.com/tinkerpop/blueprints) Java API for them though falls a bit short when you are working with strongly typed data models, such as what we have in [Bio4j](http://bio4j.com). 

So that's why one month ago I started working on a Java API for property graphs that could let you express as much as possible about your graph model in the type system. The result (still highly experimental) is very much in the spirit of Blueprints basic interfaces, but with more types: 

- every element has (and cannot be defined without) a companion type
- you can only retrieve the properties that an element has statically
- relationships have a fixed, statically known source and type
- in/out style methods can be both generic and as arguments you can only pass relationships with the right types; their return type can depend on the (statically-known) arity of the relationship
- all the types can be further refined by implementations

At some point it felt a bit of a dancing bear effort (as the old saying goes: the amazing thing is that the bear can dance _at all_) but in the end, and mostly thanks to Java 8 [default methods](http://docs.oracle.com/javase/tutorial/java/IandI/defaultmethods.html) it is surpringly usable and expressive; so much that we are adopting it as a base for [Bio4j](http://bio4j.com). If you are working with typed graph data in Java, I think you should keep reading. OK enough about generalities, let's do a walk-through!

### the Element base class

As in Blueprints, there's a base `Element` class, which acts as a container for properties; here they are also typed. Let's look first at the signatures

#### Elements and their types

``` java
// just part of it
public interface Element <
  E extends Element<E,ET>, 
  ET extends Element.Type<E,ET>
> 
{
  
  // the type of this element
  public ET type();

  public static interface Type <
    E extends Element<E,ET>,
    ET extends Element.Type<E,ET>
  >
  {
    // a value representing this type
    public ET value();
  }  
}
```

The key here is how `Element` and `Element.Type` refer to each other in their definitions; this way you cannot define an element without defining its type. I was playing with this ideas and this [post](http://axisofeval.blogspot.com/2010/05/typeful-dynamic-programming-or-javac.html) from Manuel Simoni where a similar application of this pattern is mentioned confirmed me that this was possible. 

Being able to link at the type level entities and their types, together with the together with  makes possible for `N` and `NT` to represent implementing types of `Element` and `Element.Type` respectively. This technique lets you work with implementing classes generically at the level of the abstract type. We can do all this thanks to Java supporting a variant of [F-bounded polymorphism](http://www.cs.utexas.edu/~wcook/papers/FBound89/CookFBound89.pdf).

#### generic, safe properties

The property signature can say a lot:

``` java
public abstract class Property <
    // the element which has this property
    N extends Element<E,ET>, NT extends Element.Type<E,ET>,
    // the property
    P extends Property<E,ET,P,V>,
    // the value type of this property
    V
  > 
  {
    // body elided
  }
```

`P` refers again to the implementing class, and `V` is the value type for this property. The pair `E,ET` here acts as a witness for `E,ET` elements having this property; this way inside `Element` we can define a `get` method which can only be called on properties defined for that `Element`, as `E,ET` correspond to "this" element:

``` java
public <P extends Property<E,ET,P,V>, V> V get(P p);
```

As I just said, `E` and `ET` are references to "this" element and its type. What this implies just based in the signature is

- _you can only call get on properties that are defined for **that** element_

Another important point is that properties could be defined anywhere, and separately from the element definition. You can also of course create abstract properties; imagine that you want to have an id for all of your nodes (but only nodes, not relationships), of type `String`; just do

``` java
public abstract class Id <
  N extends Node<N,NT>, NT extends Node.Type<N,NT>,
  I extends Id<N,NT,I>
>
  extends Property<N,NT,I,String>
{}
```

### Relationships

Both nodes and relationships are elements, so that they have a type and can have properties. Nodes are essentially just a marker interface over elements. About relationships, the key features are

- typed source and target
- relationship types specify the arity

The interface is essentially

``` java
public interface Relationship <
  S extends Node<S,ST>, ST extends Node.Type<S,ST>,
  R extends Relationship<S,ST,R,RT,T,TT>, RT extends Relationship.Type<S,ST,R,RT,T,TT>,
  T extends Node<T,TT>, TT extends Node.Type<T,TT>
> 
  extends Element<R,RT>
{

  public S source();
  public T target();
}
```

As before, elements and their types always go together; here

- `S,ST` represents the source node and its type,
- `R,RT` this rel and its type, and
- `T,TT` the target node and its type

note how inside the body we can refer to implementing types in the definition of the `source` and `target` methods.

The arity is defined at the relationship type, and I'm following the same terminology as in [Titan type definitions](https://github.com/thinkaurelius/titan/wiki/Type-Definition-Overview#cardinality-constraints).

``` java
public interface Type <
  S extends Node<S,ST>, ST extends Node.Type<S,ST>,
  R extends Relationship<S,ST,R,RT,T,TT>, RT extends Relationship.Type<S,ST,R,RT,T,TT>,
  T extends Node<T,TT>,TT extends Node.Type<T,TT>
> 
  extends Element.Type<R,RT> 
{

  public default Arity arity() { return Arity.manyToMany; }

  public static enum Arity {

    oneToOne, 
    oneToMany, 
    manyToOne,
    manyToMany;
  }
}
```

A good mnemonic is that this is determined by the return type of the in and out methods, being `inToOut`: 

- `r` is `oneToMany` means `in(r)` returns one rel, `out(r)` returns a list
- `manyToOne` means `in(r)` returns a list, `out(r)` one rel

And this is basically all for now; below there's a self-contained example for a model declaration with just users, twits and a "user twitted twit" relationship, in all its  type parameter glory:

``` java
import com.ohnosequences.typedGraphs.*;

/*
  A User node. N,NT need to be left abstract until the point where you bound them in a final class; same for all the equivalent entity,type pairs in what follows.
*/
public interface User <
  N extends User<N,NT>, NT extends User.Type<N,NT>
>
extends
  Node<N,NT>
{
  public interface Type <
    N extends User<N,NT>, NT extends User.Type<N,NT>
  >
  extends
    Node.Type<N,NT>
  {
    /*
      An id property. It is defined inside the node type just for convenience, so that implementing classes can refer to it as User.Type.id. Here with N,NT we're bounding this property to be of User nodes, and the value type is set to String using default methods
    */
    public interface id <
      N extends User<N,NT>, NT extends User.Type<N,NT>,
      P extends id<N,NT,P,String>>
    >
    extends
      Property<N,NT,P,String> 
    {

      @Override public default valueClass() { return String.class; }
    }
  }
}

/*
  A node for twits. The pattern is exactly the same as that for Users; we're just adding a permalink property.
*/
public interface Twit <
  N extends Twit<N,NT>, NT extends Twit.Type<N,NT>
>
extends
  Node<N,NT>
{
  public interface Type <
    N extends Twit<N,NT>, NT extends Twit.Type<N,NT>
  >
  extends
    Node.Type<N,NT>
  {
    public interface permalink <
      N extends Twit<N,NT>, NT extends Twit.Type<N,NT>,
      P extends permalink<N,NT,P,String>>
    >
    extends
      Property<N,NT,P,String> 
    {

      @Override public default valueClass() { return String.class; }
    }
  }
}

/*
  This relationship connects a user with one of its tweets; its arity is then many to one. It also has a date property.
*/
public interface Twitted <
  S extends User<S,ST>, ST extends User.Type<S,ST>,
  R extends Twitted<S,ST, R,RT, T,TT>, RT extends Twitted.Type<S,ST, R,RT, T,TT>,
  T extends Twit<T,TT>, TT extends Twit.Type<T,TT>
>
extends
  Relationship<S,ST,R,RT,T,TT>
{
  public interface Type <
    S extends User<S,ST>, ST extends User.Type<S,ST>,
    R extends Twitted<S,ST, R,RT, T,TT>, RT extends Twitted.Type<S,ST, R,RT, T,TT>,
    T extends Twit<T,TT>, TT extends Twit.Type<T,TT>
  >
  extends
    Relationship.Type<S,ST,R,RT,T,TT>
  {

    public interface date <
      S extends User<S,ST>, ST extends User.Type<S,ST>,
      R extends Twitted<S,ST, R,RT, T,TT>, RT extends Twitted.Type<S,ST, R,RT, T,TT>,
      T extends Twit<T,TT>, TT extends Twit.Type<T,TT>,
      P extends date<S,ST,R,RT,T,TT,P,java.util.Date>
    >
    extends
      Property<R,RT,P,String> 
    {

      @Override public default valueClass() { return String.class; }
    }
  }

}
```
