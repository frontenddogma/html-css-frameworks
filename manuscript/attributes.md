# Attribute guter Frameworks

Was ist denn nun ein »gutes« Framework? Was hat, oder was muss ein Framework haben, das wir benutzen wollen? Was macht ein Framework aus, das wir bauen wollen, oder bauen wollen würden? Ich habe mich damit lange beschäftigt, darüber nachgedacht, daran gearbeitet und mich dazu ausgetauscht.

In einem beruflichen und professionellen Zusammenhang bedeutet »gut« in erster Linie Qualität. Das lässt sich auch auf Frameworks anwenden. Ein Framework sollte, ganz besonders wenn es ein externes ist, das von anderen, vielleicht vielen anderen, benutzt wird, den höchsten Qualitätsstandards und -ansprüchen genügen.

Frameworks neigen dazu, eingesetzt zu werden, sobald ein Projekt eine bestimmte Größe und Komplexität erreicht hat (auch wenn das schon probiert wurde, braucht ein einzelnes Dokument kein Bootstrap oder YAML). Sie werden dann, Stichwort externe Frameworks, von Dritten entwickelt. Da Größe und Komplexität auch Probleme schwerer werden lassen, und da Dritte, wie wir gesehen haben, weder all unsere Bedürfnisse kennen noch besonders verlässlich sind, brauchen wir unbedingt ein paar Garantien und Sicherheiten.

Wir können uns eine solche Sicherheit beschaffen, indem wir den »Bloat«, das Fett, das besonders externe Frameworks mit sich bringen, loswerden. Wir wissen, was hier notwendig ist: Zuschneiden (_Tailoring_, oder _Customization_). Hiernach sollte ein gutes Framework ausdrücklich eins sein, das maßgeschneidert ist, dass auf unsere Bedürfnisse zugeschnitten wird (da es das nahezu nie ist, weil nicht sein kann).

Wenn wir nun von einem großen, komplexen Projekt ausgehen, arbeiten wir wahrscheinlich nicht allein mit oder an dem Framework; wenn es ein externes ist, wissen wir noch nicht einmal, ob die Entwickler des Frameworks unsere Sprache sprechen – buchstäblich und metaphorisch. Was hier hilft ist Usability, Benutzerfreundlichkeit. Ein gutes Framework sollte benutzerfreundlich sein.

Und schließlich verändern sich Anforderungen mit der Zeit: Wie arbeiten wir später mit dem Framework? Was passiert, wenn wir etwas ändern müssen? Oder wenn wir etwas hinzufügen müssen, vielleicht in Eile? Und was hier wichtig ist, ist Erweiterbarkeit, und so sollte ein Framework auch erweiterbar sein. Entweder wir haben eine genaue Vorstellung, wie wir unser Framework erweitern, oder das Framework selbst sollte davon eine klare Vorstellung (Dokumentation) haben.

Dieses Verlangen nach Qualität ist lediglich vernünftig und professionell. Wir können mehr Vertrauen in ein Framework haben, wenn es auf unsere Bedürfnisse maßgeschneidert, wenn es benutzerfreundlich und wenn es erweiterbar ist. Diese drei besonderen Attribute wollen wir uns nochmal näher anschauen und dabei die Optionen herausarbeiten, die Entwickler haben, Frameworks auch entsprechend zu bauen.

I> ### Über Qualität
I>
I> Es ist leicht, »Qualität« zu sagen oder »ja, will ich auch«. Aber was genau ist Qualität? Oder, nach dem bereits Behandelten, was ist Qualitäts-Code? Wenn wir etwas darüber nachdenken – vielleicht genau jetzt, ohne zu lesen – werden wir keine Mühen haben, mehr als nur die Ideale maßgeschneidert, benutzerfreundlich und erweiterbar zu finden. So gibt es auch:
I>
I> * schnell
I> * zugänglich/barrierefrei
I> * semantisch
I> * robust
I> * skalierbar
I> * dokumentiert
I> * wartbar
I> * valid
I> * selbsterklärend
I> * konsistent
I> * »automagisch«
I> * »State of the Art«
I> * einfach
I> * kompakt
I> * flexibel
I> * getestet
I> * fehlertolerant
I> * selbstkorrigierend
I> * und mehr
I> 
I> Und dies umfasst noch nicht mal irgendwelche emotionalen Eigenschaften, die man mit Qualität in Verbindung bringen könnte, wie »angenehm« oder vielleicht »unterhaltsam«. Qualität hat aber viele Facetten. 

