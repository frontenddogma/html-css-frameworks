# Attribute guter Frameworks

Was ist denn nun ein »gutes« Framework? Was hat, oder was muss ein Framework haben, das wir benutzen wollen? Was macht ein Framework aus, das wir bauen wollen, oder bauen wollen würden? Ich habe mich lange damit beschäftigt, darüber nachgedacht, daran gearbeitet und dazu ausgetauscht.

In einem beruflichen und professionellen Zusammenhang bedeutet »gut« in erster Linie Qualität. Das lässt sich auch auf Frameworks anwenden. Ein Framework sollte, ganz besonders wenn es ein externes ist, das von anderen, vielleicht vielen anderen, benutzt wird, den höchsten Qualitätsstandards und -ansprüchen genügen. (Diese Normativität ist natürlich subjektiv, man muss sie nicht mögen oder ihr unbedingt zustimmen.)

Frameworks neigen dazu, eingesetzt zu werden, sobald ein Projekt eine bestimmte Größe und Komplexität erreicht hat. (Auch wenn manche das schon probiert haben, braucht ein einzelnes Dokument kein Bootstrap oder YAML.) Externe Frameworks werden dazu von Dritten entwickelt. Da Größe und Komplexität auch Probleme wachsen lassen, und da Dritte, wie wir gesehen haben, weder all unsere Bedürfnisse kennen noch notwendigerweise verlässlich sind, brauchen wir ein paar Garantien und Sicherheiten, wenn wir ein Framework einsetzen wollen.

Wir können uns eine solche Sicherheit beschaffen, indem wir den »Bloat«, das Fett, das besonders externe Frameworks mit sich bringen, loswerden. Wir wissen, was hier notwendig ist: Zuschneiden (_Tailoring_, oder _Customization_). Hiernach sollte ein gutes Framework ausdrücklich eins sein, das maßgeschneidert ist, das auf unsere Bedürfnisse zugeschnitten ist.

Wenn wir nun von einem großen, komplexen Projekt ausgehen, arbeiten wir wahrscheinlich nicht allein mit oder an dem Framework; wenn es ein externes ist, wissen wir noch nicht einmal, ob die Entwickler des Frameworks unsere Sprache sprechen – metaphorisch und buchstäblich. Was in beiden Fällen hilft ist Usability, Benutzerfreundlichkeit. Ein gutes Framework sollte benutzerfreundlich sein, so dass es einfach für uns und unsere Teams ist, damit zu arbeiten.

Dann verändern sich Anforderungen mit der Zeit: Wie arbeiten wir später mit dem Framework? Was passiert, wenn wir etwas ändern müssen? Oder wenn wir etwas hinzufügen müssen, vielleicht in Eile? Und was hierzu wichtig ist, ist Erweiterbarkeit, und so sollte ein Framework auch erweiterbar sein. Entweder haben wir eine genaue Vorstellung, wie wir unser Framework erweitern, oder das Framework selbst sollte davon eine klare Vorstellung (Dokumentation) haben.

Das Verlangen nach Qualität ist lediglich vernünftig und professionell. Wir können mehr Vertrauen in ein Framework haben, wenn es auf unsere Bedürfnisse zugeschnitten, wenn es benutzerfreundlich und wenn es erweiterbar ist. Diese drei besonderen Attribute wollen wir uns näher anschauen und dabei die Optionen herausarbeiten, die Entwickler haben, Frameworks auch entsprechend zu bauen.

I> ### Über Qualität
I>
I> Es ist leicht, »Qualität« zu sagen und »ja, will ich auch«. Aber was genau ist Qualität? Oder, nach dem bereits Behandelten, was ist Code von Qualität? Wenn wir darüber nachdenken – vielleicht genau jetzt, ohne weiterzulesen – werden wir keine Mühen haben, mehr als nur die Ideale »maßgeschneidert«, »benutzerfreundlich« und »erweiterbar« zu finden. So gibt es auch:
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
I> * »State of the Art«
I> * einfach
I> * kompakt
I> * flexibel
I> * getestet
I> * fehlertolerant
I> * selbstkorrigierend
I> * »automagisch«
I>
I> … und dies umfasst noch nicht mal irgendwelche emotionalen Eigenschaften, die man noch mit Qualität in Verbindung bringen könnte, wie »angenehm« oder vielleicht »unterhaltsam«. Qualität hat viele Facetten.

