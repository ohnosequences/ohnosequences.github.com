---
layout: post
title: "typed property graphs in Java"
date: 2014-05-18 20:53
comments: false
categories: Java graphs libraries
---

I've been working the past month or so in a Java API for property graphs that could let you express as much as possible about your graph model in the type system. Everything is very much in the spirit of Blueprints basic interfaces, but with more types: 

- every element has (and cannot be defined without) a companion type
- you can only retrieve the properties that an element has statically
- relationships have a fixed, statically known source and type
- in/out style methods can be both generic and only callable on relationships with the right types; their return type can depend on the (statically-known) arity of the relationship
- all the types can be further refined by implementations
- ...

At some point it felt a bit of a dancing bear effort _TODO explain_ but in the end (and mostly thanks to Java 8 default methods) it is surpringly usable and expressive; so much that we are adopting it as a base for [Bio4j](http://bio4j.com). If you are working with typed graph data in Java, I think you should keep reading. OK enough about generalities, let's do a walk-through!

### the Element base class

As in Blueprints, there's a base `Element` class, which acts as a container for properties; here they are also typed. Let's look first at the type part

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

The key here is how `Element` and `Element.Type` refer to each other in their definitions; this way you cannot define an element without defining its type (of course you can somewhat play around this restriction through a clever use of inheritance). 

This together with F-bounded polyomorphism makes possible for `N` and `NT` to represent implementing types of `Element` and `Element.Type` respectively. This technique lets you work with implementing classes generically at the level of the abstract type.

Let's see an stupid implementation, just for the sake of example:

``` java
public final class Hey implements Element<Hey, Hey.Type> {

  @Override public Hey.Type type() { 

    return Type.hey;
  } 

  public static enum Type implements Element.Type<Hey, Hey.Type> {

    hey;

    @Override public Type value() {  return hey;  }
  }
}
```

#### generic, safe properties

The property signature can say a lot:

``` java
public abstract class Property <
    // the element which has this property
    N extends Element<N,NT>, NT extends Element.Type<N,NT>,
    // the property
    P extends Property<N,NT,P,V>,
    // the value type of this property
    V
  > 
  {
    // body elided
  }
```

`P` refers again to the implementing class, and `V` is the value type for this property. The pair `N,NT` here acts as a witness for `N,NT` nodes having this property; this way inside `Element` we can define a `get` method which can only be called on properties defined for that `Element`

``` java
public <P extends Property<E,ET,P,V>, V> V get(P p);
```



``` java
// same as before
public final class Hey implements Element<Hey, Hey.Type> {

  public static enum id extends Property<Hey,Hey.Type,id,String> {

    id(Type.hey, "id", String.class);
  }

  // just for convenience
  public static id id = id.id
}
```

that's all. Now given a `Hey` instance you can get its id through

``` java
// you can also do a static import of Hey
String hey_id = hey.get(Hey.id);
```

Let's look at the signature for the `get` method inside `Element`

``` java
public <P extends Property<E,ET,P,V>, V> V get(P p);
```

Recall that `E` and `ET` are references to "this" element and its type. What this implies just based in the signature is

- _you can only call get on properties that are defined for **that** element_

Another important point is that `id` could be defined anywhere; for example, for concrete implementations it is normally a good idea to group properties somewhere. 

You can also of course create abstract properties; imagine that you want to have an id for all of your nodes (but only nodes, not relationships), of type `String`; just do

``` java
public abstract class Id <
  N extends Node<N,NT>, NT extends Node.Type<N,NT>,
  I extends Id<N,NT,I>
>
  extends Property<N,NT,I,String>
{}
```

### Relationships

Both nodes and relationships are elements, so that they have a type and can have properties. Nodes are essentially About relationships, the key features are

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

The arity is defined at the relationship type, and I'm following the same terminology as in [Titan type definitions](https://github.com/thinkaurelius/titan/wiki/Type-Definition-Overview).

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

## full example

_TODO_ link to the typed graphs repo