# Frameworks entwickeln

Frameworks zu entwickeln ist eine Kunst, die mit einer Menge Verantwortung einhergeht, und externe Frameworks haben dabei etwas von Draufgängertum. Wie das Buch bisher festhält, ist es notwendigerweise am schwierigsten, ein externes Framework zu bauen, weil wir die Bedürfnisse anderer Projekte nicht kennen _können_. Aus diesem Grund kommen Entwickler von externen Frameworks zwangsläufig in die Lage, etwas auszuliefern, dem es irgendwo mangelt – oder das viel zu viel ist.

Der folgende Abschnitt beschreibt die Grundlagen für die Entwicklung eines Frameworks, mit speziellem Bezug auf die Arbeit in einer größeren Organisation.

## Prinzipien

Wir haben hierzu bereits viele Aufgaben erledigt und die Prinzipien für die Framework-Entwicklung erarbeitet. Ein Framework sollte idealerweise die höchsten Qualitätsstandards anstreben, und:

1. Ein Framework sollte maßgeschneidert sein.
2. Ein Framework sollte benutzerfreundlich sein.
3. Ein Framework sollte erweiterbar sein.

Diese Prinzipien sollten die Hauptwerte für jedes Framework darstellen, und zur Umsetzung können wir bereits auf Methoden zurückgreifen, die in vorherigen Abschnitten behandelt wurden.

Anpassungs- und Konfigurationsmöglichkeiten, wie im Abschnitt »1. Ein Framework sollte maßgeschneidert sein« behandelt, spielt hier eine besondere Rolle, da diese eine Geheimwaffe – und letzte Verteidigungslinie – des externen Framework-Entwicklers sind. Framework-Konfigurationsoptionen sind der einzige Weg, es fremden Nutzern, Nutzern, deren Projekte wir nie kennenlernen werden, möglich zu machen, zuzuschneiden.

Ich hatte mich ursprünglich dagegen entschieden, einen Abschnitt speziell zu Konfiguration zu schreiben (und auch für den Moment in dieser ergänzten deutschen Ausgabe). Zum einen stellt Konfiguration kein Allheilmittel für externe Frameworks dar, zum anderen bedeutet sie so viele zusätzliche Aufgaben im Entwicklungsbereich, dass die Entwicklung in vielen Situationen prohibitiv teuer werden kann. Dies liegt daran, dass je mehr Konfigurationsmöglichkeiten es gibt, desto komplexer ein Framework wird. Zu der Entwicklungsarbeit selbst gehören dann natürlich auch immer noch Tests, Qualitätsmanagement, Wartung, usw.

## Prototyp

Das wichtigste, das für ein erfolgreiches Framework benötigt wird, ist ein Prototyp. Hierbei ist nochmal die Erkenntnis wichtig, dass wir es immer noch nur mit Stylesheets und Skripten zu tun haben. Große Projekte – Projekte, für die Frameworks wirklich gebraucht werden – haben immer schon von Prototypen profitiert.

Was bedeutet denn Prototyp? In seiner einfachsten Form eine statische Website. Diese sollte alle Dokumenttypen und -elemente beinhalten, die wir in der Produktion benötigen, denn hier wird aller Code für Struktur (HTML), Präsentation (CSS) und Verhalten (JavaScript) zusammengetragen. Der Prototyp sollte dabei realistische, wo wichtig auch extreme Beispielinhalte umfassen.

Ein Prototyp ist unersetzlich, damit wir testen können, ob das Framework wirklich funktioniert und seinen Zweck erfüllt.

