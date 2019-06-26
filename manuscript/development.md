# Frameworks entwickeln

Frameworks zu entwickeln ist eine Kunst, die mit einer Menge Verantwortung einhergeht, und externe Frameworks haben dabei was von Draufgängertum. Wie das Buch bisher festhält, ist es notwendigerweise am schwierigsten, ein externes Framework zu bauen, weil wir die Bedürfnisse anderer Projekte nicht kennen _können_. Aus diesem Grund kommen Entwickler von externen Frameworks zwangsläufig in die Lage, etwas auszuliefern, dem es irgendwo mangelt – oder das zuviel ist.

Der folgende Abschnitt beschreibt die Grundlagen für die Entwicklung eines Frameworks, mit speziellem Bezug auf die Arbeit in einer größeren Organisation.

## Prinzipien

Wir haben hierzu bereits viele Aufgaben erledigt und schon Prinzipien für die Framework-Entwicklung erarbeitet. Ein Framework sollte idealerweise die höchsten Qualitätsstandards anstreben und dazu

1. maßgeschneidert,
2. benutzerfreundlich und
3. erweiterbar

sein.

Diese Prinzipien sollten die Hauptwerte für jedes Framework darstellen, und zur Umsetzung können wir bereits auf Methoden zurückgreifen, die in vorherigen Abschnitten behandelt wurden.

Anpassungs- und Konfigurationsmöglichkeiten, wie im Abschnitt »1. Ein Framework sollte maßgeschneidert sein« behandelt, spielen hier eine besondere Rolle, da diese eine Geheimwaffe – und letzte Verteidigungslinie – des externen Framework-Entwicklers sind. Framework-Konfigurationsoptionen sind der einzige Weg, es fremden Nutzern, Nutzern, deren Projekte wir nie kennenlernen werden, möglich zu machen, zuzuschneiden.

Ich hatte mich ursprünglich dagegen entschieden, einen Abschnitt speziell zu Konfiguration zu schreiben (und das gilt für den Moment auch in dieser ergänzten deutschen Ausgabe). Zum einen stellt Konfiguration kein Allheilmittel für externe Frameworks dar, zum anderen bedeutet sie so viele zusätzliche Aufgaben im Entwicklungsbereich, dass die Entwicklung in vielen Situationen prohibitiv teuer werden kann. Dies liegt daran, dass je mehr Konfigurationsmöglichkeiten es gibt, desto komplexer ein Framework wird. Zur Entwicklungsarbeit selbst gehören dann natürlich auch immer noch Tests, Qualitätsmanagement, Wartung, usw.

## Prototyp

Das Wichtigste, das aus praktischer Sicht für ein erfolgreiches Framework benötigt wird, ist ein Prototyp. Hierbei ist nochmal die Erkenntnis wichtig, dass wir es immer noch mit Stylesheets und Skripten zu tun haben. Große Projekte – Projekte, für die Frameworks wirklich gebraucht werden – haben immer schon von Prototypen profitiert.

Was umfasst ein Prototyp? In seiner einfachsten Form eine statische Website. Diese sollte alle Dokumenttypen und -elemente beinhalten, die wir in der Produktion benötigen, denn hier wird aller Code für Struktur (HTML), Präsentation (CSS) und Verhalten (JavaScript) zusammengetragen. Der Prototyp sollte dabei realistische, wo wichtig auch extreme Beispielinhalte umfassen.

Ein Prototyp ist unersetzlich, damit wir testen können, ob ein Framework wirklich funktioniert, es seinen Zweck erfüllt und auch robust genug ist.

