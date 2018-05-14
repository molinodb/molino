## Molino commentary - theory & implemenation

#### Only one [nid] should exist universally to represent a given [nub]
This means that for a given [nub], all spolk should refer to that [nub] by one [nid] rather than creating more [nid] representing the same [nub].

For example let's say [nid] 'a349x' represents [dog]. All [spolk] universally should use 'a349x' when referring to [dog] and not create a new [nid] to represent [dog] if it is really equivalent.  

Undoubtedly, multiple [nid] for the same [nub] will occur.  [molino] implementations should expect and provide a means to handle [multiple nid referring to the same nub] but the objective should remain to have one [nid] for one [nub]. 

See [fluid nub]. 

#### A [nub] can be further and indefinitely defined 
Every time a [spolk] is created referencing a [nub], that [nub] becomes further defined.  So [nub] will be further defined sometimes, and maybe usually, indefinitely.  

#### A [spolk] predicate is never a [nid] representing a [nbl]
A [nbl] has no meaning on its own. A [nbl] is just a collection of bits - it only has meaning on its own because we impart human meaning when we read it (if we can read it). A [nbl] is only given meaning by associating it as a subject or object in a [spolk]. So, how can it be a predicate?

For example, let's say my [nbl] is the string 'bought'. So [john] / 'bought' / [typewriter] can make no sense.  It makes sense to "us" as english human language readers but not to [molino].  It's like saying [john] / 'somecollectionofgarbagybits' / [typewriter]. 

Now assuming [bought] is the _[nub]_ that represents the concept about buying, this does makes sense:  [john] / [bought] / [typewriter].  This also makes sense : [bought] / [has western english of]  'bought' as does 'bought' / [is western english for] / [bought].  And we can go on : [bought] / [is past tense for] / [buy], [typwriter] / [has western english of] /  'typewriter' etc. Now, we can digitally combine the [spolk] and [nbl] to  represent that to an english speaking human as 'John bought typewriter'.  Yay!

So, [nid] that represent [nbl] work as subject and object but not as predicate.  

#### A [nid] permanently and forever represents the [nub], [nbl] or [spolk] for which it was created 
This could have been "A [nid] permanently and forever represents the [nub], [nbl] or [spolk] for which it was created _as long as that [nid] exists anywhere to represent that [nub], [nbl] or [spolk]_" but how would "_as long as that [nid] exists anywhere to represent that [nub], [nbl] or [spolk]_" be determined?  

If it's a private [molino farm], for example, and a [nid] is created to represent a [nub] within a [spolk].  Almost immediately, it's recognized its a mistake.  The great danger, almost immediately, is that [nid] is or has been used somewhere that hasn't been considered.  A log or, even more difficult to determine, a person already used the [nid] in code or some other documentation.  Even, if you create a process to delete the [nid] you really then have a [nub] which really is [this nid that i'm about to delete] which of course now you're back to referencing the [nid] that you're about to delete.  

So, it seems to me, ever forward - if a [nid] is a mistake, create a [nub] and [spolk] to document it, maybe even a [molino rule] to keep it away from most requests and move on to your next [nid].  

__[nid] values should be absent of any meaning__ has relevance here as well.  Trying to create [nid] that have meaning, context or taxonomy will invariably lead to greater need, and urges to delete and reassign [nid].

#### [nid] values should be absent of any meaning about what they represent
Trying to create [nid] that is includes any meaning : 
* Inputs [spolk] information into a [nid].  Go ahead, try to create a human meaningful [nid] that doesn't have information that is really subject/predicate/object information
* Makes [nid] brittle 
* Makes [nid] specific to a given language (you were thinking of Swahili [nid], right?)
* Takes too much time: devising a [nid] naming strategy that is human context friendly can be substantially and exponentially time consuming (trust me, I know).  Feel the freedom of simply saying make this [nub] or [nbl] without worrying about what the [nub] or [nbl] is called. 
* [nid] are generally for computers, not people
* Also see __A [nid] permanently and forever represents...__

I am not dogmatic in general in other databases in the old rule "do not input meaning into IDs".  This isn't about that.  The smaller the domain of a given database, I think the more 'ok' it is to build meaning into IDs.  The domain context of smaller databases makes the meaning and taxonomies being built into the IDs less brittle. Conversely, in the intended universal world of [molino], the IDs must be as agnostic as possible. 

We are all tempted to create [nid] that have meaning and are human recognizeable. Resist.  

#### OK, so why use the [farm id] in creating [nid]
Each [nid] of course must be universally unique 

[nid] values are ultimately scarce (considering that less than infinity is scarce).  Allowing [molino farm] to create their own [nid] decentralizes the responsibility for managing that scarcity. 

As an added benefit, (at the risk of violating __[molino] implmentations should use [molino])__, having [farm id] as part of the [nid] will likely simplify [molino routing]  (not that the [farm id] determines the current [molino farm] on which the [molino element] exists).

#### Why use the [nid] rather than the [local id] as the keys in a given [molino farm]
Why not just let its owning [molino process] append the approprite [farm id] to the requesting agent? 

Some considerations:  

1. Because, every [nub],[nbl] and [spolk] requires a [nid], even if a [molino farm] would record just a [local id] as its keys, then the full, permanent [nid] would still need to be recorded for each [molino element]  (note that "full, permanent" is redundant).  Doing that, at least 2 [molino element]  (one with the [local id] and one with the [nid]) rather than just 1 that would be needed if just recorded the [nid].

2. The performance gain by shortening the key to just [local id] is likely negligible. 

3. The pre-pended [farm id] in a [nid] does not indicate what [molino farm] currently 'owns' a [molino element] but rather which [molino farm] generated that [nid]. Immediately thereafter, the [molino element] could move to another [molino farm]. 

#### Why do you put all the [molino] terms in brackets [ ]?
This is a great question with an unsatisfying and arbitrary answer. At times I just want to ditch the brackets in writing but then I realize I've just gotten used to them. 

When I first started jotting down these concepts, I didn't know (or really care) what to call the core elements.  Having a concept but not the name for it fits exactly what a [nub] is: I don't care what letters are used to describe it, it is [this thing] and I can always add a name later.  So, I quickly jotted the terms based on being short ([nub],[nbl],[nid]) and befitting a windmill with SPOlk for Subject,Predicate,Object.  

#### Does [molino] use a schema?
[molino] does not define any schema.  The schema are built by using [molino].

#### Why call it 'molino'?
"Fortune is guiding our affairs better than we ourselves could have wished. Do you see over yonder, friend Sancho, thirty or forty hulking giants? I intend to do battle with them and slay them. With their spoils we shall begin to be rich for this is a righteous war and the removal of so foul a brood from off the face of the earth is a service God will bless."

Just then they came in sight of thirty or forty windmills that rise from that plain. And no sooner did Don Quixote see them that he said to his squire, "Fortune is guiding our affairs better than we ourselves could have wished. Do you see over yonder, friend Sancho, thirty or forty hulking giants? I intend to do battle with them and slay them. With their spoils we shall begin to be rich for this is a righteous war and the removal of so foul a brood from off the face of the earth is a service God will bless."

"What giants?" asked Sancho Panza.

"Those you see over there," replied his master, "with their long arms. Some of them have arms well nigh two leagues in length."

"Take care, sir," cried Sancho. "Those over there are not giants but windmills. Those things that seem to be their arms are sails which, when they are whirled around by the wind, turn the millstone."

— Part 1, Chapter VIII. Of the valourous Don Quixote's success in the dreadful and never before imagined Adventure of the Windmills, with other events worthy of happy record.

