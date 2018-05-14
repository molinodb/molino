
## [molino] and RDF

#### Can there be [nub]?  
Ie, Can a thing be identified without the thing having any digital property except an identifier?
* [molino]: Yes.
* RDF: Yes. It is a [blank node](https://www.w3.org/TR/rdf11-concepts/#section-blank-nodes). 
* neo4j: ? 

#### Can it be transactional? eg; "Dan has liked Ann" 3 times
* [molino]: Yes.  Each [spolk] has a [nid]. Each of those [spolk nid] can be referred to in other [spolk] to add additional information such as date. 
* RDF: Yes but confirm methods.  [neo4j says no unless use workarounds](https://neo4j.com/blog/rdf-triple-store-vs-labeled-property-graph-difference/) 
* neo4j: Yes.

#### Can it support complete atomic decomposition? 
* [molino]: Yes
* RDF: Yes.  (But is RDF really intended for document metadata.)

## Implementation

#### [nid] distributed dereferencing? 
Ie, can the referent of the [nid] be found only by the [nid]?
* [molino]: Yes.
* RDF: Yes. [nid] is [iri]
* neo4j: ?  With API build on top 

#### Universally unique [nid] creation
* [molino]: Yes.
* RDF: Yes; but see [Can there be [nub]?](#Can there be [nub]?)

#### Universally accessible [molino elements]
* [molino]: Yes.
* RDF: Yes.
* neo4j: ?  With API build on top 

#### Privately implementable [molino farm]s? 
* [molino]: Yes.
* RDF: Yes.


# Does [molino] work with [RDF](https://www.w3.org/TR/rdf11-concepts/)

Yes, with: 
* [nid] is always an [IRI](https://www.w3.org/TR/rdf11-concepts/#dfn-iri)
* 

The question is 'Does RDF fit within the definition of'
As [molino] has a broader definition 

> [1.1 Graph-based Data Model](https://www.w3.org/TR/rdf11-concepts/#data-model)
>
> The core structure of the abstract syntax is a set of [triples](https://www.w3.org/TR/rdf11-concepts/#dfn-rdf-triple), each consisting of a [subject](https://www.w3.org/TR/rdf11-concepts/#dfn-subject), a [predicate](https://www.w3.org/TR/rdf11-concepts/#dfn-predicate) and an [object](https://www.w3.org/TR/rdf11-concepts/#dfn-object). A set of such triples is called an [RDF graph](https://www.w3.org/TR/rdf11-concepts/#dfn-rdf-graph). An RDF graph can be visualized as a node and directed-arc diagram, in which each triple is represented as a node-arc-node link.
>
> ![alt-text](https://www.w3.org/TR/rdf11-concepts/rdf-graph.svg)
>
>Fig. 1 An RDF graph with two nodes (Subject and Object) and a triple connecting them (Predicate)
>
> There can be three kinds of [nodes](https://www.w3.org/TR/rdf11-concepts/#dfn-node) in an RDF graph: [IRIs](https://www.w3.org/TR/rdf11-concepts/#dfn-iri), [literals](https://www.w3.org/TR/rdf11-concepts/#dfn-literal), and [blank nodes](https://www.w3.org/TR/rdf11-concepts/#dfn-blank-node).


#### RDF [subject](https://www.w3.org/TR/rdf11-concepts/#dfn-subject)
> "the __subject__, which is an IRI or a blank node" 

#### RDF [blank node](https://www.w3.org/TR/rdf11-concepts/#section-blank-nodes)


RFC 3987 (IRI Standard)

>  "The characters in URIs are frequently used for representing words of
   natural languages.  This usage has many advantages: Such URIs are
   easier to memorize, easier to interpret, easier to transcribe, easier
   to create, and easier to guess."


#### FOAF
>
>FOAF describes the world using simple ideas inspired by the Web. In FOAF descriptions, there are only various kinds of things and links, which we call properties. The types of the things we talk about in FOAF are called classes. FOAF is therefore defined as a dictionary of terms, each of which is either a class or a property. Other projects alongside FOAF provide other sets of classes and properties, many of which are linked with those defined in FOAF.
>
> FOAF collects a variety of terms; some describe people, some groups, some documents. Different kinds of application can use or ignore different parts of FOAF. The overview here shows one way of viewing FOAF terms: we ignore archaic and historical parts, and divide the rest into terms that only make sense on the Web, and those that have universal applicability when linking people and information.
> Main FOAF terms, grouped in broad categories.
> * Core - These classes and properties form the core of FOAF. They describe characteristics of people and social groups that are independent of time and technology; as such they can be used to describe basic information about people in present day, historical, cultural heritage and digital library contexts. In addition to various characteristics of people, FOAF defines classes for Project, Organization and Group as other kinds of agent. Related work: Dublin Core, SKOS, DOAP, SIOC, Org vocabulary, Bio vocabulary.
> * Social Web - in addition to the FOAF core terms, there are a number of terms for use when describing Internet accounts, addressbooks and other Web-based activities. Related work: Portable Contacts, W3C Social Web group.
> * Linked Data utilities - FOAF began as the 'RDFWeb' project, and established a widely adopted model for publishing simple factual data via a networked of linked RDF documents. FOAF remains important to the growing "Linked Data" community, while also maintaining a concern for information that is not readily summarised as simple factual data. FOAF is an attempt to use the Web to integrate factual information with information in human-oriented documents (eg. videos, books, spreadsheets, 3d models), as well as information that is still in people's heads. This history explains why FOAF includes a few 'demonstration' terms that served largely educational purposes (eg. geekcode), alongside a few technical utility terms (eg. focus, LabelProperty) that support wider information-linking efforts. The dictionary-based design of FOAF allows a certain pragmatism: we simply record here a set of terms that are useful to the Web community, while keeping an emphasis on the central idea of FOAF, which is about linking networks of information with networks of people.`