# Frameworks entwickeln

Frameworks zu entwickeln ist eine Kunst, die mit einer Menge Verantwortung einhergeht. Externe Frameworks haben dabei etwas von Draufgängertum (gepaart mit einem Schuss Naivität). Wie das gesamte Buch bisher festhält, es ist notwendigerweise am schwierigsten, ein externes Framework zu bauen, weil wir die Bedürfnisse anderer Projekte nicht kennen _können_. Aus diesem Grund kommen Entwickler von externen Frameworks zwangsläufig in die Lage, etwas auszuliefern, dem es irgendwo mangelt – oder das vielzu viel ist.

Der folgende Abschnitt beschreibt die Grundlagen für die Entwicklung eines Frameworks, mit speziellem Bezug für die Arbeit in einer größeren Organisation.

## Prinzipien

Wir haben hierzu bereits alle Aufgaben erledigt und alle Prinzipien für die Framework-Entwicklung erarbeitet. Ein Framework sollte entsprechend die höchsten Qualitätsstandards anstreben, und:

1. Ein Framework sollte maßgeschneidert sein.
2. Ein Framework sollte benutzerfreundlich sein.
3. Ein Framework sollte erweiterbar sein.

Diese Prinzipien sollten die Hauptwerte für jedes Framework darstellen, und dazu können wir bereits auf Methoden zurückgreifen, die in vorherigen Abschnitten behandelt wurden.

Anpassungs- und Konfigurationsmöglichkeiten, wie in Abschnitt »1. Ein Framework sollte maßgeschneidert sein« behandelt, spielt hier eine besondere Rolle, da diese die Geheimwaffe – und letzte Verteidigungslinie – des externen Framework-Entwicklers sind. Frameworks-Konfigurationsoptionen sind der einzige Weg, es fremden Nutzern, Nutzern, deren Projekte wir nie kennenlernen werden, möglich zu machen, zuzuschneiden.

Ich habe mich ursprünglich dagegen entschieden, einen Abschnitt speziell über die Konfiguration zu ergänzen (und auch für den Moment in dieser ergänzten deutschen Ausgabe). Zum einen stellt Konfiguration kein Allheilmittel für externe Frameworks dar, zum anderen erschafft sie so viele Probleme (Aufgaben) im Entwicklungsbereich, dass dieser in vielen Situation prohibitiv teuer wird. Dies liegt daran, dass je mehr Konfigurationsmöglichkeiten es gibt, desto komplexer ein Framework wird. Zu der Entwicklungsarbeit selbst gehören dann natürlich auch immer noch Tests, Qualitätsmanagement, Wartung, usw.

## Prototyp

Das wichtigste, was für ein erfolgreiches Framework benötigt wird, ist ein Prototyp. Hierbei ist nochmal die Erkenntnis wichtig, dass wir es wirklich nur mit einfachen Stylesheets und Skripten zu tun haben. Große Projekte – Projekte, für die Frameworks wirklich gebraucht werden – haben immer schon von Prototypen profitiert.

Was bedeutet denn Prototyp? In seiner einfachsten Form ist dies eine statische (interne) Website. Diese sollte alle Dokumenttypen und -elemente beinhalten, die wir in der Produktion benötigen, denn hier wird aller Code für Struktur (HTML), Präsentation (CSS) und Verhalten (JavaScript) zusammengetragen. Der Prototyp sollte realistische, wo wichtig auch »extreme« Beispielinhalte umfassen – dies dient dem Testen, dass alles funktioniert.

Ein Prototyp ist unersetzlich, damit wir testen können, ob das Framework wirklich funktioniert und seinen Zweck erfüllt.

