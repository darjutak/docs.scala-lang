---
layout: sips
title: SIP Meeting Minutes - 22nd October 2018

partof: minutes
---

# Minutes

The following agenda was distributed to attendees:

|Topic|Reviewers| Accepted/Rejected |
| --- | --- | --- |
| Summary of the Contributors thread [“Proposal to add Trait Parameters to the Language”](https://contributors.scala-lang.org/t/proposal-to-add-trait-parameters-to-the-language/2356) | Iulian Dragos | Pending
| Summary of the Contributors thread [“Proposal to add Intersection Types to the Language”](https://contributors.scala-lang.org/t/proposal-to-add-intersection-types-to-the-language/2351) | Eugene Burmako | Pending |
| Summary of the Contributors thread [“Proposal to add Union Types to the Language”](https://contributors.scala-lang.org/t/proposal-to-add-union-types-to-the-language/2352) | Eugene Burmako | Pending |
| Summary of the Contributors thread [“Proposal to add Dependent Function Types to the Language”](https://contributors.scala-lang.org/t/proposal-to-add-intersection-types-to-the-language/2351) | Miles Sabin | Pending |
| Summary of the Contributors thread [“Proposal to add Implicit Function Types to the Language”](https://contributors.scala-lang.org/t/proposal-to-add-intersection-types-to-the-language/2351) | Miles Sabin | Pending |

Jorge Vicente Cantero was the Process Lead and Darja Jovanovic was the secretary.


## Date and Location
The meeting took place on the 22nd October 2018 at 5 PM CEST via Google Hangouts at EPFL in Lausanne, Switzerland as well as other locations.

[Watch on Scala Center YouTube channel](https://www.youtube.com/watch?v=gctI7SRKp20)


Minutes were taken by Darja Jovanovic

## Attendees

* Martin Odersky ([@odersky](https://github.com/odersky)), EPFL
* Jorge Vicente Cantero ([@jvican](https://github.com/jvican)), Process Lead
* Seth Tisue ([@SethTisue](https://github.com/SethTisue)), Lightbend
* Eugene Burmako ([@xeno-by](https://github.com/xeno-by)), Twitter
* Sébastien Doeraene ([@sjrd](https://github.com/sjrd)), Scala Center
* Miles Sabin ([@milessabin](https://github.com/milessabin)), Independent
* Heather Miller ([@heathermiller](https://github.com/heathermiller)), CMU
* Darja Jovanovic ([@darjutak](https://github.com/darjutak)), Scala Center

## Not present
* Iulian Dragos ([@dragos](https://github.com/dragos)), Triplequote
* Josh Suereth ([@jsuereth](https://github.com/jsuereth)), Independent
* Adriaan Moors ([@adriaanm](https://github.com/adriaanm)), Lightbend
## Proceedings
### Opening Remarks

Summary for union & intersection types

Proposals:
https://contributors.scala-lang.org/t/proposal-to-add-union-types-to-the-language/2352
https://contributors.scala-lang.org/t/proposal-to-add-intersection-types-to-the-language/2351

Motivation:

Both the SIP and the documentation page simply state that  A with B is not commutative without explaining why that is and what that entails. As the discussion on the forum shows, this is non-obvious, so I believe this needs to be added to the SIP.
It would be good to make it clear why noncommutativity of compound types is problematic in practice. The discussion on the forum mentions a contrived example, but it would be good to see real-world code affected by this.
Exploding lubs are mentioned as a problem solved by union types, but like noncommutativity of compound types, this problem doesn't come with examples. I think this needs to be elaborated.
Same comment for Scala.js and null safety.
Moreover, what are best practices of using union & intersection types? Academically, their benefits look solid, but in what practical situations using these features will result in more expressive or more robust code? Documentation pages have some synthetic code snippets, but it would be good to understand, at least provisionally, the effect that these features will have on the language.

Specification:

- How does the Scala grammar change to accommodate union and intersection types (SLS 13)? 
- In particular, is there any way to define types called | and &, and use them in infix type applications?
- How do union and intersection types affect membership (SLS 3.4)?
- How do union and intersection types affect the conformance relation between types (SLS 3.5.2)?
- How are union and intersect types erased (SLS 3.7)? Also see https://github.com/lampepfl/dotty/issues/5139.
- "The present design is kept very conservative in what concerns type inference. In essence, union types must be explicitly declared in most situations". What does "most situations" entail?

Compatibility:

Do we need a separate SIP for deprecating and eventually removing compound types, or we vote for everything at once?
Will Scala 2 programs be able to use Scala 3 definitions that make use of union and intersection types?

Iulian

"Trait Parameters" didn't generated a whole lot of debate. There were two points raised:

- what's left to differentiate between traits and classes. Adriaan answered saying linearization order is "fixed" when you define a class, while traits leave that open
- the interaction with implicit parameter lists, where a trait that's inherited indirectly will need to be repeated to fill-in parameters, even though they are implicit and syntactically they would still be missing.

Specifically, Oron Port raised a proposal where the compiler would automatically insert necessary trait super classes with implicit parameters list at the point where a class is inheriting them indirectly. Martin suggested to keep things less magical for now and perhaps add it in a later version.

Miles

## Implicit Function Types

### References

+ [Scala Contributors thread](https://contributors.scala-lang.org/t/proposal-to-add-implicit-function-types-to-the-language/2353).
+ [Dotty documentation page](https://dotty.epfl.ch/docs/reference/implicit-function-types.html)
+ [Pre-SIP: ThisFunction](https://contributors.scala-lang.org/t/pre-sip-thisfunction-scope-injection-similar-to-kotlin-receiver-function/2234)
+ [DelayedInit/onCreate thread](https://contributors.scala-lang.org/t/delayedinit-or-oncreate-any-solution/1748).
+ [Scope injection thread](https://contributors.scala-lang.org/t/implicit-function-types/219/39).

### Comments

There was a single comment in the thread from Alexey Matveev, which pointed at three threads
elsewhere,

+ Overlaps between implicit function types and Kotlin-style "receiver functions" for builder
  DSL patterns.
+ Relationship with potential replacements for `DelayedInit`.
+ An application of implicit function types to scope injection in DSLs.

The last of these describes an idiom which should be compatible with Dotty function types as
they are now, and looks to be related to the requests in the previous two threads.

### Editorial comments

We should try and collate idioms which this feature enables and evaluate their usefulness in
areas where there are related open issues.

We need to ensure consistency with dependent and polymorphic function types.

## Dependent Function Types

### References

+ [Scala Contributors thread](https://contributors.scala-lang.org/t/proposal-to-add-dependent-function-types-to-the-language/2354).
+ [Dotty documentation page](https://dotty.epfl.ch/docs/reference/dependent-function-types.html).

### Comments

There was a short thread in response to Martin's aside "once we have dependent function types,
of course one would like to have polymorphic function types as well." on mirroring method
overloading in function types somehow.

Whilst that's largely orthogonal to implicit function types per se, the poster was asking for
something similar to shapeless's polymorphic function values which we should ensure can be
encoded smoothly using a combination of polymorphic, implicit and dependent function types in
Scala 3.

Lack of further comments suggests either that the feature is uncontroversial, or that it's not
sufficiently well understood to attract significant comment. My sense is that there is enough
community interest in the feature and that if there were major issues some comment would have
been made.

### Editorial comments

We need to ensure consistency with implicit and polymorphic function types, and with related
constructs, eg. constructors.
