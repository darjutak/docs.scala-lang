---
layout: sips
title: SIP Meeting Minutes - 24th October 2017

partof: minutes
---

# Minutes

The following agenda was distributed to attendees:

|Topic|Reviewers| Accepted/Rejected |
| --- | --- | --- |
| [SIP-34: Right-Associative By-Name Operators](http://docs.scala-lang.org/sips/right-associative-by-name-operators.html) | Adriaan Moors | Pending |
| [SIP-35: Opaque types](http://docs.scala-lang.org/sips/opaque-types.html) | Sébastien Doeraene | Pending |
| [SIP-33: Match infix and prefix types to meet expression rules](http://docs.scala-lang.org/sips/make-types-behave-like-expressions.html)| Josh Suereth | Pending |
|[SIP-28 and SIP-29: Inline meta](http://docs.scala-lang.org/sips/inline-meta.html)|Josh Suereth and Iulian Dragos| Pending |

Jorge Vicente Cantero was the Process Lead and Darja Jovanovic as secretary.

## Date and Location
The meeting took place on the 24th October 2017 via Google Hangouts at EPFL in Lausanne, Switzerland as well as other locations.

[Watch on Scala Center YouTube channel](https://youtu.be/aIc-o1pcRhw)

Minutes were taken by Darja Jovanovic.

## Attendees

* Martin Odersky ([@odersky](https://github.com/odersky)), EPFL
* Jorge Vicente Cantero ([@jvican](https://github.com/jvican)), Process Lead
* Seth Tisue ([@SethTisue](https://github.com/SethTisue)), Lightbend
* Heather Miller ([@heathermiller](https://github.com/heathermiller)), Scala Center
* Sébastien Doeraene ([@sjrd](https://github.com/sjrd)), EPFL
* Eugene Burmako ([@xeno-by](https://github.com/xeno-by)), Twitter
* Iulian Dragos ([@dragos](https://github.com/dragos)), Independent
* Adriaan Moors ([@adriaanm](https://github.com/adriaanm)), Lightbend
* Darja Jovanovic ([@darjutak](https://github.com/darjutak)), Scala Center
* Ólafur Páll Geirsson ([olafurpg](https://github.com/olafurpg)), Scala Center



## Proceedings
### Opening Remarks

**Jorge** opens the meeting and introduces Olaf as a guest presenter for the SIP 28 and 29. Goes on to the first item on the agenda.


### [SIP-34: Right-Associative By-Name Operators](http://docs.scala-lang.org/sips/right-associative-by-name-operators.html)
[YouTube time: 00.31''- 2'03''](https://youtu.be/aIc-o1pcRhw?t=32)

**Jorge** states that this SIP is uncontroversial and that Committee should vote, if there are no further comments. **Sébastien** adds that community didn't have any comments either.
The Committee votes.

**Conclusion**: The SIP is accepted by unanimity.

### [SIP-35: Opaque types](http://docs.scala-lang.org/sips/opaque-types.html)
[YouTube time: 02'03''-03'12''](https://youtu.be/aIc-o1pcRhw?t=122)

**Jorge** gives a brief update about the stage of the eSIP-35, says that both community and the committee members gave a lot of feedback.
They are working on updates, but don't have any to share for this meeting.

**Conclusion**: The SIP-35 will be discussed on the next meeting.

### [SIP-33: Match infix and prefix types to meet expression rules](http://docs.scala-lang.org/sips/make-types-behave-like-expressions.html)
[YouTube time: 03'12''-03'12''](https://youtu.be/aIc-o1pcRhw?t=194)

**Jorge** introduces the SIP adding that Oron provided the implementation for associativity of the infix type, not for the prefix type. **Martin** makes the remark that Dotty does the same thing. He continues by saying he is "skeptical" about *prefix* types, as it seems to be another feature and "a necessary compromise to the mathematical conventions". On the other hand, he believes that once the roots for the associativity are fixed **?? PLEASE ADD, I DONT UNDERSTAND WHAT HE SAYS.**
**Martin** concludes by saying "yes" to the infix part and "no" to the prefix part. **Adriaan** agrees and adds that the best way to go forward would be to split up the SIP, based on the "one idea one SIP" motto, noting that *prefix* and *infix* types, even though related, are not dependent therefore should be treated separately.
The Committee agrees with Adriaan.

**Conclusion** The SIP 35 should be split in two separate SIPs, underlining that one related to *prefix* types needs more convincing as for now it looks like a "dead-end".
The *infix* type has sound ground and should be worked on.
The feedback will be given to the author.



### [SIP-28 and SIP-29: Inline and meta](http://docs.scala-lang.org/sips/pending/inline-meta.html)
[YouTube time: 10'05'' until the end](https://youtu.be/aIc-o1pcRhw?t=605)


**Olaf** introduces himself as the new SIP project lead, and goes as  [YouTube time: 10'05'' - 15'32''](https://youtu.be/aIc-o1pcRhw?t=605):

# SIP-29: Macros update October 2017

From the last SIP meeting:
>  Conclusion: The SIP is delayed until Olaf gathers the team and has some new
>  updates to share with the Committee.

"We have a team of contributors:
- myself, project lead working for the Scala Center on proposal SCP-014:
  towards "non-experimental" macro system (my interpretation: portable and
  robust macros).
- Liu Fengyun, on behalf of the Dotty team.
- Mikhail Mutcianco, on behalf of Jetbrains.

We are in a dialogue with:
- Eugene Burmako
- Scala community via contributors.scala-lang.org
- Heather Miller
- Ryan Culpepper
- Adriaan Moors/Jason Zaugg, Scala compiler team


My role as I see it is to
- communicate with involved parties,
- research the macro landscape/ecosystem,
- coordinate engineering efforts on the new macro system so that it 1) addresses
  existing pains and 2) at least something is delivered within a timeline of 4-6 months.

What I'd like to get out of this meeting is to present our findings from the
past 3 weeks, give my personal recommendations and collect your feedback on how
to prioritize our upcoming work"



**Conclusion**: The SIP is delayed until **Olaf** gathers the team and has some new updates to share with the Committee.
