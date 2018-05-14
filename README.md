# molino

#### Theory
Everything can be described completely via subject, predicate, object relationships.  Nothing can be described without relationship to something else so everything is a subject, predicate &/or object without exception. 

`molino` attempts to define elements and rules to digitally implement the above statement.

#### Elements
* __[nub]__ : Any non-digital thing without limit whether physical or not

	This may be a specific a tangible thing or non tangible things such as a concept, an idea, a theory, or any other imaginable notion. 

	A [nub] is identified here in writing with '[ ]' such as [my dog Fido] or [that idea I had at 2:00 this morning].  This convention is for writing and description only. 

* __[nbl]__ : Any digital value

	Any digital value such as the string 'sister', the number 532, the string 'War and Peace is a long novel.' or any other computer storable value. 

 * __[nid]__ : A universally unique value to represent one [nub], [nbl] or [spolk]

* __[spolk]__ : A subject, predicate, object relationship physically represented by 3 [nid]; one for the subject, one for the predicate, one for the object. 

	A [spolk] is identified here in writing with [nub] and [nbl] of the subject, predicate & object represented seperated by '/'; eg [my dog fido]/[likes]/[hamburger] or [brown]/[has english language of]/'brown' for a shortcut representation to a [nbl].  This convention is for writing and description only.  

#### Rules 
* Everything in [molino] is represented by a [nub],[nbl],[nid] or [spolk]
* A [nub] is never a digital value
* A [nbl] is always a digital value
* A [spolk] is always a subject, predicate and object; each represented by, and only by, a [nid]
* Each [nub],[nbl] and [spolk] is represented by a [nid] which, by definition, is universally unique across all [molino]
* A [nid] permanently and forever represents the [nub], [nbl] or [spolk] for which it was created 
* A [spolk] predicate is never a [nid] representing a [nbl]

#### Example
Assume `a53` is the [nid] assigned to [nub] of [dog fido]  (a [nub] so not any digital representation or description of Fido but the actual dog) 

Assume `q3x` is the [nid] assigned to the [nub] of [has name of]  (a [nub] that is of course a concept and likely a predicate)

Assume `lB0` is the [nid] assigned to the [nbl] of 'Fido' (a [nbl] so the actual digital value of 'Fido')

We could then create a [spolk] in a [molino] database with the subject, predicate & object of `a53`, `q3x` and `lB0` respectively which means `[dog fido] / [has name] / 'Fido'`.

And continue to create more and more [spolk] about [dog fido], for example, such as who adopted him, where born, when born, color, vaccinations, on and on.  But [dog fido] will __always__ be represented universally in [molino] by the [nid] `a53`. 

#### [molino] documents
* [Current State](./molino_current_state.md)
* [Molino Implementation](./molino_implementation.md)
* [Molino and RDF](./molino-rdf.md)
* [Molino comments](./molino_commentary.md)
* [Graph & RDB Comments](./graph-rdb-discussion.md)
* [References](./references.md)