Prototypen unterliegen eigenen Kriterien. Sie müssen, wie ich vor Jahren einmal [skizziert](https://meiert.com/de/publications/talks/20070523/#toc-requirements) habe, folgendes sein oder anstreben:

* vollständig
* aktuell
* realistisch
* fokussiert
* zugänglich/verfügbar
* diszipliniert betrieben
* gewartet
* kommuniziert/beworben
* dokumentiert

(Ich glaube, diese nun mehr als zehn Jahre alten Punkte bedürfen der Revision und Restrukturierung.)

Jeder dieser Punkte ist wichtig, aber die ersten drei kritisch. Ein Prototyp muss wirklich alles umfassen (alle Seitentypen und -elemente, auch wenn dies einer Content- und nicht App-Perspektive entstammt), er muss aktuell sein (jegliche Änderungen müssen sofort angewendet werden können und sichtbar sein) und er muss realistisch sein (Beispielinhalte müssen eine möglichst gute Annäherung daran darstellen, wie das Framework wahrscheinlich außerhalb des Prototypen verwendet wird).

Gute Prototypen sind wie Frameworks selbst eine Kunst und bedürften einer wesentlich längeren Ausführung.

## Qualitätsmanagement

Um sicherzustellen, dass wir die Qualität liefern, zu der wir uns als Experten verpflichten wollen, müssen wir diese überprüfen. Dies wird durch Qualitätssicherung (die darauf abzielt, Probleme über den Prozess zu verhindern) und Qualitätskontrolle (die Probleme im Produkt sucht und behebt) erzielt.

Das immer noch eher junge Feld der Webentwicklung kennt mehr Qualitätskontrolle als -sicherung. Ein gutes Beispiel dafür sind die vielen [Validierer](https://uitest.com/analysis/#validation), [Barrierefreiheits-](https://uitest.com/analysis/#accessibility) und [Performance-Tests](https://uitest.com/analysis/#performance). Auf der Qualitätssicherungsseite ist das prominenteste Beispiel die Erstellung und Verfolgung von Code-Richtlinien, wobei manche Organisationen und Einzelpersonen vor allem in den letzten Jahren spezielle und ausgefeilte Infrastruktur aufgebaut haben, um ihren Code zu testen und zu verbessern. (Dies alles bezieht sich eher auf Web- denn auf Softwareentwicklung, denn in der Softwareentwicklung gibt es hier eine stärkere Historie und Tradition, mit Tests zu arbeiten. Auch hier gab es gerade nach 2015 noch viele weitere Verbesserungen.)

Zur Qualitätssicherung ist es nützlich:

* Code-Richtlinien zu etablieren;
* Qualitätskriterien für den Output zu definieren;
* regelmäßig Tests (über Prototyp und Live-Implementierung) laufen zu lassen.

Bei der Qualitätskontrolle sollte man folgendes testen:

* Barrierefreiheit
* Links (wenn anwendbar)
* Performance
* Responsiveness
* Wartbarkeit
* Validierung
* Formatierung
* allgemeine Code-Qualität

(Ich selbst betreibe einen Hub für solche Tools, und habe ein kleines Büchlein geschrieben, das näher auf das Thema Qualitätskontrolle eingeht: Werfen Sie gerne einen Blick auf [uitest.com/analysis/](https://uitest.com/analysis/) für eine umfangreiche Sammlung an Werkzeugen, um Websites zu bauen und testen, sowie [_The Little Book of Website Quality Control_](https://www.oreilly.com/library/view/the-little-book/9781492042860/) für ein paar weitere Gedanken zum Thema.)

Ganz im Sinne der Effizienz ist es sinnvoll, Tests dann zu automatisieren. Die Dokumentation einzelner Tools gibt oft schon wichtige Hinweise, da viele Werkzeuge lokal installiert werden können, über eine API verfügen oder andersartig wie über npm eingesetzt werden können. Dazu gibt es Instrumente wie [Selenium](https://www.seleniumhq.org/) und [ChromeDriver](http://chromedriver.chromium.org/), die automatisiertes Testen im Browser ermöglichen. Wie bei vielen anderen komplexen Themen soll hier nur grob in eine Richtung verwiesen werden.

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

* Versuchen Sie, wegen der vergleichsweise hohen Kosten HTML-Änderungen zu vermeiden. Updates sollten bevorzugt nur in Styling- oder Skripting-Anpassungen bestehen und keine besonderen Arbeiten für Nutzer bedeuten (das umfasst Entwickler, die mit dem Framework arbeiten). Die Anpassung von Framework-Referenzen (URL-Anpassungen, Paketaktualisierungen) sind natürlich okay.

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

Es gibt viele Arten, zu dokumentieren, aber eine der effektivsten ist, einen bzw. den Prototypen auch für diese Zwecke einzusetzen. Beispielinhalte können in Dokumentation umgewandelt werden, die die Seitentypen und -elemente erklären, die sie selbst bilden, und es ist ebenso möglich, Informationskästen auf Hover anzuzeigen, die Hintergrundinformationen und zugehörigen Code beschreiben. (Ein sauber gewarteter Prototyp, der auf diese Weise aufgewertet wird, kann wirklich das Rückgrat eines Frameworks bilden. Manches Designsystem ging in den letzten Jahren in diese Richtung, und [Storybook](https://storybook.js.org/), kann man sagen, greift dies nochmals auf.)

Dokumentation fängt jedoch bereits im Code an, und dort müssen wir ebenfalls Disziplin an den Tag legen. Unsere Code-Richtlinien sollten dies unterstreichen und unterstützen; Dokumentationsstandards wie [CSSDOC](https://web.archive.org/web/20130701094049/http://cssdoc.net/) ([CSSdoc](https://github.com/Paratron/CSSdoc)?) und [JSDoc](https://devdocs.io/jsdoc/), ebenso wie Werkzeuge, die Dokumentation automatisch aus unserem Code generieren, sind hier von großer Hilfe.

Die Idee hinter Dokumentation ist, dass wir uns, dem Team, den Framework-Nutzern sowie Interessierten das Leben etwas einfacher machen. Sie Teil des gesamten Entwicklungsprozesses zu machen ist in der Framework-Entwicklung genauso wichtig wie in der Entwicklung allgemein.

## Logistik

Da wir uns emsig durch alle relevanten Framework-Themen durchhangeln, ist unsere Reise auch schon fast vorbei. Ein wichtiger Aspekt ist noch die Framework-Logistik. Wir haben davon bereits ein paar Teile behandelt:

* Code-Richtlinien
* Werkzeuge zur Qualitätskontrolle
* Dokumentation

Was wir noch nicht berührt haben:

* Pläne und Roadmaps zur Framework-Entwicklung
* Versionskontrollsysteme (oftmals [Git](https://git-scm.com/), ehemals auch gerne [Mercurial](https://www.mercurial-scm.org/), [Subversion](https://subversion.apache.org/), [CVS](https://www.nongnu.org/cvs/))
* Request- und Bug-Management-Systeme (wie [JIRA](https://www.atlassian.com/software/jira) oder [Bugzilla](https://www.bugzilla.org/))
* Framework-Websites mit Feeds und weiteren Features (öffentlich bei externen Frameworks)
* Mailing-Listen für
** Entwickler (ob für das Team oder Interessierte)
** Nutzer (offen für jeden)
** Ankündigungen (die wichtigsten Neuigkeiten, die auch an die Entwickler- und Nutzerlisten gehen sollten)
* Übersichten für Live-Implementierungen (primär für Tests und Samples, aber auch für Referenzen)

Eine Website für das Framework und eine Liste für Ankündigungen sind besonders erwähnenswert, weil sie Framework-Inhabern und -Entwicklern gute Dividende bringen. Die Website dient dabei als Hub für Informationen und Dokumentation. Eine Ankündigungsliste ist unverzichtbar, um Interessierte über neue Veröffentlichungen auf dem Laufenden zu halten und Nutzer in eine für sie nützliche Richtung zu lenken.

Framework-Support fällt ebenfalls in die Kategorie Logistik. Er bekommt hier aber keine weitere Aufmerksamkeit weil wir Support zum einen an verschiedenen Stellen des Wegen »einbetten« können – in Prinzipien, Zielen, Dokumentation – und zum anderen, weil Support stark von Details und Komplexität des Frameworks abhängt, und den Problemen, die es zu lösen versucht.

D> Gehen wir noch einmal durch alles durch. Für die Entwicklung hochwertiger Frameworks sollte auf folgendes geachtet werden:
D>
D> * Prinzipien
D> * Einen Prototyp
D> * Qualitätsmanagement
D> * Wartung
D> * Dokumentation
D> * Logistik
D>
D> Da diese in absteigender Wichtigkeit geordnet sind, können Frameworks mit schlechtem Support und lückenhafter Dokumentation wahrscheinlich überleben, aber brechen sich alle Gräten, wenn es ihnen an Vision, Tests oder Hingabe mangelt.