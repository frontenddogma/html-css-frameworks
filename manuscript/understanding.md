# Frameworks verstehen

## Was ist ein Framework?

»Framework« ist ein weitgefasster Begriff, der manchmal auch missverstanden wird. Konzeptionell und im Sinne der Webentwicklung kann ein Framework mit einer Bibliothek verglichen werden: eine Bibliothek nicht von Büchern, sondern von Design-Patterns, zusammen mit der entsprechenden Funktionalität. 

Das [Pure-Framework](https://purecss.io/) kennt beispielsweise die folgenden Button-Typen:

* Default
* Inaktiv
* Aktiv
* Primär

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

Das fehlende Puzzlestück, oder schon buchstäblich Verbindungsstück, ist, diese Bilbliothek zu verknüpfen, um über das vorgegebene Markup die Funktionalität auch auf die ausgewählten Patterns anzuwenden.

Eine der einfachsten Arten, Bootstrap zu verwenden, besteht beispielsweise darin, etwas wie folgendes zu referenzieren:

```html
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
```

Nachdem wir Frameworks mit voll funktionalen Pattern-Libraries (-Bibliotheken) verglichen haben, kommt hier noch eine andere Perspektive. Frameworks können auch einfach als die Stylesheets und Skripte betrachtet werden, die sie sind; und externe Frameworks als _geteilte_ Stylesheets und Skripte, denen ein höhere Status zugestanden wird. Man könnte tatsächlich _jedwedes_ Stylesheet oder Skript (oder beides) herauspicken und es zum Framework deklarieren! 

Die Konsequenzen dieser zweiten Erkenntnis sind weitreichend; und auch wenn sie erst trivial anmutet, ist sie doch ein Schlüssel dafür, Frameworks zu verstehen. Wir werden den Begriff »Framework« weiter verwenden, um die übliche Sprache im Feld zu gebrauchen, aber werden uns zwischendurch zur Orientierung durchaus auf die Idee erhabener Stylesheets und Skripte berufen. 

## Warum Frameworks?

Frameworks versprechen sowohl Design- als auch Entwicklungszeit zu sparen. Die Denkweise dahinter ist, dass viele der Dinge, die Website-Betreiber und -Entwickler wollen, schon tausende Male gemacht wurden, und das Rad deshalb nicht neu erfunden werden muss oder sollte. Interne Frameworks werden hier normalerweise etwas nüchterner betrachtet, so dass dies besonders auf externe Frameworks zutrifft (mehr zur Unterscheidung in einem Augenblick).

Wenn Frameworks mit diesem Versprechen kommen, muss man die Frage stellen, ob sie es auch erfüllen. Die Antwort darauf läuft letztlich auf eine Kostenkalkulation hinaus, die unglücklicher- aber auch logischerweise für jedes Projekt und Framework anders ausfällt. Was für Entwicklungskosten wurden eingespart? Wieviel wurde im Gegenzug für Training, Anpassungen und Aktualisierungen ausgegeben?

Ergänzend zum Vorschlag, diese Rechnungen tatsächlich durchzuführen und jedes Projekt entsprechend zu _durchdenken_, behandeln die nächsten Seiten Frameworks in dem Detail, das notwendig ist, um jedem zu ermöglichen, eine eigene Theorie von den _raisons d’être_ für Frameworks aufzustellen. 

## Arten und Einsatzfälle von Frameworks

Alle Frameworks bilden Design-Patterns ab, aber trotzdem müssen wir erstmal allgemeinere Unterscheidungen treffen. Zum einen gibt es einen Unterschied zwischen internen und externen Frameworks – wobei mit »Framework« öfter die externen bezeichnet werden. Zum anderen gibt es, offensichtlich aber dennoch wichtig, einen Unterschied zwischen der Benutzung und der Entwicklung von Frameworks (auch wenn Entwickler selbst oft auch Nutzer sind, was für eine gewisse Unschärfe sorgt). Und dann gibt es noch den Unterschied zwischen Neulingen und Experten.

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

Beachten Sie, dass das Entwickeln eines internen Frameworks und dessen Veröffentlichung (eine Auslegung, die sogar auf Blog-Themes angewandt werden könnte) hier nicht als Entwicklung eines externen Frameworks betrachtet wird. Der ausschlaggebende Punkt ist die Zielsetzung während der anfänglichen Entwicklungsphase. Eine grundlegende Revision und Überarbeitung eines Frameworks, um es extern oder ausschließlich intern zu machen, würde jedoch eine solche Entwicklungsphase darstellen und damit akzeptabel im Sinne dieser Kriterien sein. 

Was die Tabelle zeigt, ist die Idee, dass Frameworks mit lediglich zwei Ausnahmen liberal verwendet und entwickelt werden können. Eine Ausnahme ist, dass Experten keine externen Frameworks _benutzen_ sollten; die andere, dass Anfänger keine externen Frameworks _bauen_ sollten.

Beiden Ausnahmen, von denen die erste vor allem heute, einige Jahre nach Erscheinen der Originalausgabe dieses Buchs, sehr hart wirken muss, liegt eine Verletzung von Qualitätsstandards oder der Annahme solcher Standards zugrunde: Während ein externes Framework den Idealen eines Experten (welche ich später beschreibe) widersprechen sollte, hätte ein Neuling zwangsläufig noch gar keine Ideale, um überhaupt ein hochwertiges Framework entwerfen zu können.

Ein internes Framework ist immer sicher zu verwenden oder entwickeln, weil es dem bevorzugten Weg entspricht, Websites und -Apps zu bauen. Intern ist immer besser als extern, weil eine externe Lösung nie alle Bedürfnisse eines fremden Projekts kennen kann und sie damit in einem entscheidenden Punkt _per se_ schon qualitativ inferior ist. Dazu kommt, dass interne Lösungen sowohl für Experten als auch Neulinge die effektivere Route darstellen, in Übung zu bleiben und sich weiterzuentwickeln, und das nicht nur, weil hier Fehler, die jeder von uns begeht, eine kleinere Reichweite haben.

Die Entwicklung eines externen Frameworks ist am besten bei einem (oder natürlich mehreren) erfahrenen Webentwickler aufgehoben, einem der entsprechend der Prinzipien, die in diesem Buch aufgezeigt werden, selbiges Framework so bauen und dokumentieren kann, dass es tatsächlich nützlich ist, und das bei einem annehmbaren Verhältnis von Kosten zu Nutzen. Dem weniger erfahrenen Entwickler oder dem, der in Eile ist, wird der Gebrauch eines externen Frameworks nur deshalb angeraten, weil ihm manche Aspekte weniger wichtig sind; er mag weniger auf Qualität achten und vielleicht geht es ihm auch gar nicht um eine langfristige Vision für das entsprechende Projekt.

I> ### Kompilierte Frameworks
I>
I> Kompilierte, zusammengestellte Frameworks sind solche, die auch Stylesheets und Skripte von Dritten umfassen. Dies mögen öffentliche Reset-Stylesheets sein, kann aber auch durchaus umfangreiche UI-Elemente einschließen. Skeleton band ursprünglich z.B. [Normalize.css](https://necolas.github.io/normalize.css/) ein, während Blueprint auf [Eric Meyers CSS-Reset](https://meyerweb.com/eric/tools/css/reset/) aufsetzt. Vor ein paar Jahren waren [WrapBootstrap](https://wrapbootstrap.com/) and [Flat UI Pro](https://designmodo.com/flat/) eher einfache Beispiele für kompilierte Frameworks, weil sie schlicht Bootstrap erweiterten (wie so einige andere, nun, Stylesheets). Generell aber finden wir die Gattung der kompilierten Frameworks am häufigsten intern, wenn Organisationen ihre eigenen Frameworks auf der Basis extierender öffentlicher Lösungen zusammenschrauben.
I>
I> Wir gehen auf diese Art von Framework nicht weiter ein, weil sie letztlich externen Frameworks gleichzusetzen sind, die wir behandeln. Um aber auf der sicheren Seite zu sein: Zusammengesetzte Frameworks bedeuten zusammengesetzte Probleme, und bedeuten zusätzliche Arbeit, was Tests und Wartung anbelangt. Erhöhte Aufmerksamkeit ist gefragt. 

## Beliebte Frameworks

Es gibt Dutzende – vielleicht Hunderte – von öffentlichen HTML-/CSS-Frameworks, die Webentwickler bisher als nützlich empfunden haben. Hier ist eine Auswahl, um einen Eindruck davon zu vermitteln, wie groß die Welt der Frameworks geworden ist:

* [960 Grid System](https://960.gs/)
* [Basscss](https://basscss.com/)
* [Beard](http://buildwithbeard.com/)
* [Bijou](https://andhart.github.io/bijou/)
* [Blueprint](http://www.blueprintcss.org/)
* [Bootstrap](https://getbootstrap.com/)
* [Brutalist Framework](http://www.brutalistframework.com/)
* [Bulma](https://bulma.io/)
* [Compass](http://compass-style.org/)
* [CSS Smart Grid](http://origin.css.gd/)
* [Foundation](https://foundation.zurb.com/)
* [Gantry](http://gantry.org/)
* [Golden Grid System](http://goldengridsystem.com/)
* [Gridless](https://thatcoolguy.github.io/gridless-boilerplate/)
* [HiQ](https://jonathanharrell.github.io/hiq/)
* [HTML KickStart](http://www.99lime.com/elements/)
* [HTML5 Boilerplate](https://html5boilerplate.com/)
* [IceCream](http://html5-ninja.com/icecream/)
* [Ingrid](http://piira.se/projects/ingrid/)
* [KNACSS](https://www.knacss.com/)
* [kouto swiss](http://kouto-swiss.io/)
* [Kube](https://imperavi.com/kube/)
* [Layers CSS](http://labs.jerryjappinen.com/layers/)
* [Less Framework](http://lessframework.com/)
* [Metro](https://metroui.org.ua/)
* [Mueller Grid System](https://muellergridsystem.com/)
* [Profound Grid](https://www.profoundgrid.com/)
* [Pure](https://purecss.io/)
* [Responsee](https://www.myresponsee.com/)
* [Responsive Aeon](http://newaeonweb.com.br/responsiveaeon/)
* [Responsive Grid System](https://www.bigdropinc.com/blog/responsive-gs/)
* [Simple Grid](https://thisisdallas.github.io/Simple-Grid/)
* [Skeleton](http://getskeleton.com/)
* [Susy](https://www.oddbird.net/susy/)
* [Tachyons](http://tachyons.io/)
* [Tacit](https://yegor256.github.io/tacit/)
* [turretcss](https://turretcss.com/)
* [YAML](http://www.yaml.de/)

(Manche Lesen mögen sich dabei an [Choke](https://meiert.com/en/blog/choke/) erinnert fühlen, obwohl der Humor damals eher grob war.)

Die dargestellten Frameworks sind z.T. sehr unterschiedlich und variieren in Funktionalität und Scope. Manche konzentrieren sich auf Grund-Layouts, während andere den kompletten Bogen schlagen, um nicht nur mobiles sondern auch Druck-Styling anzubieten.

Auch wenn ihr Fundament noch immer auf 2015 basiert (sorgfältig geprüft und ergänzt), ist eine Aufzählung wie die obige etwas, das recht schnell veraltet. Während Frameworks wie ganz besonders YAML (nicht zu verwechseln mit [_YAML Ain’t Markup Language_](https://yaml.org/)) schon über ein Jahrzehnt alt sind, sind andere schon lange wieder in der Versenkung verschwunden – selbst aus der erst 2015 aufgenommenen Übersicht sind ganze _17_ Frameworks weggefallen (die meisten davon ersatzlos gestorben); sie stehen 8 neuen gegenüber.

Der Nutzen der Liste hat sich damit zwar immer noch langlebiger erwiesen als erwartet, dennoch geht es hier mehr um besagten Eindruck, einen raschen Schnappschuss, ganz vielleicht noch einen Ausgangspunkt zum Experimentieren, aber nicht um eine verlässliche Peilung für die gesamte Frameworks-Landschaft. Dazu ist diese Landschaft einfach zu groß und schnelllebig – und wenn manche der folgenden Thesen richtig sind, kennen wir ein paar der technischen Gründe dafür.