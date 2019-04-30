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

Nun wo wir Frameworks mit voll funktionalen Pattern-Libraries (-Bibliotheken) verglichen haben, soll noch ein anderer Blick folgen. Frameworks können auch einfach als die Stylesheets und Skripte betrachtet werden, die sie sind; und externe Frameworks als _geteilte_ Stylesheets und Skripte, denen ein höhere Status zugestanden wird. Man könnte tatsächlich _jedwedes_ Stylesheet oder Skript oder beides herauspicken und es zum Framework deklarieren! 

Die Konsequenzen dieser zweiten Erkenntnis sind weitreichend; und auch wenn sie erst trivial anmutet, ist sie doch ein Schlüssel dafür, Frameworks zu verstehen. Wir werden den Begriff »Framework« weiter verwenden, um die übliche Sprache im Feld zu gebrauchen, aber werden uns zwischendurch zur Orientierung durchaus auf die Idee erhabener Stylesheets und Skripte berufen. 

## Why Frameworks?

Frameworks versprechen, sowohl Design- als auch Entwicklungszeit zu sparen. Die Denkweise dahinter ist, dass viele der Dinge, die Website-Betreiber und -Entwickler wollen, schon tausende Male gemacht wurden, und dass deshalb das Rad nicht neu erfunden werden muss oder sollte. Interne Frameworks werden hier normalerweise etwas nüchterner betrachtet, so dass dies besonders auf externe Frameworks zutrifft (mehr zur Unterscheidung in einem Augenblick).

Wenn Frameworks mit diesem Versprechen kommen, muss man sich eigentlich die Frage stellen, ob sie es auch erfüllen. Die Antwort darauf läuft letztlich auf eine Kostenkalkulation hinaus, die unglücklicher- aber auch logischerweise für jedes Projekt und Framework anders ausfällt. Was für Entwicklungskosten wurden eingespart? Wieviel wurde im Gegenzug für Training, Anpassungen und Aktualisierungen ausgegeben?  

Ergänzend zum Vorschlag, diese Rechnungen tatsächlich durchzuführen und jedes Projekt entsprechend zu _durchdenken_, behandeln die nächsten Seiten Frameworks in dem Detail, das notwendig ist, um jedem zu ermöglichen, eine eigene Theorie von den <i>raisons d'être</i> für Frameworks aufzustellen. 

## Arten und Einsatzfälle von Frameworks

Alle Frameworks bilden Design-Patterns ab, aber trotzdem müssen wir erstmal allgemeinere Unterscheidungen treffen. Zum einen gibt es einen Unterschied zwischen internen und externen Frameworks – wobei es oftmals nur die externen sind, die gemeinhin als Frameworks bezeichnet werden. Zum anderen gibt es, offensichtlich aber dennoch wichtig, einen Unterschied zwischen der Benutzung und der Entwicklung von Frameworks (auch wenn Entwickler selbst auch Nutzer sein können, was für eine gewisse Unschärfe sorgt). Und dann gibt es noch den Unterschied zwischen Neulingen und Experten.

Das sollten wir einmal skizzieren.

| | Experte | | Neuling | |
| --- | --- | --- | --- | --- |
| | Benutzen | Entwickeln | Benutzen | Entwickeln |
| Internes Framework | ? | ? | ? | ? |
| Externes Framework | ? | ? | ? | ? |

Was denken Sie? Sollten beide Arten von Frameworks auf beide Arten betrieben werden, von beiden Gruppen?

Hier sind meine Gedanken. Lassen Sie uns vergleichen.

| | Experte | | Neuling | |
| --- | --- | --- | --- | --- |
| | Benutzen | Entwickeln | Benutzen | Entwickeln |
| Internes Framework | ✅ ja | ✅ ja | ✅ ja | ✅ ja |
| Externes Framework | ⛔ nein️ | ✅ ja | ✅ ja | ⛔ nein |

Beachten Sie, dass das Entwickeln eines internen Frameworks und Veröffentlichen dessen, eine Auslegung, die sogar auf Blog-Themes angewandt werden könnte, hier nicht als Entwicklung eines externen Frameworks betrachtet wird. Der ausschlaggebende Punkt ist die Zielsetzung während der anfänglichen Entwicklungsphase. Eine grundlegende Revision und Überarbeitung eines Frameworks, um es extern oder ausschließlich intern zu machen, würde eine solche Entwicklungsphase jedoch darstellen und damit akzeptabel im Sinne dieser Kriterien sein. 