Prototypen unterliegen eigenen Kriterien. Sie müssen, wie ich vor Jahren einmal [skizziert](https://meiert.com/de/publications/talks/20070523/#toc-requirements) habe, folgendes sein oder anstreben:

* Vollständig
* Aktuell
* Realistisch
* Fokussiert
* Zugänglich/verfügbar
* Diszipliniert betrieben
* Gewartet
* Kommuniziert/beworben
* Dokumentiert

(Ich glaube, diese nun mehr als 10 Jahre alten Punkte bedürfen der Revision und Restrukturierung.)

Jeder dieser Punkte ist wichtig, aber die ersten drei kritisch. Ein Prototyp muss wirklich alles umfassen (alle Seitentypen und -elemente, auch wenn dies aus einer Content- und nicht App-Perspektive kommt), er muss aktuell sein (jegliche Änderungen müssen sofort angewendet werden und sichtbar sein) und er muss realistisch sein (Beispielinhalte müssen eine möglichst gute Annäherung daran sein, wie das Framework wahrscheinlich außerhalb des Prototypen verwendet wird).

Gute Prototypen sind auch eine Kunst und bedürfen einer wesentlich längeren Ausführung.

## Qualitätsmanagement

Um sicherzustellen, dass wir die Qualität liefern, zu der wir uns als Experten oft verpflichten wollen, müssen wir diese überprüfen. Dies wird durch Qualitätssicherung (die darauf abzielt, Probleme über den Prozess zu verhindern) und Qualitätskontrolle (die Probleme im Produkt sucht und behebt) erzielt.

Das immer noch eher junge Feld der Webentwicklung kennt mehr Qualitätskontrolle als -sicherung. Ein gutes Beispiel dafür sind die vielen [Validierer](https://uitest.com/analysis/#validation), [Barrierefreiheits-](https://uitest.com/analysis/#accessibility) und [Performance-Tests](https://uitest.com/analysis/#performance). Auf der Qualitätssicherungsseite ist das prominenteste Beispiel die Erstellung und Verfolgung von Code-Richtlinien, wobei manche Organisationen und Einzelpersonen vor allem in den letzten Jahren durchaus spezielle und ausgefeilte Infrastruktur aufgebaut haben, um ihren Code zu testen und zu verbessern. (Dies alles bezieht sich eher auf Web- denn auf Softwareentwicklung, denn in der Softwareentwicklung gibt es hier eine stärkere Historie und Tradition, mit Tests zu arbeiten. Auch hier gab es gerade nach 2015 noch viele weitere Verbesserungen.)

Zur Qualitätssicherung ist es nützlich:

* Code-Richtlinien zu etablieren;
* Qualitätskriterien für den Output zu definieren;
* regelmäßig Tests (über Prototyp und Live-Implementierung) laufen zu lassen.

Zur Qualitätskontrolle sollte man folgendes testen:

* Barrierefreiheit
* Links (wenn anwendbar)
* Performance
* Responsiveness
* Wartbarkeit
* Validierung
* Code-Qualität
* Formatierung

(Ich selbst betreibe einen Hub für solche Tools, und habe ein kleines Büchlein geschrieben, das näher auf das Thema Qualitätskontrolle eingeht: Werfen Sie gerne einen Blick auf [uitest.com/analysis/](https://uitest.com/analysis/) für eine umfangreiche Sammlung an Werkzeugen, um Website zu bauen und testen, sowie [_The Little Book of Website Quality Control_](https://www.oreilly.com/library/view/the-little-book/9781492042860/) für ein paar weitere Gedanken zum Thema.)

Es ist, um es im Geiste von Google – und Effizienz – auszudrücken, immer sinnvoll, solche Tests zu automatisieren. Die Dokumentation einzelner Tools gibt oft schon wichtige Hinweise, da viele Werkzeuge lokal installiert werden können, über eine API verfügen oder andersartig wie über npm eingesetzt werden können. Dazu gibt es Instrumente wie [Selenium](https://www.seleniumhq.org/) und [ChromeDriver](http://chromedriver.chromium.org/), die automatisiertes Testen im Browser ermöglichen. Wie bei vielen anderen komplexen Themen, kann hier nur grob in eine Richtung verwiesen werden.

## Wartung

Wir haben bisher aufgeführt, wie wichtig Prinzipien, ein Prototyp und Qualitätsmanagement für die Frameworks-Entwicklung sind. Der letzte Schlüssel ist Wartung. Wartung bedeutet hier (wie bei Prototypen) vor allem das Commitment, die Hingabe zu einem Framework. Dies ist aus zwei Gründen von Bedeutung.

Zum einen ist Wartung entscheidend, weil der Gebrauch eines Frameworks ein Versprechen an seine Nutzer ist. Das Versprechen umfasst auf jeden Fall, dass das verwendete Framework, wenn nicht bereits garantiert für immer perfekt gewartet wird. Das Versprechen verlangt sogar noch mehr als Wartung, nämlich dass wer auch immer es wartet, er alles in seiner Macht stehende tut, keine strukturellen Änderungen vorzunehmen, sondern nach Möglichkeit nur präsentations- und verhaltensbezogene.

Zum anderen, weil das Commitment zu Wartung eine weitere Sicherheitsmaßnahme darstellt. Die Idee in der Webentwicklung ist (sollte sein), dass das [HTML am wichtigsten ist](https://meiert.com/de/publications/articles/20091027/), wirklich gut zu schreiben, weil es am teuersten ist, zu ändern – Stichwort Kostendefinition –, und zwar wesentlich teurer als Stylesheets und Skripte. (Daran hat sich auch mit weiterem Tooling und neueren Frameworks nichts wesentlich geändert.) Ein ausdrückliches Commitment hält uns davon ab, ein Framework zu verwerfen, auslaufen zu lassen, um »einfach ein neues zu nehmen«, und ist damit wiederum auch näher an der Vision von Nur-CSS-Design-Iterationen und -Refactorings. (Natürlich werden strukturelle Änderungen auch immer HTML-Anpassungen, damit auch CSS- und JavaScript-Modifikationen und für das Framework neue »Major«-Releases erfordern.)

Ein Framework, das echte und sogar komplexte Design- und Entwicklungsprobleme löst, kommt mit einer ganz expliziten Verpflichtung zu Wartung. Das haben die populäreren Frameworks über die Jahre längst bewiesen.

I> ### Warten und Kaputtmachen
I>
I> Hier ist etwas Ironisches: Auch wenn wir als Framework-Entwickler verantwortungsbewusst und sorgfältig vorgehen sollten, mit Framework-Updates nichts unnötig kaputt zu machen, sollten wir uns davor auch nicht übermäßig sorgen. Zur Frage, was das Wichtigste sei, wenn man Frameworks entwickelt und wartet, habe ich vor ein paar Jahren [folgendes entgegnet](https://plus.google.com/+JensOMeiert/posts/4aVAQhJvnh6):
I>
I> »Je häufiger ein Framework verwendet wird, je erfolgreicher es damit ist, desto wahrscheinlicher wird es, dass Updates und Wartungsarbeiten mal etwas kaputt machen. […] Wartung ist der Schlüssel, aber es ist unmöglich, sicher zu stellen, dass nie etwas schief geht, und der Versuch allein schon unglaublich teuer. Dazu kommt, dass selbst wenn Dinge schief gehen, sie nie [katastrophal] schief gehen. Das führt wieder zum Setzen von Erwartungen: […] die Leute sollten Updates nicht fürchten, sondern schätzen.«
I>
I> Ich denke, dass diese Einschätzung noch immer solide ist. Code kann mit Furcht nichts anfangen. Wenn wir als Entwickler unsere Hausarbeit machen, können gelegentliche Probleme sogar eine gute (und vielleicht die einzige) Sache sein, Framework-Nutzer im Umgang mit Grundregeln und ordentlichem Framework-Gebrauch zu schulen, und eventuelle Code-Probleme aufzuzeigen. Als Entwickler müssen wir manchmal auch unangenehme Entscheidungen treffen.

### Aktualisierungen

Die Handhabung von Framework-Updates ist so wichtig, dass wir sie nochmal gesondert behandeln sollten. Sie sind generell einfacher bei internen als bei externen Frameworks, obwohl Aktualisierungen in großen Organisationen mit vielen Entwicklern und Teams, die weit verstreut sind, ebenfalls eine Herausforderung darstellen.

Hier sind ein paar Tricks, die Framework-Aktualisierungen einfacher machen:

* Versuchen Sie, wegen der vergleichsweise hohen Kosten HTML-Änderungen zu vermeiden. Updates sollten idealerweise nur in Styling- oder Skripting-Anpassungen bestehen und keine besonderen Arbeiten für Nutzer bedeuten (das umfasst Entwickler, die mit dem Framework arbeiten). Die Anpassung von Framework-Referenzen (URL-Anpassungen, Paketaktualisierungen) sind natürlich okay.

* Kündigen Sie Aktualisierungen im Voraus an.

* Bieten Sie eine Möglichkeit, Aktualisierungen im Vorfeld auf Nebeneffekte zu prüfen. Dies kann durch etwas einfaches wie Bookmarklets geschehen (siehe Info-Kasten) oder durch etwas raffiniertes wie Proxying (wobei ein Proxy Requests abfängt, um Framework-Dateien zu ändern oder umzuleiten, um darüber dann zu testen).

* Informieren Sie Nutzer über mögliche Nebeneffekte (und nutzen Sie die Gelegenheit, auf die bereits beschriebenen Probleme beim Überschreiben hinzuweisen).

* Kommunizieren Sie den Status laufender Updates.

Wovon wir hier ausgehen ist, dass wir nicht einfach nur Frameworks »versionieren«. Das ist die Praxis, ein Framework rauszubringen – sagen wir, `foo` – und bei der ersten Änderung nicht `foo` zu aktualisieren, sondern `foo-2` auszuliefern. Und dann `foo-3`. Und so weiter. Diese Praxis kann eine Option sein, muss aber nicht die Regel bilden. Die Regel sollte sein, das Framework selbst nach den hier vorgestellten Ideen zu aktualisieren. Der Grund dafür ist, dass Versionierung den Zweck und [Vorteil von CSS](https://meiert.com/en/blog/advantage-of-css/) unterminiert (und ähnlich so von JavaScript), was mittels der Trennung der Belange (_Separation of Concerns_) sofortige Updates bedeutet. Wir werden diese Vision, die sehr stark darauf aus ist, Updates sofort auszuspielen und Arbeit zu vermeiden, nochmal behandeln – vor allem, da dies aktuell, mehrere Jahre nach Schreiben des Buches etwas sehr strikt und wider dem gegenwärtigen Usus anmuten mag. Bei größeren, »Major«-Aktualisierungen sollte damals wie heute auf jeden Fall ein Versionssprung in Erwägung gezogen werden.

I> ### Test-Bookmarklets
I>
I> CSS-Bookmarklets sind immer noch eine schöne, Low-Tech-Methode, es zu ermöglichen, Frameworks-Neuerungen vorab zu testen.
I>
I> Framework:
I>
I> ```css
I> article {
I>   margin: auto;
I>   width: 50%;
I> }
I> ```
I>
I> Framework nach Update:
I>
I> ```css
I> article {
I>   width: 90%;
I> }
I> ```
I>
I> Um einen Test des Updates vorzubereiten, um zu prüfen, dass auch alles in Zukunft wie gehabt funktioniert, nimmt man alle geänderten sowie etwaige _entfernte_ Deklarationen, setzt die Eigenschaften der entfernten Deklarationen auf ihre _Initial_-Werte und generiert so die Testregeln:
I>
I> Test-Stylesheet:
I>
I> ```css
I> article {
I>   margin: 0;
I>   width: 90%;
I> }
I> ```
I>
I> Wir vereinfachen das hier etwas mit der Annahme, dass `<article>` keine `margin`-Werte von woanders aufschnappt. `margin` muss gesetzt werden, da auch wenn es in der Framework-Aktualisierung entfernt wurde, es immer noch durch das alte Framework angewandt wird, welches ja wiederum noch auf den Seiten greift, auf denen wir den neuen Code testen wollen. Entsprechend muss das Test-Stylesheet diesen vorherigen Code neutralisieren – etwas was wir in sehr kniffligen Fällen zur Not auch noch durch die [`all`-Eigenschaft](https://www.w3.org/TR/css3-cascade/#all-shorthand) probieren könnten.
I>
I> Jesse Rudermans [Bookmarklet-Generator](https://www.squarefree.com/userstyles/make-bookmarklet.html) ist ein sehr einfaches aber funktionsfähiges Werkzeug, um solchen Test-Code in ein Bookmarklet zu überführen (indem man das Test-CSS einfügt und den entsprechenden Bookmarklet-Code kopiert). Das Bookmarklet kann dann jedem Framework-Nutzer zusammen mit einem Weg, Probleme zu melden, zur Verfügung gestellt werden.

## Dokumentation

Obwohl dies streng genommen kein Teil des Entwicklungsprozesses ist, darf hier auch Dokumentation nicht fehlen. Dokumentation dort aufzuhängen, wo die Entwicklung passiert, hat viele Vorteile, vom Erhöhen der Wahrscheinlichkeit, dass tatsächlich dokumentiert wird bis hin zur Verbesserung von Umfang und Genauigkeit, weil dann dokumentiert wird, wenn gerade noch alles frisch im Kopf ist.

Es gibt viele Arten, zu dokumentieren, aber eine der effektivsten ist, einen bzw. den Prototypen auch für diese Zwecke einzusetzen. @@

There are several ways to document, but one of the more effective
ones is using a prototype for this purpose too. Sample contents can
be turned into documentation describing the page types and ele‐
ments they’re forming, but it’s also possible to use hover-style info
boxes that share background information and explain the code. (A
properly maintained prototype enriched this way may even do most
of the lifting of any framework site!)

Documentation begins in the code, however, and there, too, we need
to exercise discipline. Our coding guidelines should underline this;
documentation standards like CSSDOC and JSDOC, as well as tools
that automatically pull such documentation from our code, can be
of great help.

The idea behind documentation is to make life easier for ourselves,
our colleagues, framework users, and any people interested in the
work. Thus, making it part of the development process goes a long
way.

## Logistics

Our journey, now that we diligently worked through everything rel‐
evant to frameworks, is soon over. A bonus aspect concerns logis‐
tics. We have covered a few pieces that can be considered logistics:

* Coding guidelines
* Quality-control tools
* Documentation

What we haven’t touched are:

* Framework development plans or roadmaps
* Version control systems (like Git, Mercurial, or Subversion)
* Request and bug management systems (like Bugzilla)
* Framework sites (public for external frameworks) with news feeds
* Mailing lists for
** Developers (framework development team)
** Users (open to everyone interested)
** Announcements (low-volume essentials which should go to
the developers and users lists, too)
* Trackers for live implementations

A framework site and an announcements list are particularly note‐
worthy, as they can pay good dividends to framework owners and
developers. The site serves as a hub for information and documenta‐
tion. An announcements list is indispensable to inform customers
about new releases and guide framework users.

Support also falls into the logistics category. It does not get more
attention here because, for one, we “embed” support at several land‐
marks along the way—in quality goals and principles, in documen‐
tation and logistics—and for another, support is more of a tangential
topic that depends on the complexity and circumstances of the
framework and the problems it tries to solve.

D> To repeat, for expert framework development, we need
to pay special attention to:
D>
D> * Principles
D> * A prototype
D> * Quality management
D> * Maintenance
D> * Documentation
D> * Logistics
D>
D> As these are ordered in descending order of impor‐
tance, our frameworks can probably survive with poor
support and gaping docs, but sacrifices in vision, test‐
ing, and commitment will break their necks.