## 1. Ein Framework sollte maßgeschneidert sein

Wir haben Maßschneidern als »Produzieren und Anpassen auf genaue Maße und Bedürfnisse« definiert. »Produzieren« bezieht sich auf die Entwicklung eines Frameworks, egal ob intern oder extern, während es beim »Anpassen« gemeinhin um die Taillierung eines _externen_ Frameworks geht. Der Schlüssel sind »genaue Maße und Bedürfnisse«. Wir müssen unseren Bedarf und unsere Bedürfnisse kennen – sonst können wir nichts produzieren oder so anpassen, dass es diesen entspricht.

Ein Blickwinkel auf maßgeschneiderten Code ist, benötigten mit eingesetztem Code zu vergleichen. Da die blanken Zahlen für Zeichen oder Zeilen an Code dafür nicht herangezogen werden können, ist dies schwer zu determinieren, aber konzeptionell bedeutet zugeschnittener Code so wenig Code wie nötig, der so effektiv wie möglich ist.

Was muss zum Maßschneidern getan werden? Die Antwort hängt vom Ursprung des Frameworks ab.

Ein internes Framework ist recht einfach zuzuschneiden: Wir entwickeln von Anfang an direkt auf unsere Bedürfnisse hin. Diese Bedürfnisse mögen durch Comps und Mocks (umfassende Layouts), einen Styleguide oder ein Designsystem definiert werden. Sobald die benötigten Seitentypen und -elemente spezifiziert wurden, werden sie entwickelt – an dieser Stelle unerheblich, ob monolithisch oder komponentenbasiert. Wenn all dieser Code auch von der späteren Site oder App verwendet wird, kann der Code funktional kaum anders als maßgeschneidert sein (obwohl er vielleicht noch optimiert und komprimiert werden kann).

Bei einem externen Framework sieht die Sache jedoch anders aus – es ist sowohl notwendiger als auch schwieriger, dies vom Nutzer (nicht zu verwechseln mit Endnutzer, die in diesem Buch entsprechend gekennzeichnet werden) auf Maß zu trimmen, da der Erschaffer gar nicht für dessen exakten Bedarf entwickelt hat. Vereinfacht ausgedrückt müssten wir von der angebotenen Funktionalität alle nicht benötigte abziehen und den entsprechenden Code ausbauen. Das führt uns zu den Hauptproblemen mit externen Frameworks: Es kann unmöglich sein, Code zu entfernen (dies funktioniert selbst bei modularisierten Frameworks und mit diversem Tree-Shaking oft nicht rückstandsfrei), und alles Zuschneiden hängt dann von der Quantität (der Menge an Code), Qualität und Dokumentation des Frameworks ab. Alle möglichen Anpassungen erfordern dann besondere Sorgfalt und Tests, können das Framework im schlimmsten Falle kaputt machen und selbst wenn alles funktioniert, wird bei jedem Framework-Update wieder Arbeit fällig, mit wieder neuen Risiken, sofern man nicht aufgibt und entweder nichts anpasst (schlecht für die Qualität – zurück auf »Los«) oder keine Framework-Aktualisierungen mitgeht (ebenfalls schlecht für die Qualität).

Dies sind große Hindernisse, die genau der – und ein guter – Grund sind, warum wenige Leute tatsächlich so weit gehen, ein externes Framework (oder überhaupt irgendwelchen Code von Dritten) anzupassen oder zuzuschneiden. Das Ergebnis – nicht zugeschnittener und damit Code von niedrigerer Qualität – ist jedoch weder fachmännisch noch hochwertig. Und auch wenn dies weiterhin unterstellt, dass wir überhaupt an hochwertigem Code _interessiert_ sind, sollte es zeigen, dass externe Frameworks eigentlich nicht zu verwenden sind. Sie versprechen, Kosten zu sparen, nur um mittel- und langfristig eine ziemlich hohe Steuer zu erheben (dadurch, dass wir Arbeiten an ihnen durchführen müssen) – oder die Qualität unserer Projekte herunterzuziehen.

Manche Frameworks wie Bootstrap (und Bootstrap vielleicht noch am meisten) gehen diese Probleme an, indem sie umfangreiche und durchdachte Konfigurations-Wizards und -Optionen anbieten. Dies ist klug, denn so kann den Nachteilen nicht zugeschnittener Lösungen begegnet werden. Frameworks-Entwickler sollten – müssen – solche Funktionen bieten und Nutzer diese nutzen, auch wenn sie sowohl Entwicklung als auch Einarbeitung komplizierter machen. (Das ist möglicherweise auch gleich der Grund, warum es immer noch viele Frameworks gibt, die nicht konfigurierbar sind, und für die wie hier qualitätsseitig weiter Warnungen ausgegeben werden müssen.)