Prototypen unterliegen eigenen Kriterien. Sie müssen, wie ich vor Jahren einmal [beschrieben](https://meiert.com/de/publications/talks/20070523/#toc-requirements) habe, folgendes sein oder anstreben:

* vollständig
* aktuell
* realistisch
* fokussiert
* zugänglich/verfügbar
* diszipliniert betrieben
* gewartet
* kommuniziert/beworben
* dokumentiert

Auch wenn diese mehr als zehn Jahre alten Punkte mittlerweile der Revision und Restrukturierung bedürfen, ist jeder dieser Punkte wichtig, die ersten drei sogar kritisch. Ein Prototyp muss wirklich alles umfassen (alle Seitentypen und -elemente, auch wenn dies einer Content- und nicht App-Perspektive entspringt), er muss aktuell sein (jegliche Änderungen müssen sofort angewendet werden können und sichtbar sein) und er muss realistisch sein (Beispielinhalte müssen eine möglichst gute Annäherung daran darstellen, wie das Framework wahrscheinlich außerhalb des Prototypen verwendet wird).

Gute Prototypen sind wie Frameworks selbst eine Kunst und bedürfen anderswo einer wesentlich längeren Ausführung.

## Qualitätsmanagement

Um sicherzustellen, dass wir die Qualität liefern, zu der wir uns als Experten verpflichten wollen, müssen wir diese überprüfen. Dies wird durch Qualitätssicherung (die darauf abzielt, Probleme über den Prozess zu verhindern) und Qualitätskontrolle (die Probleme im Produkt sucht und behebt) erzielt.

Das immer noch eher junge Feld der Webentwicklung kennt mehr Qualitätskontrolle als -sicherung. Ein gutes Beispiel dafür sind die vielen [Validierer](https://uitest.com/analysis/#validation), [Barrierefreiheits-](https://uitest.com/analysis/#accessibility) und [Performance-Tests](https://uitest.com/analysis/#performance). Auf der Qualitätssicherungsseite ist das prominenteste Beispiel die Erstellung und Verfolgung von Code-Richtlinien, wobei manche Organisationen und Einzelpersonen vor allem in den letzten Jahren spezialisierte und ausgefeilte Infrastruktur aufgebaut haben, um ihren Code zu testen und zu verbessern. (Dies alles bezieht sich eher auf Web- denn auf Softwareentwicklung, denn in der Softwareentwicklung gibt es eine stärkere Historie und Tradition, mit Tests zu arbeiten. Auch hier gab es gerade nach 2015 noch viele weitere Verbesserungen.)

Zur Qualitätssicherung ist es nützlich:

* Qualitätskriterien für den Output zu definieren;
* Code-Richtlinien zu etablieren;
* regelmäßig Tests (über Prototyp und Live-Implementierung) laufen zu lassen.

Bei der Qualitätskontrolle sollte man folgendes testen:

* Barrierefreiheit
* Verlinkungen (wenn anwendbar)
* Performance
* Responsiveness
* Wartbarkeit
* Validierung
* Formatierung
* allgemeine Code-Qualität

(Ich selbst betreibe einen Hub für solche Tools, und habe ein kleines Büchlein geschrieben, das näher auf das Thema Qualitätskontrolle eingeht: Werfen Sie einen Blick auf [uitest.com/analysis](https://uitest.com/analysis/) für eine umfangreiche Sammlung an Werkzeugen, um Websites zu bauen und testen, sowie das seichte [_The Little Book of Website Quality Control_](https://www.oreilly.com/library/view/the-little-book/9781492042860/) für ein paar weitere Gedanken zum Thema.)

Ganz im Sinne der Effizienz ist es sinnvoll, Tests dann zu automatisieren. Die Dokumentation einzelner Tools gibt oft wichtige Hinweise, da viele Werkzeuge lokal installiert werden können, über eine API verfügen oder andersartig wie über npm eingesetzt werden können. Dazu gibt es Instrumente wie [Selenium](https://www.seleniumhq.org/) und [ChromeDriver](http://chromedriver.chromium.org/), die automatisiertes Testen im Browser oder »headless« ermöglichen. Wie bei vielen anderen komplexen Themen soll hier nur grob in eine Richtung verwiesen werden.

## Wartung

Wir haben bisher aufgeführt, wie wichtig Prinzipien, ein Prototyp und Qualitätsmanagement für die Frameworks-Entwicklung sind. Ein weiterer Schlüssel ist Wartung. Wartung bedeutet (wie bei Prototypen) vor allem das Commitment, die Hingabe zu einem Framework. Dies ist aus zwei Gründen von Bedeutung.

Zum einen ist Wartung entscheidend, weil der Gebrauch eines Frameworks ein Versprechen an seine Nutzer ist. Das sicher idealistische Versprechen umfasst, dass das verwendete Framework für immer gewartet wird. Es verlangt dazu sogar, dass wer auch immer es wartet, er alles in seiner Macht stehende tut, es einfach zu halten und somit keine strukturellen Änderungen vorzunehmen, sondern nach Möglichkeit nur präsentations- und verhaltensbezogene. Das ist ganz bestimmt Idealismus, aber wer soll uns an Ideale erinnern, wenn nicht wir selbst?

Zum anderen ist Wartung wichtig, weil das Commitment hierzu eine weitere Sicherheitsmaßnahme darstellt. Die Idee in der Webentwicklung ist (oder sollte sein), dass [HTML am wichtigsten ist](https://meiert.com/de/publications/articles/20091027/), wirklich gut zu schreiben, weil es am teuersten und im Vergleich zu CSS und JavaScript sogar _extrem_ teuer zu ändern ist – wir beachten unsere Kostendefinition. (Daran hat sich mit weiterem Tooling und neueren Frameworks erstmal nichts großartig geändert, aber konsequenter Einsatz von Komponenten rüttelt daran.) Ein ausdrückliches Commitment hält uns davon ab, ein Framework zu verwerfen, auslaufen zu lassen, um »einfach ein neues zu machen«, und ist damit wiederum auch näher an der Vision von Nur-CSS-Design-Iterationen. (Natürlich werden immer mal strukturelle Änderungen notwendig sein und damit HTML-Anpassungen, korrespondierende CSS- und JavaScript-Modifikationen und für das entsprechende Framework neue »Major«-Releases erfordern.)

Ein Framework, das echte und sogar komplexe Design- und Entwicklungsprobleme löst, kommt mit einer ganz expliziten Verpflichtung zu Wartung. Das haben die populäreren Frameworks über die Jahre selbst deutlich gezeigt – sie wurden nach meinem Kenntnisstand ausnahmslos alle gepflegt.

I> ### Warten und was kaputt machen
I>
I> Hier ist etwas Ironisches: Auch wenn wir als Framework-Entwickler verantwortungsbewusst und sorgfältig vorgehen sollten, mit (ehemals bewusst nicht versionierten) Framework-Updates nichts unnötig kaputt zu machen, sollten wir uns davor auch nicht übermäßig sorgen und selbst paralysieren. Zur Frage, was das Wichtigste sei, wenn man Frameworks entwickelt, habe ich vor ein paar Jahren [folgendes entgegnet](https://plus.google.com/+JensOMeiert/posts/4aVAQhJvnh6):
I>
I> »Je häufiger ein Framework verwendet wird, je erfolgreicher es damit ist, desto wahrscheinlicher wird es, dass Updates und Wartungsarbeiten mal etwas kaputt machen. […] Wartung ist der Schlüssel, aber es ist unmöglich, sicherzustellen, dass nie etwas schief geht, und der Versuch allein schon unglaublich teuer. Dazu kommt, dass selbst wenn Dinge schief gehen, sie [nicht unbedingt katastrophal] schief gehen. Das führt wieder zum Setzen von Erwartungen: […] die Leute sollten Updates nicht fürchten, sondern schätzen.«
I>
I> Ich denke, dass diese Einschätzung noch immer gilt. Code kann mit Furcht nichts anfangen. Wenn wir als Entwickler unsere Hausarbeiten machen, können gelegentliche Probleme sogar eine gute (und vielleicht die einzige) Sache sein, Framework-Nutzer im Umgang mit Grundregeln und ordentlichem Framework-Gebrauch zu schulen, und eventuelle Code-Probleme aufzuzeigen – zumindest bei internen Frameworks. Als Entwickler müssen wir manchmal auch unangenehme Entscheidungen treffen.

### Aktualisierungen

Die Handhabung von Framework-Updates ist so wichtig, dass sie nochmal gesondert betrachtet werden sollte. Updates sind generell einfacher bei internen als bei externen Frameworks durchzuführen, obwohl Aktualisierungen in großen Organisationen mit vielen Entwicklern und Teams, die weit verstreut sind, ebenfalls eine Herausforderung darstellen.

Hier sind ein paar Tricks, die Framework-Aktualisierungen einfacher machen:

* Versuchen Sie, wegen der vergleichsweise hohen Kosten HTML-Anpassungen (selbst Klassenänderungen) zu vermeiden. Updates sollten bevorzugt nur in Styling- oder Scripting-Arbeiten bestehen und keine besonderen Aufwände für Nutzer und Entwickler bedeuten. Die Anpassung von Framework-Referenzen (URL-Anpassungen, Paketaktualisierungen) sind okay.

* Kündigen Sie Aktualisierungen im Voraus an.

* Bieten Sie eine Möglichkeit, Aktualisierungen im Vorfeld auf Nebeneffekte zu prüfen. Dies kann durch etwas einfaches wie Bookmarklets geschehen (siehe Info-Kasten) oder durch etwas Raffiniertes wie Proxying (wobei ein Proxy Requests abfängt, um Framework-Dateien zu ändern oder umzuleiten und entsprechende Tests zu ermöglichen).

* Informieren Sie Nutzer über mögliche Nebeneffekte (und nutzen Sie die Gelegenheit, auf die bereits beschriebenen Probleme beim Überschreiben hinzuweisen).

* Kommunizieren Sie den Status laufender Updates.

Wovon wir hier ausgehen ist, dass wir nicht einfach nur Frameworks »versionieren«. Das ist die Praxis, ein Framework rauszubringen – sagen wir, `foo` – und bei der ersten Änderung nicht `foo` zu aktualisieren, sondern `foo-2` auszuliefern. Und dann `foo-3`. Und so weiter. Diese Praxis ist eine Option, muss aber nicht die Regel bilden. Die Regel sollte sein, das Framework nach den hier vorgestellten Ideen zu aktualisieren. Der Grund dafür ist, dass Versionierung den Zweck und [Vorteil von CSS](https://meiert.com/en/blog/advantage-of-css/) unterminiert (und ähnlich so von JavaScript), was mittels der Trennung der Belange (_Separation of Concerns_) sofortige Updates ermöglicht. Wir werden diese Vision, die sehr stark darauf aus ist, Updates sofort auszuspielen und unnötige Arbeit zu vermeiden, nochmal behandeln – vor allem, da dies aktuell, mehrere Jahre nach Schreiben des Buchs etwas sehr strikt und wider dem gegenwärtigen Usus anmuten mag. Bei größeren, [»Major«-Aktualisierungen](https://semver.org/) sollte damals wie heute auf jeden Fall ein Versionssprung in Erwägung gezogen werden.

D> Ich musste überlegen, wie ich mit den letzten Abschnitten am besten umgehe: Mittlerweile hat sich die Versionierung aller Arten von Software so stark eingebürgert, und das aus gutem Grund, dass der ehemalige Ansatz fast antiquiert wirken muss. Er unterlag aber der großen Motivation, durch das Auskosten eines bzw. _des_ Vorteils von CSS den Komfort zu bieten, _Updates sofort auszuspielen_ oder zu erhalten, ohne auf andere warten zu müssen oder anderswo tätig zu werden. 
D> 
D> Ehemals sahen viele im Feld, mich definitiv eingeschlossen, das als ganz entscheidenden Vorteil an; kollektiv haben wir uns in den letzten Jahren letztlich für den zwar aufwendigeren aber zumindest aus Sicht unerwarteter und unerwünschter Nebeneffekte sichereren Weg der Versionierung entschieden.

I> ### Test-Bookmarklets
I>
I> CSS-Bookmarklets sind immer noch eine schöne Low-Tech-Methode, es zu ermöglichen, Frameworks-Neuerungen vorab zu testen.
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
I> Wir vereinfachen das hier etwas mit der Annahme, dass `<article>` keine `margin`-Werte von woanders aufschnappt. `margin` muss gesetzt werden, da auch wenn es in der Framework-Aktualisierung entfernt wurde, es immer noch durch das alte Framework angewandt wird, welches ja wiederum noch auf den Seiten greift, auf denen wir den neuen Code testen wollen. Entsprechend muss das Test-Stylesheet diesen vorherigen Code neutralisieren – etwas was man in kniffligen Fällen auch noch durch die [`all`-Eigenschaft](https://www.w3.org/TR/css3-cascade/#all-shorthand) probieren kann.
I>
I> Jesse Rudermans [Bookmarklet-Generator](https://www.squarefree.com/userstyles/make-bookmarklet.html) ist ein einfaches aber funktionsfähiges Werkzeug, um solchen Test-Code in ein Bookmarklet zu überführen – man fügt das Test-CSS ein und kopiert den entsprechenden Bookmarklet-Code. Das Bookmarklet kann dann jedem Framework-Nutzer zusammen mit einem Weg, Probleme zu melden, zur Verfügung gestellt werden.

## Dokumentation

Obwohl streng genommen kein Teil des Entwicklungsprozesses, darf auch Dokumentation nicht fehlen. Dokumentation dort aufzuhängen, wo die Entwicklung passiert, hat viele Vorteile, vom Erhöhen der Wahrscheinlichkeit, dass tatsächlich dokumentiert wird bis hin zur Verbesserung von Umfang und Genauigkeit, weil dann dokumentiert wird, wenn gerade noch alles frisch im Kopf ist.

Es gibt viele Arten, zu dokumentieren, aber eine der effektivsten ist, einen bzw. den Prototypen auch für diese Zwecke einzusetzen. Beispielinhalte können in Dokumentation umgewandelt werden, die die Seitentypen und -elemente erklären, die sie selbst bilden, und es ist ebenso möglich, Informationskästen auf Hover oder andersartig anzuzeigen, die Hintergrundinformationen und zugehörigen Code beschreiben. (Ein sauber gewarteter Prototyp, der auf diese Weise aufgewertet wird, bildet ein äußerst belastbares Rückgrat eines Frameworks. Manches Designsystem ging in den letzten Jahren in diese Richtung, und [Storybook](https://storybook.js.org/), kann man sagen, treibt dies nochmal weiter.)

Dokumentation fängt ansonsten bereits im Code an, und dort müssen wir ebenfalls Disziplin an den Tag legen. Unsere Code-Richtlinien sollten dies unterstreichen und unterstützen; Dokumentationsstandards wie [CSSDOC](https://web.archive.org/web/20130701094049/http://cssdoc.net/) ([CSSdoc](https://github.com/Paratron/CSSdoc)?) und [JSDoc](https://devdocs.io/jsdoc/), ebenso wie Werkzeuge, die Dokumentation automatisch aus unserem Code generieren, können hier von großer Hilfe sein.

Die Idee hinter Dokumentation ist, dass wir uns, dem Team, den Framework-Nutzern sowie Interessierten das Leben etwas einfacher machen. Sie Teil des gesamten Entwicklungsprozesses zu machen ist in der Framework-Entwicklung genauso wichtig wie in der Entwicklung allgemein.

## Logistik

So emsig wie wir uns durch alle relevanten Framework-Themen hangeln, ist die Skizze auch fast vollständig. Der finale Aspekt ist die Framework-Logistik. Wir haben davon bereits ein paar Teile behandelt:

* Code-Richtlinien
* Werkzeuge zur Qualitätskontrolle
* Dokumentation

Was wir noch nicht berührt haben:

* Pläne und Roadmaps zur Framework-Entwicklung
* Versionskontrollsysteme (oftmals [Git](https://git-scm.com/), in früheren Zeiten auch [Mercurial](https://www.mercurial-scm.org/), [Subversion](https://subversion.apache.org/) und [CVS](https://www.nongnu.org/cvs/))
* Request- und Bug-Management-Systeme (wie [JIRA](https://www.atlassian.com/software/jira) oder [Bugzilla](https://www.bugzilla.org/))
* Framework-Websites mit Feeds und weiteren Features (öffentlich bei externen Frameworks)
* Mailing-Listen für
  * Entwickler (ob für Team oder Interessierte)
  * Nutzer (offen für jeden)
  * Ankündigungen (für die wichtigsten Neuigkeiten, die gleichzeitig auch an die Entwickler- und Nutzerlisten gehen sollten)
* Übersichten für Live-Implementierungen (primär für Tests und Stichproben, aber auch für Referenzen)

Eine Website für das Framework und eine Liste für Ankündigungen sind besonders empfehlenswert, weil sie Framework-Inhabern und -Entwicklern gute Dividende abwerfen. Die Website dient als Hub für Informationen und Dokumentation. Eine Ankündigungsliste ist unverzichtbar, um Interessierte über neue Veröffentlichungen auf dem Laufenden zu halten und Nutzer in eine für sie nützliche Richtung zu lenken. Durch beides wird das Framework benutzbarer und gleichzeitig die Support-Last der Entwickler reduziert.

Framework-Support fällt entsprechend ebenfalls in die Kategorie Logistik. Er bekommt hier aber keine weitere Aufmerksamkeit, weil wir Support zum einen an verschiedenen Stellen des Wegen unterstützen können – in Prinzipien, Zielen, Dokumentation – und zum anderen, weil Support stark von Details und Komplexität des Frameworks abhängt, und den Problemen, die es zu lösen versucht.

D> Gehen wir noch einmal durch alles durch. Für die Entwicklung hochwertiger Frameworks sollte auf folgendes geachtet werden:
D>
D> * Prinzipien
D> * Prototyp
D> * Qualitätsmanagement
D> * Wartung
D> * Dokumentation
D> * Logistik
D>
D> Da diese in absteigender Wichtigkeit geordnet sind, können Frameworks mit schlechtem Support und lückenhafter Dokumentation wahrscheinlich überleben, aber brechen sich alle Gräten, wenn es ihnen an Vision, Hingabe und Tests mangelt.