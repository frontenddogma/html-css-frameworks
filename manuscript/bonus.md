{sample: true}
# Nachwort

Den Abschluss dieses Buchs bildet ein Artikel, der einige meiner konkreten Erfahrungen mit der Entwicklung von Frameworks widerspiegelt, und zwar der als Ideengeber und leitender Entwickler der damals ersten Google-Web-Frameworks Go (2008) und Maia (2012). Der Bericht ist eine leicht modifizierte Variante der Fassung, die Sie auch unter [meiert.com/de/publications/articles/20171005](https://meiert.com/de/publications/articles/20171005/) finden.

## Was ich beim Entwickeln von Googles Frameworks gelernt habe

In [_The Little Book of HTML/CSS Frameworks_](https://www.oreilly.com/library/view/the-little-book/9781492048121/) habe ich eine Übersicht und viele Praxistipps zu Frameworks veröffentlicht; ich halte das Buch für eines meiner besten Werke, auch wenn nicht jeder seinen Empfehlungen zustimmt (in den meisten Fällen sollten wir externe Frameworks vermeiden, weil sie die [Vision](https://meiert.com/en/blog/vision-of-web-dev/) bzw. das [erste Paradigma](https://meiert.com/en/blog/two-paradigms/) der Webentwicklung verletzen).

Nirgendwo habe ich jedoch bisher über die Erfahrung gesprochen, einige größere Frameworks entwickelt zu haben – weder über das 2004er Framework (auch wenn wir es damals nicht so genannt haben) von [GMX](https://www.gmx.net/) und Partner-Sites wie [1&1](https://home.1und1.de/), was möglicherweise die erste europäische Milliarden-Besucher-Website bedeutete, die auf [validem](https://meiert.com/en/blog/about-validation/) HTML und vollständig entkoppeltem CSS bedeutete, noch über die 2008er und 2012er Frameworks, die ich bei Google baute, die letztlich auf Zehntausenden Google-Webseiten verwendet und einige Milliarden Mal aufgerufen wurden. Was folgt, erzählt einen Teil der Google-Geschichte.

Diese Geschichte sollte mit dem Zustand von Googles informationsbezogenen Websites in 2008 beginnen, als einige qualitätsbewusste Webentwickler, einer von ihnen ich, bei Google anfingen, zu arbeiten. Gelinde gesagt: Es war nicht schön, und wir erhielten viel [Kritik](https://meiert.com/en/blog/web-standards-at-google/) von einer Vielzahl angesehener Entwickler (dies machte dann einen der Gründe aus, warum es spannend war, sich dem [Webmaster-Team](https://webmasters.googleblog.com/2011/05/introducing-google-webmaster-team.html) anzuschließen).

Von außen, und so einige andere Googler waren sich dessen bewusst, bestand die Unschönheit hauptsächlich in der schlechten Code-Qualität von Googles Websites und Produkten. Die Google-Homepages bekam dabei die meiste Aufmerksamkeit, aber auch bei Produkten, die sonst gut ankamen, wurden Qualitätsprobleme von Fachleuten nicht übersehen.

Von innen, und von hier an werde ich nur noch von Google-Websites (und nicht mehr Produkten) sprechen, war klar, dass uns effektivere Prioritäten, Prozesse und – noch wichtiger – Werkzeuge fehlten; zu diesem Zeitpunkt wurden die meisten von Googles Websites händisch erstellt und gewartet.

An diesem Problem arbeitete das Team, speziell das Kernteam in Mountain View sowie ein paar Entwickler in Zürich, um ein Content-Management-System zu implementieren, das auch in Google-Dimensionen funktionierte. Wir veröffentlichten regelmäßig Websites und Einstiegsseiten in Dutzenden Sprachen, und unsere Code-Basis, HTML-Dokumente mitsamt anderem Beiwerk, umfasste schon 2008 eine sechsstellige Zahl von Dateien.

Eine Herausforderung wie auch Gelegenheit war die Diversität der Sites und Seiten, die wir erstellten. Ja, es gab eine Google-Kernidentität und Google arbeitete an einem unternehmensweiten Styleguide (die UX-Organisation um [Irene Au](https://ireneau.com/) hatte sich dem angenommen) – aber viele unserer Websites, zumindest Elemente darauf, waren einzigartig und einmalig. Diese Einzigartigkeit machte einen Grund aus, warum es noch keine solide technische Basis gab, und ich begann [proaktiv](https://meiert.com/en/blog/googliness/), das erste Google’sche HTML-/CSS-Framework zu entwickeln: [Go](https://www.google.com/css/go.css) (es ging der [Programmiersprache](https://golang.org/) voraus, dessen Team der Namenskonflikt entging).

### Go

Go war speziell, was schlicht den einmaligen Umständen geschuldet ist. Go ist, und selbst [in minifizierter Form](https://www.google.com/css/go.css) kriegt man davon einen Eindruck, ein kompaktes Framework. Das ist _by design_. Aber wie wurde es entworfen, und warum? Dazu sollten wir nochmal auf Googles Landschaft an Websites blicken – ein Blick, der tatsächlich [Pflicht](https://meiert.com/en/blog/tailoring-frameworks/) ist, wenn wir Frameworks entwerfen (aber auch [benutzen](https://meiert.com/en/blog/framework-rules/)).

Besagte Landschaft bestand aus einem international verteilten Team – dem Webmaster-Team – mit bunt gemischten internen Kunden, die von Google Corporate Communications über Legal bis hin zu Marketing reichten, das eine große Zahl von sehr unterschiedlichen, lokalisierten – bis zu 40, manchmal 50 Sprachen – Websites betrieb. Das erschuf einiges an Einzigartigkeit. Gleichzeitig geschah alle Arbeit unter dem Schirm von Google, einige Designaspekte wurden also von allen Seiten geteilt.

Sie nehmen sicher schon wahr, dass dieser übereinstimmende Teil klein war, und dass das, und nicht die hohe Zahl von Unterschieden, einen zentralen Teil von Gos Vision ausmachen musste: Go sollte nicht versuchen, »alles« abzudecken, was wir taten, sondern _gut an der Basis funktionieren_. Den kleinsten gemeinsamen Nenner finden und abbilden, das war die Idee.

Das nächste Prinzip hinter Go war _Einfachheit_, da diese Einfachheit große Gewinne versprach: Zum einen hat Einfachheit eine große Zahl großer technischer Vorteile, von höherer Geschwindigkeit über größere Robustheit bis hin zu [leichterer Wartbarkeit](https://meiert.com/de/publications/articles/20090907/). Zum anderen führt Einfachheit zu guter _Entwicklerbenutzerfreundlichkeit_ (Entwicklerfreundlichkeit?) mitsamt, etwas das für die Arbeit an Go relevant war, einer besseren Chance auf Akzeptanz und Annahme.

Diese Chance resultierte dann in etwas, das ich auswendig illustrieren möchte, fünf oder sechs Jahre, nachdem ich die letzte Go-Seite erstellt habe; man konnte ein HTML-Dokument wie folgt schreiben:

```html
<!DOCTYPE html>
<title>Google Test</title>
<meta charset=utf-8>
<link rel=stylesheet href=/css/go.css>
<h1><a href=/><img src=/logo alt=Google></a> Test</h1>
<p>Das ist nur ein Test [mit validem HTML].
```

Ebenso auswendig hervorgekramt, Go setzte dann so wenig Klassen und IDs wie möglich ein – und zwar die folgenden: [`.rtl`](https://meiert.com/en/blog/5-rtl-tips/), `.compact`, `#about`, `#nav` und `#aux`. Die Grundseitentypen waren ganze (aber dennoch limitierte) Breite, ganze Breite mit Navigation, kompakte (schmale) Seite und kompakte Seite mit Navigation. Die Zentrierung wurde durch die `.compact`-Klasse erzielt (auf `body`); das Hinzufügen einer Navigationsliste (`#nav`) erzeugte »automatisch« die Navigationsseitentypen; &c. Alle Seitentypen waren liquid und inhärent mobil-bereit. Das nur, um einen Eindruck von der Simplizität und Benutzerfreundlichkeit zu geben. (Als HTML&nbsp;5 noch weiter keimte und es noch keine [logischen Eigenschaften](https://www.w3.org/TR/css-logical-1/) in CSS gab, beruhte `#about` auf meiner [Präferenz gegenüber `#footer`](https://lists.w3.org/Archives/Public/public-html/2007Sep/0177.html), und `#nav` spiegelte das sich zu dem Zeitpunkt noch in Planung befindliche [`nav`-Element](https://html.spec.whatwg.org/multipage/semantics.html#the-nav-element) wider.)

Wie befriedigte Go dann die vielen Bedürfnisse, die in den Projekten mit unseren internen Kunden aufkamen? Wie auch schon durchscheinen mag: Go tat das nicht. Eines der Designziele war tatsächlich, dies gar nicht erst zu probieren. Go definierte den Kern von Googles Websites auf eine Weise, die so einfach wie möglich gehalten wurde, und erkannte die Einzigartigkeit und systemische Nicht-Managebarkeit all der unterschiedlichen Google-Sites durch zwei andere Entscheidungen an:

1. das Definieren anderer populärer Seitenelemente (wie Formulare) in einer Bibliothekserweiterung, »Go X« (man importierte in diesem Fall [go-x.css](https://www.google.com/css/go-x.css), was sehr wenig kognitive Zusatzbelastung bedeutete);

2. das Teilen der Verantwortung und das Überlassen von allem anderen an den Webentwickler, der an dem jeweiligen Projekt arbeitete (so dass diese Go oder Go X in ihrem [default.css](https://meiert.com/en/blog/stupidest-style-sheet-name/)-Projekt-Stylesheet importierten und ihr eigenes Ding machten).

Auf rasche Akzeptanz und Annahme hoffte ich nicht nur durch Benutzerfreundlichkeit – die Stylesheet-URL verinnerlichen und in ein einfaches HTML-Dokument mit Google-Logo packen –, sondern auch durch ein paar weitere Faktoren, die an [qualitätsverwandte Logistik](https://meiert.com/en/blog/quality-logistics/) erinnern:

* ein Template-Generator (da dies prä-CMS war, half er dem Team, konsistente Go-Vorlagen zu erstellen);
* eine Mailingliste für Ankündigungen, auf der das ganze Team vertreten war;
* eine Mailingliste für die Framework-Entwicklung;
* Dokumentation;
* improvisierte Videos ([Asim Janjua](https://twitter.com/asimjanj) und mir machten diese besondere Freude);
* [Code-Richtlinien](https://www.oreilly.com/library/view/the-little-book/9781492048459/), die die Verwendung steuerten.

Aus technischer Sicht halte ich Go für eines der elegantesten Dinge, die ich bisher entwickelt habe. Go war einfach, leicht, robust, erweiterbar, skalierbar und wartbar. Bis heute erscheint es basal und unspektakulär, und genau das war sehr sorgfältig überlegt und funktionierte außerordentlich gut. Fast ein Jahrzehnt später gibt es wenig, das ich ändern würde (ich würde neuere HTML- und CSS-Features einsetzen, um Go noch kompakter zu machen).

Bei alldem aber muss ich auch sagen, dass ich aus technischer und leitender Perspektive damit gescheitert war, größere Akzeptanz für Go zu finden. Ich hatte Fehler gemacht, andere erfahrene Entwickler im Team einzubeziehen und besser mit ihnen zusammenzuarbeiten. Ich hatte versäumt, Gos Vorteile näher zu erläutern und damit mehr Unterstützung in Team und Management zu gewinnen. Manche Reibung im Team und einige verlorene Zeit dabei, Go zum Standard zu machen, waren das Ergebnis davon. Ich musste lernen.

### Maia

Vorwärts. Eine der dringendsten Fragen, die ich mir 2012 stellen musste, war, wann wir ein neues Framework bauen würden. (Wann würden Sie?) In meinem Kopf war das Denken bislang zu _aktualisieren, iterieren_, [ohne Versionierung](https://meiert.com/en/blog/wdr-1/), weil Webdesign, ebenso Webentwicklung, [ein Prozess ist](https://meiert.com/en/blog/the-greatest-secret-in-web-design/) – und trotzdem wich ich das erste Mal von dieser Position ab. Warum?

Als wir – immer noch Googles Webmaster-Team – an einem neuen Design für alle informationsbezogenen Google-Sites arbeiteten, war absehbar, dass dies Konsequenzen für unseren Einsatz von Frameworks haben würde. Als Leiter des Projekts mutete dies für mich erst nach einem Update für Go an. Ich änderte diese Ansicht jedoch angesichts folgender Überlegungen:

* Die _Struktur_ unserer Anforderungen und unserer Seiten war dabei, sich stark zu ändern.
* Die _Komplexität_ unserer Seiten würde sich vergrößern.
* Es konnte nützlich und legitim sein, ein leichtes Framework (Go) als _Fallback_ in der Hinterhand zu haben.
* Ich wollte die Designphilosophie und Integrität von Go schützen, was sicher nicht meinen vertrauensvollsten und team-orientiertesten Schritt bedeutete (ich befürchtete, dass ich einen wichtigen Erfolg und Verantwortung verlieren würde).

Diese Punkte führten mich dazu, Bemühungen zu unterstützen und dann anzuführen, ein neues Google-Web-Framework zu entwickeln, ein Framework, dass ich »Maia« taufte (es ist ebenfalls [noch in Gebrauch](https://www.google.com/css/maia.css), obwohl ich nicht weiß, ob es gewartet und wie sehr es modifiziert wurde) – »Maia« wegen eines Faibles für griechische Mythologie: [Maia](https://de.wikipedia.org/wiki/Maia_(Tochter_des_Atlas)), Mutter von [Hermes](https://de.wikipedia.org/wiki/Hermes).

Die Geschichte von Maia ist anders als die von Go, insbesondere dadurch, dass Maia eine offiziell abgesegnete Teamunternehmung war, mit einem Team von fünf Webmastern, für deren Arbeit ich verantwortlich war. Der Prozess und die Organisation waren ähnlich zu dem, das ich in _The Little Book of HTML/CSS Frameworks_ beschreibe – angefangen bei der Motivation, eine zugeschnittene Lösung zu den eigenen (Design-)Problemen zu schaffen, über die Gründung eines Team, das über entsprechende Ziele und Werkzeuge verfügte, bis hin zur Kommunikation an eine nochmal größere Organisation. Ich glaube, dass _The Little Book of HTML/CSS Frameworks_ ein nützliches Buch ist, um mehr über solche Entwicklung zu erfahren, aber es folgen hier die Eckpfeiler für die Arbeit an Maia:

* das Definieren von Framework-Designzielen und -Entwicklungsprinzipien;
* das Zusammenstellen und Organisieren eines kleinen Teams von Entwicklern und Designern (mit den großartigen [Tony Ruscoe](http://ruscoe.net/) und [Zacky Ma](http://marchbox.com/));
* das Aufsetzen eines funktionierenden Prototypen, der auch alle Framework-Dokumentation beinhaltete (eine [wichtige und bewährte Vorgehensweise](https://meiert.com/de/publications/talks/20070523/));
* das Einrichten von Mailinglisten für Entwickler und Benutzer, für wichtige Ankündigungen.

Abgesehen von den komplexeren visuellen und technischen Anforderungen war die Entwicklung von Maia _als Team_ der größte Unterschied zur Arbeit an Go, und zusammen mit stärkerem Management-Support wohl der wesentliche Faktor dabei, weitreichende Akzeptanz zu gewährleisten und gar zu beschleunigen.

Es fällt auf, dass ich Maias Geschichte sehr knapp halte, sie gar abrupt beende; aber genau der Umstand, dass Maia Teamarbeit war, lässt es mich bevorzugen, hierüber – wenn das möglich wäre – _mit_ dem Team zu schreiben.

### Erkenntnisse

Das Geschilderte ist schon mit einigen Lektionen versehen, aber dies ist was ich betonen möchte.

1. Auch wenn ich das nicht direkt bei Google lernte – ich bin Idealist –, will ich es doch erwähnen, weil es mir wichtig erscheint: Nicht nur durch die Fokussierung und Segmentierung von Framework-Verantwortlichkeiten (wie bei Go und Go X getan) _ist es absolut möglich, zugeschnittene, effiziente und trotzdem benutzbare Frameworks zu bauen und zu warten_. (Das ist auch ein Kernpunkt in _The Little Book of HTML/CSS Frameworks_. Es gibt keinen Grund, unnötigen Code und schlechte Qualität hinzunehmen.)

2. Um eine hochwertige Lösung zu bauen, _ist Kommunikation wichtiger als Konsens_. Ich habe meine Probleme mit [Demokratie als Entscheidungswerkzeug](https://meiert.com/en/blog/teamwork-democracy-and-decisions/), da ich diese selten die beste Lösung erbringen sehe – und im Technischen gibt es oft so etwas wie ein »bestes«. Aber ich habe auch Probleme gehabt, als ich ein Team vernachlässigte, um einfach die Lösungen voranzutreiben, die nur ich für am besten erachtete. Eine Alternative ist, die beidseitige Kommunikation zu verbessern: dem Team zuhören, andere Experten aus dem Team involvieren, Unterstützung vom Management einholen, &c.

3. Dies kam gar nicht auf, als ich über Maia sprach, und ich widerspreche auch meinem vergangenen Selbst: _Es ist kritisch, zu vermeiden, ein zusätzliches Framework zu bauen._ Die [Vision](https://meiert.com/en/blog/vision-of-web-dev/) muss sein, zu iterieren und zu warten, [niemals »Fire and Forget«](https://meiert.com/de/publications/articles/20161116/). Ich hatte nichts großartig probiert, nicht gekämpft; ich hatte den Gewinn mitgenommen, den ich mit Go hatte, und dann den bequemen Weg beschritten, halbherzig ein kleines Team zu führen, um Konfrontation innerhalb der Organisation zu vermeiden (Unternehmenspolitik hatte dann auch mich erreicht, so scheint es). Das ist ein sehr anderer Schnack so plötzlich, aber ich hatte den wohl technisch inferioren Pfad genommen, als ich uns zugestand, an einem anderen Framework zu arbeiten, und damit einiges von dem geopfert, von dem wir zuvor so profitierten und was Go auszeichnete.

❧ Zum Abschluss wünsche ich, dass hier einige Dinge dabei sind, die für Ihre eigenen Framework-Entscheidungen nützlich sind, so dass Sie ernten können, was wir geerntet haben, ohne die Fehler zu machen, die ich gemacht habe. Selbst wenn ich diese lediglich anschnitt.

Mit herzlichen Wünschen an das alte Webmaster-Team. Die Arbeit mit euch allen war eine große Ehre und ein großes Vergnügen. Ich denke gerne daran zurück.