## 1. Ein Framework sollte maßgeschneidert sein

Wir haben Maßschneidern als »Produzieren und Anpassen auf genaue Maße und Bedürfnisse« definiert. »Produzieren« bezieht sich auf die Entwicklung eines Frameworks, egal ob intern oder extern, während es beim »Anpassen« gemeinhin um die Taillierung eines _externen_ Frameworks geht. Der Schlüssel hierbei sind »genaue Maße und Bedürfnisse«. Wir müssen unsere Bedürfnisse und unseren Bedarf kennen – sonst können wir nichts produzieren oder anpassen, das diesen entspricht.

Ein Blickwinkel auf maßgeschneiderten Code ist es, benötigten mit eingesetztem Code zu vergleichen. Da die blanken Zahlen für Zeichen oder Zeilen an Code dafür nicht herangezogen werden können, ist dies sehr schwer festzustellen, aber konzeptionell bedeutet zugeschnittener Code hier ein möglichst hohes Verhältnis, um so wenig Code wie möglich so effektiv wie möglich einzusetzen.

Was kann getan werden, um maßzuschneidern? Der Ansatz hängt stark vom Ursprung des Frameworks ab.

Ein internes Framework ist recht einfach, zuzuschneiden: Wir entwickeln von Anfang an direkt auf unsere Bedürfnisse hin. Diese Bedürfnisse mögen durch Comps und Mocks (umfassende Layouts), einen Styleguide oder ein Designsystem definiert werden. Sobald die benötigten Seitentypen und -elemente spezifiziert wurden, werden sie entwickelt – hier egal, ob komponentenbasiert oder monolithisch. Wenn all dieser Code auch von der späteren Site oder App verwendet wird, kann der Code kaum anders als maßgeschneidert sein (obwohl er wahrscheinlich noch optimiert und komprimiert werden kann). 

Bei einem externen Framework sieht die Sache jedoch anders aus – es ist wesentlich schwieriger, dies auf Maß zu kriegen, beim Empfänger, da der Erschaffer dies gar nicht für dessen exakten Bedarf zu entwickeln vermochte. Vereinfacht ausgedrückt müssten wir von der angebotenen Funktionalität alle nicht benötigte abziehen und den entsprechenden Code abziehen und ausbauen. Das führt uns zu den Hauptproblemen mit externen Frameworks: Es kann unmöglich sein, Code zu entfernen (dies funktioniert selbst bei modularisierten Frameworks oft nicht rückstandsfrei), und alles Zuschneiden hängt dann von der Quantität (der Menge an Code), Qualität und Dokumentation des Frameworks ab. Alle möglichen Anpassungen erfordern dann besondere Sorgfalt und Tests, können das Framework im schlimmsten Falle kaputt machen und selbst wenn alles funktioniert, wird bei jedem Framework-Update wieder Arbeit fällig, mit wieder neuen Risiken, sofern man nicht aufgibt und entweder nichts anpasst (schlecht für die Qualität) oder keine Framework-Aktualisierungen mitgeht (ebenso schlecht für die Qualität). 

Dies sind große Hindernisse, die genau der Grund sind, warum wenige Leute tatsächlich so weit gehen, ein externes Framework (oder überhaupt irgendwelchen Code von Dritten) anzupassen oder zuzuschneiden. Und sie bilden einen guten Grund. Das Ergebnis jedoch – nicht zugeschnittener und damit Code von niedrigerer Qualität – ist weder fachmännisch noch hochwertig. Und auch wenn dies weiterhin unterstellt, dass wir überhaupt alle an hochwertigem Code interessiert sind, sollte es zeigen, wenn diese Unterstellung wahr ist, externe Frameworks nicht zu wählen sind. Sie versprechen, Kosten zu sparen, nur um mittel- und langfristig eine ziemlich hohe Steuer einzutreiben (dadurch, dass wir Arbeiten an ihnen durchführen müssen) – oder sonst die Qualität unserer Projekte herunterziehen.

