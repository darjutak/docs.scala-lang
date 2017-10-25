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


### [SIP-34: Right-Associative By-Name Operators](http://docs.scala-lang.org/sips/right-associative-by-name-operators.html) (Numbered: SIP-34)
[YouTube time: 00.31''- 2'03''](https://youtu.be/aIc-o1pcRhw?t=32)

**Jorge** states that    


**Conclusion**: The SIP is numbered as "SIP-34", by unanimity and it will be at disposal for a month for the community comments.

### [SIP-35: Opaque types](http://docs.scala-lang.org/sips/opaque-types.html) (Numbered: SIP-35)
[YouTube time: 8'27''-51'13''](https://youtu.be/yzTpVbTUj18?t=507)

**Sébastien**, as a reviewer, is asked to present the SIP to the Committee and Public.
The Committee likes the proposal overall, though it has some questions/concerns.
In a 40min discussion the questions raised were as follows:

1. Articulating the motivation, emphasis on what is the concrete use of it
2. Articulating the direction regarding the value classes
3. How do we explain to users having both opaque types and multi parameter value classes **Eugene** [(link 1)](https://youtu.be/yzTpVbTUj18?t=1005); [(link 2)](https://youtu.be/yzTpVbTUj18?t=1094)
- Even "getting rid" of value classes, and letting opaque taking its place? **Seth** [(link)](https://youtu.be/yzTpVbTUj18?t=1753)
4. The importance of consistency across the language **Josh** [(link)](https://youtu.be/yzTpVbTUj18?t=1442)
5. Mention impact on Valhalla, value types at the JVM level
6. Investigate the possibilities for exposing bounds **Martin** [(link)](https://youtu.be/yzTpVbTUj18?t=2092)
7. Opaque type companion **Iulian** [(link)](https://youtu.be/yzTpVbTUj18?t=788)
- Raising confusion about the companion relation **Heather** and **Seth** [(link)](https://youtu.be/yzTpVbTUj18?t=1545)
Syntax "new" "type"


**Conclusion**: The SIP is numbered as "SIP 35" by unanimous vote. The above mentioned should to be addressed for the next meeting.


### [SIP-33: Match infix and prefix types to meet expression rules](http://docs.scala-lang.org/sips/make-types-behave-like-expressions.html)

Still waiting on the implementation updates, therefore this item will be discussed in the next SIP Meeting.

### [SIP-28 and SIP-29: Inline and meta](http://docs.scala-lang.org/sips/pending/inline-meta.html)
[YouTube time: 51'40'' until the end](https://youtu.be/yzTpVbTUj18?t=3100)

**Eugene** gives a brief history of this SIP development, shares the good news and suggests how to proceed.

**Eugene** is proud to report that the new prototype "looks good" and was published at Scala Days 2017. It can handle the def macros, macro notations and other.
Furthermore, there is a possibility of scaling it up to potentially replace the Scala reflect macros.
He raises the concern about moving forward.
He points out that so far the proposal was done on the voluntary basis and therefore the progress was slowed down.
However, after the Advisory Board approved to involve Scala Center to assist the community with "productionizing the existing prototype", there is a bright future for the project.

That said, **Eugene** suggests to delay the proposal in order to allow the time to see what comes out of the experiments.
After **Heather** raises the question about project transfer, proposing **Olaf** as a new lead and **Eugene** as an advisor, **Eugene** agrees and is happy that the project can move forward.

**Conclusion**: The SIP is delayed until **Olaf** gathers the team and has some new updates to share with the Committee.
