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

Prototypen unterliegen eigenen Kriterien. Sie müssen, wie ich vor Jahren einmal [skizziert](@@) habe, folgendes sein oder anstreben:

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

Das immer noch eher junge Feld der Webentwicklung kennt mehr Qualitätskontrolle als -sicherung. Ein gutes Beispiel dafür sind die vielen [Validierer](@@), [Barrierefreiheits-](@@) und [Performance-Tests](@@). Auf der Qualitätssicherungsseite ist das prominenteste Beispiel die Erstellung und Verfolgung von Code-Richtlinien, wobei manche Organisationen und Einzelpersonen vor allem in den letzten Jahren durchaus spezielle und ausgefeilte Infrastruktur aufgebaut haben, um ihren Code zu testen und zu verbessern. (Dies alles bezieht sich eher auf Web- denn auf Softwareentwicklung, denn in der Softwareentwicklung gibt es hier eine stärkere Historie und Tradition, mit Tests zu arbeiten. Auch hier gab es gerade nach 2015 noch viele weitere Verbesserungen.)

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

Zum anderen, weil das Commitment zu Wartung eine weitere Sicherheitsmaßnahme darstellt. Die Idee in der Webentwicklung ist (sollte sein), dass das [HTML am wichtigsten ist](@@), wirklich gut zu schreiben, weil es am teuersten ist, zu ändern – Stichwort Kostendefinition –, und zwar wesentlich teurer als Stylesheets und Skripte. (Daran hat sich auch mit weiterem Tooling und neueren Frameworks nichts wesentlich geändert.) Ein ausdrückliches Commitment hält uns davon ab, ein Framework zu verwerfen, auslaufen zu lassen, um »einfach ein neues zu nehmen«, und ist damit wiederum auch näher an der Vision von Nur-CSS-Design-Iterationen und -Refactorings. (Natürlich werden strukturelle Änderungen auch immer HTML-Anpassungen, damit auch CSS- und JavaScript-Modifikationen und für das Framework neue »Major«-Releases erfordern.)

Ein Framework, das echte und sogar komplexte Design- und Entwicklungsprobleme löst, kommt mit einer ganz expliziten Verpflichtung zu Wartung. Das haben die populäreren Frameworks über die Jahre längst bewiesen.

I> ### Warten und Kaputtmachen
I>
I> Hier ist etwas Ironisches: Auch wenn wir als Framework-Entwickler verantwortungsbewusst und sorgfältig vorgehen sollten, mit Framework-Updates nichts unnötig kaputt zu machen, sollten wir uns davor auch nicht übermäßig sorgen. Zur Frage, was das Wichtigste sei, wenn man Frameworks entwickelt und wartet, habe ich vor ein paar Jahren [folgendes entgegnet](@@):
I>
I> »Je häufiger ein Framework verwendet wird, je erfolgreicher es damit ist, desto wahrscheinlicher wird es, dass Updates und Wartungsarbeiten mal etwas kaputt machen. […] Wartung ist der Schlüssel, aber es ist unmöglich, sicher zu stellen, dass nie etwas schief geht, und der Versuch allein schon unglaublich teuer. Dazu kommt, dass selbst wenn Dinge schief gehen, sie nie [katastrophal] schief gehen. Das führt wieder zum Setzen von Erwartungen: […] die Leute sollten Updates nicht fürchten, sondern schätzen.«
I>
I> Ich denke, dass diese Einschätzung noch immer solide ist. Code kann mit Furcht nichts anfangen. Wenn wir als Entwickler unsere Hausarbeit machen, können gelegentliche Probleme sogar eine gute (und vielleicht die einzige) Sache sein, Framework-Nutzer im Umgang mit Grundregeln und ordentlichem Framework-Gebrauch zu schulen, und eventuelle Code-Probleme aufzuzeigen. Als Entwickler müssen wir manchmal auch unangenehme Entscheidungen treffen.

### Aktualisierungen

@@

The handling of framework updates is delicate enough to deserve a
separate section. Updates are generally easier to manage for internal
frameworks than for external ones, though updates in a large orga‐
nization with many developers spread out over many places can be
challenging, too.

Here are a few tricks to make framework updates easier:

* Try to avoid HTML changes because of their comparatively
high cost. An update should only consist of styling or scripting
changes and impart no actual work for users (which, to counter
the aforementioned definition blurriness, also means developers
who work with the framework). The update of framework refer‐
ences can be OK.
* Announce updates in advance.
* Provide a way to test whether the update would have any ill
effects. This can happen through something simple like book‐
marklets (see “Test Bookmarklets” on page 23), or something
more sophisticated like proxying (using a proxy to intercept and
change requests to framework files in order to feed updated files
for testing).
* Inform users about possible side effects (and use this as an
opportunity to educate them about, for example, the problems
of overwrites, as explained in “2. Don’t overwrite framework
code” on page 15).
* Communicate the status of ongoing updates.

What we’re assuming here is that we’re not just “versioning” frame‐
works. That’s the practice of shipping a framework—let’s say, foo—
and when the first changes come, not updating foo, but shipping
foo-2. And then foo-3. And so on. This practice may be an option for
us, but not a rule. The rule should be to update the framework itself,
per the ideas listed here. The reason is that versioning defeats the
purpose and advantage of CSS (similarly for JavaScript), which are
immediate changes, supported by separation of concerns (HTML
for structure, CSS for presentation, and JavaScript for behavior).
We’ll touch on the vision behind this shortly, but we should strive to
do all updates through what we already have. And only for major
changes do we look into our toolbox and, always carefully, recon‐
sider versioning.

I> ### Test Bookmarklets
I>
I> CSS bookmarklets are a great low-tech way of allowing users to test
framework changes. A short example:
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
I> Framework after update:
I>
I> ```css
I> article {
I>   width: 90%;
I> }
I> ```
I>
I> To prepare a test for the update and make sure everything keeps
working as intended, take all the changed declarations and all the
removed declarations, set the removed declarations’ properties to
their defaults, and on that basis, generate the testing rules:
I>
I> Test style sheet:
I>
I> ```css
I> article {
I>   margin: 0;
I>   width: 90%;
I> }
I> ```
I>
I> We’re simplifying here by assuming that <article> doesn’t pick up
other margin values from anywhere else. margin has to be set
because while it’s been removed from the new framework, it would
still be applied through the old framework, which is in effect on the
pages where we want to test the new code. So the test style sheet
needs to neutralize all old code—something we could in really
tricky cases, as a last resort, also attempt through the all property.
I>
I> Jesse Ruderman’s bookmarklet generator is minimal but a fine tool
to turn test code into a bookmarklet (by pasting the test CSS and
copying bookmarklet code). That bookmarklet can then be pro‐
vided to any framework user, along with a way to report problems.

## Documentation

Though not technically a part of the development process, docu‐
mentation must be discussed. Anchoring documentation where the
development happens has many advantages, from increasing the
chances that it’s actually done, to being more comprehensive and
accurate because it’s fresh on the mind.

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