Manche Frameworks wie Bootstrap (und Bootstrap vielleicht noch am meisten) gehen diese Probleme an, indem sie umfangreiche und durchdachte Konfigurations-Wizards und -Optionen anbieten. Dies ist klug, denn genau so kann den Nachteilen nicht zugeschnittener Lösungen begegnet werden. Frameworks-Entwickler sollten – müssen – solche Funktionen bieten und Nutzer diese nutzen, auch wenn sie sowohl Entwicklung als auch Einarbeitung komplexer machen. (Das ist möglicherweise auch gleich der Grund, warum es immer noch viele Frameworks gibt, die nicht konfigurierbar sind, und qualitätsseitig weiter Warnungen gegeben werden müssen.)

Nebenbei bemerkt müssen wir noch ein anderes Problem berücksichtigen: Während es wir selbst in jedem Fall von der Entscheidung profitieren, ob mit einem Framework Zeit und Geld gespart oder hohe Qualität erreicht werden soll, gewinnen unsere Nutzer nur dann, wenn die Entscheidung auf Qualität fällt. Sie haben selten etwas davon, wenn wir uns einfach für ein Framework entscheiden, dass zwar leicht aufzusetzen ist, aber mit Tonnen an ungenutztem Ballast kommt.

Um interne Frameworks maßzuschneidern sollte man:

* die Projektbedürfnisse und -ziele genau kennen;
* das Framework genau auf diese Bedürfnisse hin entwickeln. 

Um externe Frameworks maßzuschneidern sollte man:

* die Projektbedürfnisse und -ziele genau kennen;
* das Framework genau auf diese Bedürfnisse hin anpassen – oder, wenn man vom Ziel höchster Qualität kommt, vom Framework Abstand nehmen.

## 2. Ein Framework sollte benutzerfreundlich sein

