# Frameworks verstehen

## Was ist ein Framework?

»Framework« ist ein weitgefasster Begriff, der manchmal missverstanden wird. Konzeptionell und im Sinne der Webentwicklung kann ein Framework mit einer Bibliothek verglichen werden: eine Bibliothek nicht von Büchern, sondern von Design-Patterns, zusammen mit der entsprechenden Funktionalität. 

Das [Pure-Framework](https://purecss.io/) kennt beispielsweise die folgenden Button-Typen:

* Default
* Primär
* Aktiv
* Inaktiv
* Angepasst

»Funktionalität« bezieht sich normalerweise auf Darstellung/Präsentation (das Styling über CSS) und manchmal auch auf Verhalten (Scripting über JavaScript).

Der Vorteil darin, eine solche Bibliothek zu verwenden, beruht darin, dass wir diese Funktionalität nicht selbst schreiben müssen, oder so wiederholt tun müssen. Wir folgen statt dessen den Anweisungen der Bibliothek, was die Struktur anbelangt (Markup über HTML).

So erfordert beispielsweise [YAML](http://www.yaml.de/) den folgenden HTML-Code für ein horizontales Navigationsmenü:

```html
<nav class="ym-hlist">
  <ul>
    <li class="active"><strong>Aktiv</strong></li>
    <li><a href="#">Link</a></li>
    <li><a href="#">Link</a></li>
  </ul>
</nav>
```

Das einzig fehlende Puzzlestück, oder schon buchstäblich Verbindungsstück, ist, diese Bilbliothek zu verknüpfen, um über das vorgegebene Markup die Funktionalität auch auf die ausgewählten Patterns anzuwenden.

Eine der einfachsten Arten, Bootstrap zu verwenden, besteht beispielsweise darin, etwas wie folgendes zu referenzieren:

```html
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
```

Nun wo wir Frameworks mit voll funktionalen Pattern-Libraries (-Bibliotheken) verglichen haben, soll noch ein anderer Blick folgen. Frameworks können auch einfach als die Stylesheets und Skripte betrachtet werden, die sie sind; und externe Frameworks als geteilte Stylesheets und Skripte, denen ein höhere Status zugestanden wird. Man könnte tatsächlich _jedwedes_ Stylesheet oder Skript oder beides herauspicken und es zum Framework deklarieren! 

@@

The implications of this second insight are far-reaching. Although
rather trivial, it’s one of the keys to understanding frameworks. We’ll
keep the term “framework” to use common industry language but
will at times look at the idea of elevated style sheets and scripts for
guidance.
Understanding Frameworks | 3
Why Frameworks?
Frameworks promise to save both development and design time.
The thinking goes that many of the things site owners and develop‐
ers want have been done a thousand times, and thus there is no need
to reinvent the wheel. Internal frameworks commonly enjoy a more
sober regard, so this particularly applies to external frameworks.
If frameworks come with this promise, the question arises whether
or not they live up to it. The answer boils down to a cost calculation
that is, unfortunately, different for every framework and project.
How much development cost was saved? How much was, in turn,
spent on training, customization, and upgrades?
Apart from suggesting that we do the math and think through every
project, the following pages cover frameworks in the necessary
detail to empower everyone to form their own theory about the rai‐
sons d'être of frameworks.
Types and Uses of Frameworks
While all frameworks provide patterns, we must note general dis‐
tinctions. For one, there is a difference between internal and exter‐
nal frameworks—the external ones are those that typically get
referred to as frameworks. Then, there is a difference between using
and developing a framework (note that developers can be users,
which makes for some blurriness). And finally, there is a difference
between experts and amateurs.
Let’s chart this up.
Expert Beginner
Use Develop Use Develop
Internal framework ? ? ? ?
External framework ? ? ? ?
What do you think? Should either type of framework be managed
either way, by either group?
4 | The Little Book of HTML/CSS Frameworks
Here’s what I think. Let’s compare.
Expert Beginner
Use Develop Use Develop
Internal framework Yes Yes Yes Yes
External framework No Yes Yes No
Please note that developing an internal framework and making it
public, as we could even apply to blog themes, is here not consid‐
ered developing an external framework. The decisive factor is the
goal during the initial development process. A thorough revision
and overhaul of an framework to make it external or internal-only,
however, constitutes a development phase, and would be acceptable.
Reflected in the table is the idea that frameworks can be used and
developed liberally, with two exceptions. One exception is that
experts shouldn’t use external frameworks; the other is that beginners
shouldn’t develop external frameworks.
The two exceptions stem from a violation of quality standards: while
the external framework violates the ideals of the expert (which I will
later describe), it is the beginner who would not even know the nec‐
essary ideals to create a quality framework.
The internal framework is safe to use or develop in every case
because that’s the preferred way of developing web documents and
apps. Internal beats external every time because external cannot, by
definition, know all the needs of the organization and fails many
quality standards. Second, internal solutions are the better route for
both experts and beginners to stay sharp and to learn, since their
mistakes have a smaller impact.
The development of an external framework is safest only with an
experienced web developer, who can, following the principles out‐
lined in this book, skillfully build and document it so that it has a
better chance to be useful, at a low cost-benefit ratio. For the less
experienced developer or the one in a hurry, use of an external
framework is thought to be more viable simply because things mat‐
Understanding Frameworks | 5
ter a lot less for him; he may discern few impacts in quality, and he
may not yet have a long-term vision for his project.
Compilation Frameworks
Compilation frameworks are frameworks that include third-party
style sheets and scripts. These may be public reset style sheets, but
can extend to elaborate UI elements. Skeleton, for example, used to
build on Normalize.css, while Blueprint is thought to incorporate
Eric Meyer’s CSS reset. WrapBootstrap and Flat UI Pro are arguably
compilation frameworks because they extend Bootstrap, but we
typically find the compilation framework species internally, when
institutions build their own frameworks based on existing public
ones.
We don’t cover compilation frameworks in more detail because they
expand on the external frameworks we do cover. But to err on the
safe side: composite frameworks mean composite problems, and
there’s extra work involved in testing and maintaining. Special
attention is in order.
Popular Frameworks
There are many dozens of HTML/CSS frameworks that developers
have found useful. Here is a representative selection, to give you an
impression of what the world of external frameworks feels like:
• 960 Grid System
• 1140 CSS Grid
• Base
• Bijou
• Bootstrap
• Blueprint
• Cascade Framework
• Columnal
• Compass
• CSS Smart Grid
• Fluid Baseline Grid
6 | The Little Book of HTML/CSS Frameworks
• Foundation
• Gantry
• Golden Grid System
• Goldilocks
• Gridiculo.us
• Gridless
• Gridlock
• Gumby
• Groundwork
• HTML KickStart
• HTML5 Boilerplate
• IceCream
• Ingrid
• InuitCSS
• IVORY Framework
• KNACSS
• kouto swiss
• Kube
• Layers CSS
• Less Framework
• Metro UI CSS
• Mueller Grid System
• Profound Grid
• Pure
• Responsee
• ResponsiveAeon
• Responsive Grid System
• Salsa
• Semantic Grid System
• Simple Grid
• Skeleton
Understanding Frameworks | 7
• Susy
• Titan
• Toast
• Tuktuk
• YAML
(Some readers will remember Choke, too, although that humor may
have been rather crude.)
These frameworks all vary in functionality and scope. Some focus
on base layouts, while others go all the way into comprehensive
print and mobile themes.
Such a list of frameworks is the type of information that goes stale
quickly. While some frameworks, most notably YAML (not to be
confused with YAML Ain’t Markup Language), have been around
for many years, other frameworks come and go. It’s more useful to
obtain said impression from this list, regard it as a snapshot, and,
perhaps, make it a starting point to experiment