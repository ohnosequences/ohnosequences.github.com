---
layout: post
title: "typed property graphs in Java II - implementations"
date: 2014-05-19 11:18
comments: true
categories: 
---

In the previous post _TODO link_ I went through how you can use the typed graphs API for defining graph schemas: nodes and their types, relationships with specific source/target and arity, etc.

Here I want to show how you could then go and implement that schema using a particular technology: Titan in this case. All the genericity _TODO explain advantages_

The general ideas with implementations is 
  
- particular technologies (or stacks such as Blueprints) are wrapped into interfaces refining the corresponding types: `Node` -> `TitanNode`, `Relationship` -> `TitanRelationship`
- you only bound all the F-bounded parameters at the last step, when you make `final class`es implementing each entity, using the abstract refinements for each technology/stack

## Titan typed nodes

`TitanNode` and the accompanying `TitanNode.Type` extend `Node`, `Node.Type` and follow the same pattern:

``` java
public abstract class TitanNode <
  N extends TitanNode<N,NT>,
  NT extends TitanNode.Type<N,NT>
>
  // it is a TitanVertex too!
  implements Node<N,NT>, TitanVertex
{
  
  protected TitanVertex rawVertex;
  
  // rest of body omitted
}
```

So `N`,`NT` again refer to the implementing class, and we know that `N` is a `TitanNode`. It is also a `TitanVertex`, with all Titan-specific methods forwarded to the wrapped `rawVertex`.

## node and relationship types

Titan has a native notion of relationship types (labels), but there's no such thing (yet; there will be in `0.5`) for nodes. We're using properties instead, so that having that property means that the node has that type. Note that it is just the _presence_ of such property what adscribes the type to a given node; you could use the _value_ as an id for example. Looking at the code, for titan node types the interface has

``` java
// inside TitanNode.Type
public TitanKey titanKey();
public N fromTitanVertex(TitanVertex vertex);
```

while for rels

``` java
// inside TitanRelationship.Type
public TitanLabel label();
public R fromTitanEdge(TitanEdge edge);
```

We are also using node and rel types here as factories, so that passing an instance of them gives you a way of generically building a node or rel of the right type; this is essential for having what we could call

## type-safe gremlin-like ops

It is pretty nice that you can get all this generic, schema-aware methods. Basically you have all possible `in`/`out` methods with bounds guaranteeing correct behaviour statically (obviously, as long as your data conforms to the declared schema). For example

``` java
// inside TitanNode
public <
    // a rel with source this node: N,NT 
    R extends TitanRelationship<N,NT, R,RT, T,TT>,
    // the relationship type is to one
    RT extends TitanRelationship.Type<N,NT,R,RT,T,TT> & Relationship.Type.ToOne<N,NT, R,RT, T,TT>,
    // the target node and its type
    T extends TitanNode<T,TT>, 
    TT extends TitanNode.Type<T,TT>
  >
  // you pass the rel type as a param and get rels of that type out 
  R outToOne(RT relType) {

    Iterable<TitanEdge> tEdges = this.getTitanEdges(
      com.tinkerpop.blueprints.Direction.OUT,
      relType.label()
    );

    return relType.from(tEdges.iterator().next());
  }
```

So you get

1. a completely generic uniform implementation
2. to which you can only pass to `outToOne` a relationship with
    1. that node as source
    2. a "whatever-to-one" arity


## where the types should go?

I've found that a good approach consists on making an abstract class `MyTitanGraph` where you define all your node and relationship types, together with the code required to initialize all the Titan keys, labels, etc; _TODO link_ `TitanTypedGraph` contains some helper methods for this. Then a concrete class can extend that without worrying about how initialize all those types etc. Then you can access all those types in your methods from an instance as fields: `graph.term.id`, `graph.partOf`, ...

``` java
List<TitanTerm> uh = oh.outToManyNodes(graph.partOf);
String oh_name = oh.get(graph.term.id);
// just the rels
List<TitanPartOf> rels = oh.outToMany(graph.partOf);
```

the good thing is that all of this can be kept abstract with respect to the particular graph on which you are running these traversals.

_TODO_ a `TitanTypedGraph` example with all the types declared there.