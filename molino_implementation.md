
#### Objectives  
* [nid] distributed dereferencing: [spolk nid] and [nbl nid] need a means of distributed dereferencing to their values.
* Backward compatible: An implementation standard that doesn't limit, cut off or block implementations built with this standard as the standard evolves
* Practically unlimited scaleability 
* Universally unique [nid] creation
* Universally accessible [molino elements]
* Easy/quick spin up of new [molino farm] with little barrier to whom
* Privately implementable [molino farm]s - but still with universally unique [nid]; can be connected globally later either partially or wholly
* Distributed access control by distributed [molino owner]s
* Platform, tool & language agnostic : [molino farm] should not be segregated from each other based on their implementation of platform, tool or language
* Performance: [molino farm] or [molino element] should identify their performance (read/write response expectations)
* Permanence: [molino element] should identify their permanence including the [element life risk]  (risk of being unrecoverable) and [element stability]  (if [nbl] value or [spolk] subject/predicat/object can be changed)
* Any [agent] should be able to make a single [api] call to refer to all [molino elements] to which they have access
* View and edit history of [molino element]
* Process rules: Allow [molino element] which can define rules that [molino process] implement
* Trust/

#### Nope (or likely not)
* Authentication

#### Guidance
* [nid] values should be absent of any meaning about what they represent
* A [nbl] can be changed (but can be prevented from being changed)
* A [spolk] can be changed (but can be prevented from being changed)
* A [nub] can be further and indefinitely defined (as more [spolk] are created)
* Only one [nid] should exist universally and permanently to represent a given [nub] 
* Use [molino] for [molino] implementations 

#### Remember
* By definition, a [nid] is always unique across the entire [molino] universe.  If it isn't universally unique, it isn't a [nid]. 
* [nub] do not have [molino owner].  [spolk] do. 

#### Definitions
* [molino farm] : A set of [nub], [nbl] and [spolk] represented by one (?) gateway [molino process].  
* [molino element] : [nub],[nbl],[nid] or [spolk]
* [molino process] : An authorized process which can to receive requests from an agent and processing those requests for a [molino farm]; ie, read, write, combine, implement [molino rules], etc
* [molino process rule] : [molino element] which define how a [molino process] processes based on the related [molino element] involved
* [molino routing] : Directing an agent to the appropriate [molino process] given a [molino element]
* [nbl nid] : a [nid] that represents a [nbl]
* [nub nid] : a [nid] that represents a [nub]
* [spolk nid] : a [nid] that represents a [spolk]
* [numeric nbl] : a [nbl] that is a number
* [numeric nbl nid] : [nbl nid] that represents (and equals) its [numberic nbl]
* [spolk kvp] : A key value pair with an [nid] as a key associated to a [spolk].  
* [nbl kvp] : A key value pair with a [nid] as a key associated to a [nbl] 
* [local id] : A value which is unique across all [molino elements] within a given [molino farm].  It is typically prepended with a [farm nid] to make a [nid] (universally unique). 
* [farm nid] : [nid] which represents a specific [molino farm]
* [element life] : All [molino element] should be considered permanent 

#### Rules 
__Following to be modified so that [nid] can be any IRI which follows [RFC 3987](http://www.ietf.org/rfc/rfc3987.txt)__

* [local id] can contain the following characters :

    | UTF-8 hex | characters   | note                |
    |-----------|--------------|---------------------|
    |   30-39   |  0-9         |                     |
    |   41-5a   |  A-Z         |                     |
    |   61-7a   |  a-z         |                     |

* [nid] can contain the following characters :

    | UTF-8 hex | characters   | note                |
    |-----------|--------------|---------------------|
    |   30-39   |  0-9         |                     |
    |   3a      |  :           | reserved*           |
    |   41-5a   |  A-Z         |                     |
    |   61-7a   |  a-z         |                     |

* A [molino farm] can generate [nid].  Only the [molino farm] generating a [nid] may create a [nid] prepended with its [farm nid].  They create the [nid]  (universally unique) by concatenating their [farm id] with a colon with a [local id] they generated.  For example, for the [nid] a34x:r2Fx -> a34x is the [molino farm] [nid] and r2Fx is the [local id] referencing a [molino element]. Colon character (:) (UTF-8 hex 40) is never used when generating a [local id].

    This is __not__ intended to input any meaning into a [nid] but rather a method to distribute [nid] creation and keep [nid] universally unique.  

* [farm nid]  (and only [farm nid]) are not pre-pended with the [farm nid] on which they were created; ie, every [nid] that is not a [farm nid] begins with the [nid] of the [molino farm] on which it was created concatenated with a colon. 

* A [nid] has no meaning.  No information about a [nid] can be assumed or determined about the [nid] or what the [nid] represents by the value of the [nid]. [nid] may be generated sequentially, randomly or other methods which ensure they are unique when generated. At most, the [molino farm] on which the [nid] was generated may be determined but it does not indicate its current [molino farm].

* [numeric nbl nid] always have a first character that is numeric character 0-9 (UTF-8 hex 30-39).  All other [nid] never have first character that is numeric. 

* A [numeric nbl] is any number and each has the equivalant [numeric nid]; eg [numeric nbl] is 42 and the [numeric nid] is also 42.  So, [spolk] can contain a direct representation to a [numeric nbl]  eg a4B:q9xr:43 - 43 is the [numeric nbl] and [numeric nid]. 


#### Security 
* Every [nbl] and [spolk] have at least one [molino owner]. A [nub] cannot / does not have [molino owner].
* A [molino owner] controls [read access], [write access] and [molino owner] for those [nbl] and [spolk] for which they are [molino owner]
* The [molino farm] that created the [molino element] is the [molino owner] if a [molino owner] is not explicitly assigned 
* __Consideration to prove__ : Controlling access to [spolk] is all that is needed for full and complete data security.  Useable information and knowledge can only be determined with access to subject, predicate, object relationships.  


#### Common [spolk] on [molino element] creation: 
Common Additional [spolk] when new [nub],[nbl] or [spolk] are created: 
* [created by] 
* [created on date] 
* [owned by] 
* [has primary english description]

#### Tests for success
* Can Dad easily publish? 
* Can Dad easily query? 
* Does Dad trust it? 