Nebenbei bemerkt müssen wir noch ein anderes Problem berücksichtigen: Während wir selbst in jedem Fall von der Entscheidung profitieren, ob mit einem Framework Zeit und Geld gespart (kein Maßschneidern) oder hohe Qualität erreicht werden soll (Maßschneidern), gewinnen unsere _Endnutzer_ nur dann, wenn die Entscheidung auf Qualität fällt. Sie haben selten etwas davon, wenn wir uns einfach für ein Framework entscheiden, das zwar leicht aufzusetzen ist, aber mit Tonnen an ungenutztem Ballast daherkommt.

Um ein internes Framework maßzuschneidern sollte man:

* die Projektbedürfnisse und -ziele genau kennen;
* das Framework genau auf diese Bedürfnisse hin entwickeln.

Um ein extern Framework maßzuschneidern sollte man:

* die Projektbedürfnisse und -ziele genau kennen;
* das Framework genau auf diese Bedürfnisse hin anpassen – oder, vom Ziel höchster Qualität ausgehend, vom Framework Abstand nehmen.

## 2. Ein Framework sollte benutzerfreundlich sein

Ein gutes Framework ist nicht nur maßgeschneidert, sondern auch benutzerfreundlich. Was heißt Benutzerfreundlichkeit, oder Benutzbarkeit, oder, um beim Englischen zu bleiben, _Usability_ bei Frameworks? Sie beginnt mit der Anwendung der [üblichen Definition](https://en.wikipedia.org/wiki/Usability): leichte Bedien- und Erlernbarkeit. Und aus meiner Sicht mit einer universellen Regel: Einfachheit (_Keep It Simple_). Einfachheit hilft bei fast allem.

Das kann aber noch nicht die vollständige Antwort sein, denn es muss weiter differenziert werden. Was uns hilft ist nicht die Unterscheidung zwischen Frameworks, sondern Rollen: die zwischen Framework-Benutzern und -Entwicklern.

Für den Framework-Benutzer (kein Endnutzer, aber jemand, der auch ein Entwickler sein kann, der mit dem _Gebrauch_ eines Frameworks beschäftigt ist) ist ein benutzerfreundliches Framework eins, das leicht zu verstehen und verwenden ist. Dieses Verständnis wird primär durch klare und umfassende Framework-Dokumentation erreicht sowie, wenn nötig (z.B. zur Integration oder Einbettung), nachvollziehbaren Code.

Für den Framework-Entwickler liegt wesentlich stärkere Betonung auf benutzbarem Code. Es gibt hier vor allem zwei Dinge, die der Benutzerfreundlichkeit von Code dienen: die Befolgung von »[Best](https://meiert.com/de/publications/articles/20090907/) [Practices](https://meiert.com/de/publications/articles/20180405/)« zu Wartbarkeit sowie [Code-Konventionen und -Richtlinien](https://www.oreilly.com/library/view/the-little-book/9781492048459/). Einfache Wartbarkeit und konsistenter Stil, was kommentierten und sprechenden Code einschließt, bilden das Rückgrat benutzerfreundlichen Codes.

Dem Thema [_Developer Experience_ (DX)](https://hackernoon.com/developer-experience-dx-devs-are-people-too-6590d6577afe) zugehörig gibt es noch einen weiteren Bereich unterhalb von Benutzerfreundlichkeit, nämlich: Benutzerfreundlichkeit für Entwickler, oder _Developer Usability_. Dieser Bereich könnte mit »leichter Bedien- und Erlernbarkeit von Code« beschrieben werden. Vielleicht erhält er nicht so viel Aufmerksamkeit, weil benutzerfreundlicher Code oft unter anderen Namen propagiert und eingefordert wird, aber wie wir sehen, könnte er vielleicht davon profitieren, separat ausgezeichnet zu werden.

Um ein Framework für dessen Nutzer benutzerfreundlicher zu machen sollte man:

* es einfach halten;
* Usability-Konventionen folgen;
* Usability-Tests durchführen;
* verständliche und ausreichende Dokumentation bieten.

Um ein Framework für Entwickler benutzerfreundlicher zu machen sollte man:

* es einfach halten;
* selbsterklärenden Code anstreben;
* Code lesbar und konsistent formatieren;
* »Best Practices« für Wartbarkeit befolgen;
* Dokumentation speziell für Framework-Entwickler bieten.

## 3. Ein Framework sollte erweiterbar sein

Das letzte zu betonende Attribut guter Frameworks ist Erweiterbarkeit. Erweiterbarkeit bei Frameworks bedeutet, dass es nicht nur möglich, sondern gut definiert und sogar leicht ist, zu erweitern oder ergänzen – nicht inhärent im Sinne eines neuen Framework-Bestandteils, sondern als sich wie ein solcher Bestandteil anfühlende Ergänzung.

Erweiterbarkeit ist aus zwei Gründen notwendig. Zum einen bieten vor allem externe Frameworks nicht alles, was wir brauchen – das haben wir schon als Kernproblem festgehalten –, und so muss es einen Weg geben, neue Features zu ergänzen. Zum anderen, und dies bezieht sich nun eher auf große Projekte, wird es grundsätzlich immer Bedarf nach neuen Funktionen und Patterns geben – und das Problem mit diesen ist deren Einzigartig- und auch Flüchtigkeit: Manche Funktionen mögen nur ein- oder zweimal verwendet werden und rechtfertigen damit keine (code-seitige) Nähe zum Framework-Kern, noch nicht mal zu Erweiterungen. Sowohl der Ort als auch die Handhabung solcher Elemente muss bedacht werden.

Um fehlende Funktionalität abzubilden, behelfen sich mit Frameworks arbeitende Entwickler oft, indem sie das Framework quasi ignorieren und einfach ein Stylesheet oder Skript einhängen, das das abdeckt, was das Framework nicht beherrscht. Das ist tatsächlich in Ordnung – der Punkt der Erweiterbarkeit dreht sich hier eher darum, dass das Framework _zumindest einen Mechanismus oder wenigstens Dokumentation beinhaltet_, wie »Nicht-Framework-Funktionalität« und damit Erweiterungen behandelt werden sollten.

Das Minimum, das technisch für das Framework selbst vorgesehen werden sollte, ist der basischste aller Code-Schutzmechanismen: ein Namensraum, also ein framework-spezifisches ID- oder Klassen-Präfix (`#framework-`, `.framework-`), und selbiges in JavaScript. In den vergangenen Jahren hat sich der Trend zwar stark von solchen Namensräumen fortentwickelt, aber die Gründe für die Entwicklung – das halbtote [OOCSS](https://web.archive.org/web/20090625191515/http://oocss.org/), das beliebte [BEM](http://getbem.com/), dazu [HTML-»Harakiri«](https://meiert.com/de/publications/articles/20091027/) wie [Atomic CSS](https://acss.io/) oder [Tachyons](http://tachyons.io/) – stehen auf genauso tönernen Füßen wie die in den meisten öffentlichen Frameworks noch immer verbreitete Praxis, kein Präfix zu verwenden und damit Styling-Kollisionen nicht nur zu riskieren, sondern zu erbetteln. (Dies wollte ich einfach stehenlassen, auch wenn in der jüngeren komponentenbasierten Entwicklung mit [»gescopeten« Styles](https://vuejs.org/v2/guide/comparison.html#Component-Scoped-CSS) die Gefahr von Kollisionen äußerst gering ist.)

Neue und selten benutzte Funktionen stellen eine Herausforderung dar, die gewissermaßen in den besten Familien auftritt. Es gibt immer Bedarf nach etwas Neuem, und es gibt auch immer Seitentypen und -elemente, die selten verwendet werden. Dies sind zwei der Hauptgründe für krebsartig wachsenden Code, und dieser ist schwer zu kontrollieren, wenn er nicht streng beobachtet und zeitnah eingefangen wird. Eine bewährte Gegenmaßnahme ist es, spezielle Stylesheet- und Skript-Abschnitte vorzusehen und auszuzeichnen, in denen neuer, vor allem aber experimenteller und vorerst selten eingesetzter Code landet. (Ein separates Stylesheet und Skript kann ebenfalls für solche Zwecke bereitgestellt werden – selbst etwas wie »experimental.css« kann Wunder wirken, da hier nicht alles, was sich erst noch bewähren muss, sofort in der Masse des strikt notwendigen Codes untergeht und technische Schulden aufgebaut werden.)

Frameworks-Entwickler sollten entsprechend versuchen, zu antizipieren, ob Code oder vielmehr die entsprechenden Funktionen erstmal selten gebraucht werden, um diese (und bei einem Komponentenansatz auch entsprechende Komponenten) in »Quarantäne« zu stecken. Frameworks-Nutzer wiederum können Vermerke für alles vornehmen, was nur in Sonderfällen mal zum Einsatz kommt. Ein dokumentierter Standard für eine solche Quarantäne kann effektivere Kontrolle und damit bessere Entscheidungen ermöglichen, ob Code behalten, umgezogen – oder entfernt wird.

Dieses Prinzip war sehr erfolgreich bei Googles HTML-/CSS-Framework »Go« (nicht zu verwechseln mit der erst später entwickelten Programmiersprache). Go verfügte über ein »Rucksack«-Stylesheet, Go X, das alle Elemente beinhaltete, die nur selten verwendet wurden. Dies erlaubte, den Kern des Frameworks äußerst klein zu halten ([etwa 4 KB](https://www.google.com/css/go.css), einschließlich des Google-Logos), aber auch, schnell weitere Funktionen einzubinden. Projektspezifischer Code, gewissermaßen die dritte Stufe nach Go-Kern und Go-X-Bibliothek, musste separat eingebunden werden, was dokumentiert – wie in diesem Kapitel empfohlen – aber dann Verantwortung jedes Google-Projekts selbst war. Am Ende dieses Buchs finden Sie ein paar weitere Details zu den Prinzipien hinter dem Go-Framework; was an dieser Stelle zu ergänzen ist, ist dass dies heute dank verstärkt komponentenbasierter Arbeit sowie weiterer Tooling-Optionen, die eine Art »CSS-Tree-Shaking« ermöglichen, eher _eine_ Option darstellt, mit selten benötigtem Code umzugehen.

Um ein Framework erweiterbar zu machen sollte man:

* einen Namensraum in Erwägung ziehen;
* die Handhabung von Nicht-Framework-Code explizit berücksichtigen und definieren;
* spezifizieren, wo neuer und selten gebrauchter Code landen sollte;
* neuen und selten gebrauchten Code regelmäßig überprüfen, um ihn entweder näher am oder im Framework zu verorten oder zu entfernen.

D> Ich habe diese Regeln trotz meiner Erfahrungen und Überzeugungen eher als »starke Empfehlungen« ausgedrückt. Ich war ehemals versucht, »müssen«, »müssen«, »müssen« zu schreiben. Wann auch immer wir mehr Dogma in unserem Entwicklerleben wünschen, benutzen wir dieses Verb. Letztendlich aber haben große Teile dieses Buchs ihren Ursprung noch in der Webentwicklungswelt von vor fünf bis zehn Jahren (weitere Aktualisierungen sollten das Buch weiter nach vorne schieben), und gibt es nicht nur neuere Tooling-Optionen, sondern auch [andere Schulen](https://meiert.com/blog/two-paradigms/) [und Philosophien](https://meiert.com/blog/css-extremes/) – Philosophien, die dank z.B. Tree-Shaking gar nichts verwerfliches daran entdecken können, wenn in irgendeiner Ecke Code liegt, der nicht verwendet wird. Das muss man eigentlich sezieren und sich näher anschauen, aber genau das macht dieses Buch noch nicht.
D>
D> Ein weiterer Punkt: Egal wie es um die Qualität eines Frameworks beschaffen ist, seine Einsatzziele kennen nur seine Nutzer, diejenigen die ein Framework für ein bestimmtes Projekt wählen und einsetzen. Frameworks sind dann vielleicht ein bisschen wie Autos: Ein gutes Auto sollte, sagen wir mal, sicher, leicht handhabbar und wirtschaftlich sein. Vergleichbar wie man sagen kann, dass ein gutes Framework maßgeschneidert, benutzerfreundlich und erweiterbar sein sollte. Der Autobauer und der Frameworks-Entwickler können hier Qualität abliefern. Aber genauso wie es dann auf die Fahrer ankommt, zu sagen, wo sie mit ihren Autos denn hin wollen, kommt es letztlich auf die Framework-Nutzer an, das Fahrtziel ihres Frameworks festzulegen. Wir können Frameworks genauso an die Wand fahren wie Autos. Egal, wie gut sie sind.