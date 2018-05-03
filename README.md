# molino

#### Theory
Everything can be described completely via subject, predicate, object relationships.  Nothing can be described without relationship to something else so everything is a subject, predicate &/or object without exception. 

`molino` attempts to define elements and rules to digitally implement the above statement.

#### Elements
* __[nub]__ : Any non-digital thing without limit whether physical or not

	This may be a specific a tangible thing or non tangible things such as a concept, an idea, a theory, or any other imaginable notion. 

	A [nub] is identified here in writing (only) with '[ ]' such as [my dog Fido] or [that idea I had at 2:00 this morning].  This convention has nothing to do with [molino] rules, theory or implementation and is only intended to assist in how [nub] are discussed in a short-hand manner. 

* __[nbl]__ : Any digital value

	Any digital value such as the string 'sister', the number 532, the string 'War and Peace is a long novel.' or any other computer storable value. 

 * __[nid]__ : A digital value that is universally unique to represent one [nub], [nbl] or [spolk]

* __[spolk]__ : A subject, predicate, object relationship physically represented by 3 [nid]; one for the subject, one for the predicate, one for the object. 

	A [spolk] is identified here in writing (only) with subject, predicate & object seperated by '/'; eg [my dog fido]/[likes]/[hamburger] or [brown]/[has english language of]/'brown' for a shortcut representation to a [nbl]. 

#### Rules 
* Everything in [molino] is represented by a [nub],[nbl],[nid] or [spolk]
* A [nub] is never a digital value
* A [nbl] is always a digital value
* A [spolk] is always a subject, predicate and object; each represented by, and only by, a [nid]
* Each [nub],[nbl] and [spolk] is represented by a [nid] which, by definition, is universally unique across all [molino]
* A [nid] permanently and forever represents the [nub], [nbl] or [spolk] for which it was created 
* A [spolk] predicate is never a [nid] representing a [nbl]

#### Example
Assume `a53` is the [nid] assigned to [nub] of [dog fido] (a [nub] so not any digital representation or description of Fido but the actual dog) 

Assume `q3x` is the [nid] assigned to the [nub] of [has name of] (a [nub] that is of course a concept and likely a predicate)

Assume `lB0` is the [nid] assigned to the [nbl] of 'Fido' (a [nbl] so the actual digital value of 'Fido')

We could then create a [spolk] in a [molino] database with the subject, predicate & object of `[dog fido] / [has name] / 'Fido'`  with their resepctive [nid] of `a53 / q3x / lB0`.

And continue to create more and more [spolk] about [dog fido], for example, such as who adopted him, where born, when born, color, vaccinations, on and on.  But [dog fido] will __always__ be represented universally in [molino] by the [nid] `a53`. 


## An In-progress Implementation Standard

#### Guidance
* [nid] values should be absent of any meaning about what they represent
* A [nbl] can be changed
* A [spolk] can be changed
* A [nub] can be further and indefinitely defined (as more [spolk] are created)
* Only one [nid] should exist universally and permanently to represent a given [nub] 
* Use [molino] for [molino] implementations 

#### Objectives  
* Practially unlimited scaleability 
* Universally unique [nid] creation
* Universally accessible [molino elements]
* Privately implementable [molino farm]s but still with universally unique [nid] (and can be connected globally later either partially or wholly)
* Distributed access control by distributed [molino owner]s
* Platform, tool & language agnostic : [molino farm] should not be segregated from each other based on their implementation of platform, tool or language
* Permanence: [molino elements] should have a contract as to their permanence including the [element life] and [element stability] (if [nbl] value or [spolk] subject/predicat/object can be changed)
* Any [agent] should be able to make a single [api] call to refer to all [molino elements] to which they have access
* View and edit history of [molino element]

#### No (or likely not)
* Authentication

#### Important to remember
* By definition, a [nid] is always unique across the entire [molino] universe.  If it isn't universally unique, it isn't a [nid]. 

#### Definitions: 
* [molino farm] : A set of [nub], [nbl] and [spolk] represented by one (?) gateway process.  
* [molino elements] : [nub],[nbl],[nid] and [spolk]
* [nbl nid] : a [nid] that represents a [nbl]
* [nub nid] : a [nid] that represents a [nub]
* [spolk nid] : a [nid] that represents a [spolk]
* [numeric nbl] : a [nbl] that is a number
* [numeric nbl nid] : [nbl nid] that represents (and equals) its [numberic nbl]
* [spolk kvp] : A key value pair with an [nid] as a key associated to a [spolk].  
* [nbl kvp] : A key value pair with a [nid] as a key associated to a [nbl] 
* [local id] : A value which is unique across all [molino elements] within a given [molino farm].  It is typically prepended with a [farm nid] to make a [nid] (universally unique). 
* [farm nid] : [nid] which represents a specific [molino farm]

#### Rules (working...)
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

* Only [farm nid] don't start with the [farm nid] on which they were created; ie, every [nid] that is not a [farm nid] begins with the [nid] of the [molino farm] on which it was created concatenated with a colon. 

* A [nid] has no meaning.  No information about a [nid] can be assumed or determined about the [nid] or what the [nid] represents by the value of the [nid]. [nid] may be generated sequentially, randomly or other methods which ensure they are unique when generated. At most, the [molino farm] on which the [nid] was generated may be determined but it does not indicate its current [molino farm].

* [numeric nbl nid] always have a first character that is numeric character 0-9 (UTF-8 hex 30-39).  All other [nid] never have first character that is numeric. 

* A [numeric nbl] is any number and each has the equivalant [numeric nid]; eg [numeric nbl] is 42 and the [numeric nid] is also 42.  So, [spolk] can contain a direct representation to a [numeric nbl]  eg a4B:q9xr:43 - 43 is the [numeric nbl] and [numeric nid]. 


#### SECURITY (working...)
* Every [nbl] and [spolk] have at least one [molino owner]. (A [nub] cannot have [molino ownership] because it does not exist digitally)
* A [molino owner] controls [read access], [write access] and [molino ownership] for those [nbl] and [spolk] for which they have [molino ownership]
* The [molino farm] that created the [molino element] is the [molino owner] if a [molino owner] is not explicitly assigned 

#### Common [spolk] on [molino element] creation: 
Common Additional [spolk] when new [nub],[nbl] or [spolk] are created: 
* [created by] 
* [created on date] 
* [owned by] 
* [has primary english description]