Ein gutes Framework ist nicht nur maßgeschneidert, sondern auch benutzerfreundlich. Was heißt aber Benutzerfreundlichkeit, oder Benutzbarkeit, oder, um beim Englischen zu bleiben, Usability bei Frameworks? Sie beginnt mit der Anwendung der [üblichen Definition](https://en.wikipedia.org/wiki/Usability): leichte Bedien- und Erlernbarkeit. Und mit einer universellen Regel: Einfachheit (_Keep It Simple_). Einfachheit hilft bei fast allem. 

Das kann aber noch nicht die vollständige Antwort sein, denn es muss weiter differenziert werden. Was uns hier hilft ist nicht die Unterscheidung zwischen Frameworks, sondern Rollen: die zwischen Framework-Benutzern und -Entwicklern.

Für den Framework-Benutzer (der auch ein Entwickler sein kann, aber hier mit dem _Gebrauch_ eines Frameworks beschäftigt ist) ist ein benutzerfreundliches Framework eins, das leicht zu verwenden und verstehen ist. Dieses Verständnis wird primär durch klare und umfassende Framework-Dokumentation erreicht sowie, wenn nötig (z.B. zur Integration oder Einbettung), nachvollziehbaren Code. 

Für den Framework-Entwickler liegt wesentlich stärkere Betonung auf benutzbarem Code. Es gibt hier vor allem zwei Dinge, die der Benutzerfreundlichkeit von Code dienen: die Befolgung von »[Best](https://meiert.com/en/blog/maintainability-guide/) [Practices](https://meiert.com/en/blog/maintainability-guide-2/)« zu Wartbarkeit sowie [Code-Konventionen und -Richtlinien](https://www.oreilly.com/library/view/the-little-book/9781492048459/). Einfache Wartbarkeit und konsistenter Stil, was sprechenden und kommentierten Code einschließt, bilden das Rückgrat benutzerfreundlichen Codes.

Dem Thema [_Developer Experience_ (DX)](https://hackernoon.com/developer-experience-dx-devs-are-people-too-6590d6577afe) zugehörig gibt es noch einen weiteren Bereich unterhalb von Benutzerfreundlichkeit, nämlich: Benutzerfreundlichkeit für Entwickler, oder _Developer Usability_. Dieser Bereich könnte mit »leichter Bedien- und Erlernbarkeit von Code« beschrieben werden. Vielleicht erhält er nicht soviel Aufmerksamkeit, weil benutzerfreundlicher Code oft unter anderen Namen propagiert und eingefordert wird, aber wie wir sehen, könnte er vielleicht davon profitieren, separat ausgezeichnet zu werden.

Um Frameworks für Nutzer benutzerfreundlicher zu machen sollte man:

* es einfach halten;
* Usability-Konventionen folgen;
* Usability-Tests durchführen;
* verständliche und ausreichende Dokumentation bieten.

Um Frameworks für Entwickler benutzerfreundlicher zu machen sollte man:

* es einfach halten;
* selbsterklärenden Code anstreben;
* Code lesbar und konsistent formatieren;
* »Best Practices« für Wartbarkeit folgen;
* Dokumentation speziell für Framework-Entwickler bieten.

### 3. Ein Framework sollte erweiterbar sein

Das letzte zu betonende Attribut ist Erweiterbarkeit. Erweiterbarkeit bedeutet bei Frameworks, dass es nicht nur möglich, sondern gut definiert und einfach ist, es zu erweitern oder ergänzen – nicht inhärent im Sinne eines neuen Framework-Bestandteils, sondern als sich wie ein solcher Teil anfühlende Ergänzung. 

Erweiterbarkeit ist aus zwei Gründen notwendig. Zum einen bieten vor allem externe Framework nicht alles, was wir brauchen – das haben wir schon als Kernproblem festgehalten –, und so muss es einen Weg geben, neue Features zu ergänzen. Zum anderen, und dies bezieht sich nun eher auf große Projekte, wird es grundsätzlich immer Bedarf nach neuen Funktionen und Patterns geben – und das Problem damit ist deren Einzigartig- und auch Flüchtigkeit: Manche Funktionen mögen nur ein- oder zweimal verwendet werden und rechtfertigen damit keine Nähe zum Framework-Kern, oder noch nicht mal zu Erweiterungen. Sowohl der Ort als auch Handhabung solcher Elemente muss bedacht werden.

Um fehlende Funktionalität abzubilden, behelfen sich Frameworks-Entwickler oft, indem sie das Framework quasi ignorieren und einfach ein Stylesheet oder Skript einhängen, das das abdeckt, was das Framework nicht beherrscht. Das ist tatsächlich in Ordnung – der Punkt der Erweiterbarkeit dreht sich hier eher darum, dass das Framework _zumindest einen Mechanismus oder wenigstens Dokumentation beinhaltet_, wie »Nicht-Framework-Funktionalität« und damit Erweiterungen behandelt werden sollen. Das Minimum, was technisch berücksichtigt werden sollte, ist der basischste aller Code-Schutzmechanismen: ein Namensraum, also ein framework-spezifisches ID- oder Klassen-Präfix (`#framework-`, `.framework-`), und selbiges in JavaScript. In den vergangenen Jahren hat sich der Trend zwar stark von solchen Namensräumen fortentwickelt, aber die Gründe für die Entwicklung – das halbtote [OOCSS](http://oocss.org/), das beliebte [BEM](http://getbem.com/), dazu [HTML-»Harakiri«](https://meiert.com/de/publications/articles/20091027/) wie [Atomic CSS](https://acss.io/) oder [Tachyons](http://tachyons.io/) – stehen auf genauso tönernen Füßen wie die in den meisten öffentlichen Frameworks noch immer verbreitete Praxis, kein Präfix zu verwenden und damit Styling-Kollisionen nicht nur zu riskieren, sondern zu erbetteln.

Neue und selten benutzte Funktionen stellen eine Herausforderung dar, die gewissermaßen in den besten Familien auftritt. Es gibt irgendwie immer Bedarf nach etwas Neuem, und es gibt auch immer irgendwelche Seitentypen und -elemente, die selten verwendet werden. Dies sind zwei der Hauptgründe für krebsartig wachsenden Code, und sie sind schwer zu kontrollieren, wenn sie nicht streng beobachtet und eingefangen werden. Da wir es mit einem kleinen Buch zu tun haben, eine bewährte Gegenmaßnahme ist es, spezielle Stylesheet- und Skript-Abschnitte vorzusehen und auszuzeichnen, in denen neuer, vor allem aber experimenteller und vorerst selten eingesetzter Code landet. (Ein separates Stylesheet und Skript kann ebenfalls für solche Zwecke bereitgestellt werden.) Frameworks-Entwickler sollten entsprechend versuchen, zu antizipieren, ob Code oder vielmehr die entsprechenden Funktionen vielleicht erstmal selten gebraucht werden, um diese so in »Quarantäne« zu stecken; Frameworks-Nutzer, die, die nicht aktiv daran entwickeln, sollten durchaus aber auch Vermerke für alles vornehmen, was nur in Sonderfällen mal zum Einsatz kommt. Ein dokumentierter Standard für eine solche Quarantäne kann effektivere Kontrolle und damit bessere Entscheidungen ermöglichen, ob Code behalten, umgezogen – oder entfernt wird. 

Das Prinzip war sehr erfolgreich mit Google HTML-/CSS-Framework »Go« – nicht zu verwechseln mit der erst später entwickelten Programmiersprache. Go verfügte über ein »Rucksack«-Stylesheet, Go X, das alle Elemente beinhaltete, die nur selten verwendet wurden. Dies erlaubte, den Kern des Frameworks äußerst klein zu halten ([etwa 4&nbsp;KB](https://www.google.com/css/go.css), einschließlich des Google-Logos), aber es trotzdem zu ermöglichen, schnell weitere Funktionen einzubinden. Projektspezifischer Code, gewissermaßen die dritte Stufe nach dem Go-Kern und der Go-X-Bibliothek, musste dann separat eingebunden werden, was dokumentiert war – wie in diesem Kapitel so sehr empfohlen – aber dann Verantwortung jedes Google-Projekts selbst war. Am Ende dieses Buches finden Sie ein paar weitere Details zu den Prinzipien hinter dem Go-Framework; was an dieser Stelle zu ergänzen ist, ist dass dies heute dank verstärkt komponentenbasierter Arbeit sowie weiterer Tooling-Optionen, die eine Art »CSS-Tree-Shaking« ermöglichen, eher _eine_ Option darstellt, mit selten benötigtem Code umzugehen.

Um Frameworks erweiterbar zu machen sollte man:

* einen Namensraum in Erwägung ziehen;
* die Handhabung von Nicht-Framework-Code explizit berücksichtigen und definieren;
* spezifizieren, wo neuer und selten gebrauchter Code landen sollte;
* neuen und selten gebrauchten Code regelmäßig überprüfen, um ihn entweder näher am oder im Framework zu verorten oder zu entfernen.

I> Beachten Sie, dass ich diese Regeln trotz meiner Erfahrung und Überzeugungen eher als »starke Empfehlungen« ausgedrückt habe. Ich war ehemals versucht, »müssen«, »müssen«, »müssen« zu schreiben. Wann auch immer wir mehr Dogma in unserem Entwicklerleben wünschen, benutzen wir dieses Verb. Letztendlich aber haben große Teile dieses Buchs ihren Ursprung noch in der Webentwicklungswelt von vor etwa fünf Jahren (weitere Aktualisierungen sollten das Buch weiter nach vorne schieben), und gibt es nicht nur neuere Tooling-Optionen, sondern auch andere Schulen und Philosophien – Philosophien, die dank z.B. Tree-Shaking gar nichts verwerfliches entdecken können, wenn in irgendeiner Ecke Code liegt, der nicht verwendet wird. Das muss man eigentlich sezieren und sich näher anschauen, und genau das macht dieses Buch noch nicht.  
I>
I> Ein letzter Punkt: Egal wie es um die Qualität eines Frameworks beschaffen ist, seine Einsatzziele kennen nur seine Nutzer, diejenigen die ein Framework für ein bestimmtes Projekt wählen und einsetzen. Frameworks sind dann vielleicht ein bisschen wie Autos: Ein gutes Auto sollte, sagen wir mal, sicher, leicht handhabbar und ökonomisch sein. Vergleichbar wie man sagen kann, dass ein gutes Framework maßgeschneidert, benutzerfreundlich und erweiterbar sein sollte. Der Autobauer und der Frameworks-Entwickler können hier Qualität abliefern. Aber genauso wie es dann auf die Fahrer ankommt, zu sagen, wo sie mit ihren Autos denn hin wollen, kommt es letztlich auf die Framework-Nutzer an, das Fahrtziel ihres Frameworks festzulegen. Wir können Frameworks genauso an die Wand fahren wie Autos. Egal, wie gut sie sind.