Was die Tabelle darstellt, ist die Idee, dass Frameworks mit lediglich zwei Ausnahmen liberal verwendet und entwickelt werden sollten. Eine Ausnahme ist, dass Experten keine externen Frameworks gebrauchen sollten; die andere, dass Anfänger keine externen Frameworks entwickeln sollten.

Beiden Ausnahmen, von denen die erste vor allem heute, einige Jahre nach Erscheinen der Originalausgabe dieses Buches, sehr hart wirken muss, liegt eine Verletzung von Qualitätsstandards oder der Annahme solches Standards zugrunde: Während ein externes Framework den Idealen eines Experten (welche ich später beschreibe) widersprechen sollte, hätte ein Neuling zwangsläufig noch gar keine Ideale, um ein hochwertiges Framework überhaupt entwerfen zu können.

Ein internes Framework ist immer sicher zu verwenden oder entwickeln, weil es dem bevorzugten Weg entspricht, Websites und -Apps zu bauen. Intern ist immer besser als extern weil extern nie alle Bedürfnisse des entsprechenden Projekts kennen kann, und damit qualitativ an vielen Stellen inferior ist. Dazu kommt, dass interne Lösungen sowohl für Experten als auch Neulige die effektivere Route darstellen, in Übung zu bleiben und sich weiterzuentwickeln, nicht nur, weil ihre Fehler, die jeder von uns begeht, hier eine kleinere Reichweite haben.  

Die Entwicklung eines externen Frameworks ist am besten bei einem (oder natürlich mehreren) erfahrenen Webentwickler aufgehoben, einem der entsprechend der Prinzipien, die in diesem Buch aufgezeigt werden, selbiges Framework so bauen und dokumentieren kann, dass es tatsächlich nützlich ist, und das bei einem annehmbaren Verhältnis von Kosten zu Nutzen. Dem weniger erfahrenen Entwickler oder dem, der in Eile ist, wird der Gebrauch eines externen Frameworks eher deshalb angeraten, weil ihm manche Aspekte weniger wichtig sind; er mag weniger auf Qualität achten und vielleicht geht es ihm auch gar nicht um eine langfristige Vision für das entsprechende Projekt.   

I> ### Kompilierte Frameworks
I>
I> Kompilierte, zusammengestellte Frameworks sind solche, die Stylesheets und Skripte von Dritten umfassen. Dies mögen öffentliche Reset-Stylesheets sein, kann aber auch durchaus umfangreiche UI-Elemente beinhalten. Skeleton band ursprünglich z.B. [Normalize.css](https://necolas.github.io/normalize.css/) ein, während Blueprint auf [Eric Meyers CSS-Reset](https://meyerweb.com/eric/tools/css/reset/) aufsetzt. Vor ein paar Jahren waren [WrapBootstrap](https://wrapbootstrap.com/) and [Flat UI Pro](https://designmodo.com/flat/) eher einfache Beispiele für kompilierte Frameworks, weil sie schlicht Bootstrap erweitern (wie so einige andere, nun, Stylesheets). Generell aber finden wir die Gattung der kompilierten Frameworks am häufigsten intern, wenn Organisation ihre eigenen Frameworks auf der Basis extierender öffentlicher Lösungen zusammenschrauben.
I>
I> Wir gehen auf diese Art von Framework nicht weiter ein, weil sie letztlich auf externen Frameworks aufbauen, die wir behandeln. Um aber auf der sicheren Seite zu sein: zusammengesetzte Frameworks bedeuten zusammengesetzte Probleme, und bedeuten zusätzliche Arbeit, was Tests und Wartung anbelangt. Erhöhte Aufmerksamkeit ist gefragt. 

## Beliebte Frameworks

@@

There are many dozens of HTML/CSS frameworks that developers
have found useful. Here is a representative selection, to give you an
impression of what the world of external frameworks feels like:

* 960 Grid System
* 1140 CSS Grid
* Base
* Bijou
* Bootstrap
* Blueprint
* Cascade Framework
* Columnal
* Compass
* CSS Smart Grid
* Fluid Baseline Grid
* Foundation
* Gantry
* Golden Grid System
* Goldilocks
* Gridiculo.us
* Gridless
* Gridlock
* Gumby
* Groundwork
* HTML KickStart
* HTML5 Boilerplate
* IceCream
* Ingrid
* InuitCSS
* IVORY Framework
* KNACSS
* kouto swiss
* Kube
* Layers CSS
* Less Framework
* Metro UI CSS
* Mueller Grid System
* Profound Grid
* Pure
* Responsee
* ResponsiveAeon
* Responsive Grid System
* Salsa
* Semantic Grid System
* Simple Grid
* Skeleton
* Susy
* Titan
* Toast
* Tuktuk
* YAML

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