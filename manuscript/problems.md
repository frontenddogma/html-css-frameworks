@@ Check on links and emphasis


# Bekannte Probleme

Da Frameworks vor allem in größeren Projekten nützlich sind, sind die Probleme beim Einsatz mit Frameworks auch oft größer. Hier sind einige der verbreitetsten und schwerwiegendsten Probleme, zusammen mit ein paar Ideen, wie man mit ihnen umgehen kann.

## Mangel an Disziplin

Eins der größten Probleme, die im Einsatz von Frameworks auftauchen, ist Mangel an Disziplin. Bei Nutzern bedeutet dies, dass diese Frameworks nicht wie vorgesehen benutzen und die beiden Grundregeln verletzen (Dokumentation beachten, keinen Code überschreiben). Bei Entwicklern heißt dies üblicherweise, dass sie bei der Qualität abreißen lassen, also Qualitätsstandards ignorieren, Prototypen vernachlässigen oder Dokumentation nicht mehr schreiben oder aktuell halten. Das Ergebnis ist dasselbe: Sabotage – das wollte ich aus der Originalausgabe stehen lassen –, bloß von unterschiedlichen Seiten.

Die Lösung ist nicht einfach. Benutzern externer Frameworks steht es eh frei, zu tun, was sie wollen; ihnen mag gar nicht erst auffallen, dass die das gewählte Framework nicht richtig zureiten. Die Situation ist bei internen Frameworks einfacher, da Regeln aufgestellt, kommuniziert und durchgesetzt werden können. Kein Mittel bringt aber garantiert Heilung – Menschen sind gerne kreativ, und zu verfolgen, wie Frameworks in der Praxis genau verwendet werden, scheint einen guten Einblick in die menschliche Natur zu geben (ebenso wie auf Murphys Gesetz).

## Mangel an einem Prototypen

Keinen Prototypen zu haben ist ein gleichermaßen kritisches Problem, dank all der im Kapitel @@ genannten Vorteile, die ein solcher mit sich bringt. Abgesehen von der Tatsache, dass die Entwicklung von Frameworks ungleich schwerer wird, wenn sie in keiner abgegrenzten Umgebung getestet werden kann, vergrößert sich die Wartungskomplexität quasi minütlich ohne Prototyp, ohne solche Umgebung. Ein Framework ohne Prototyp dreht frei, gerät außer Kontrolle. Wie zuvor angeraten kann bereits eine Sammlung statischer Seiten bereits helfen – so diese die grundlegenden Elemente vollständig abdeckt, und sie aktuell und realistisch ist.

## Mangel an Wartung

Wenn wir Wartungsarbeiten nur noch bei größeren strukturellen Änderungen oder Problemen mit Dritten vornehmen, verpassen wir nicht nur Gelegenheiten, sondern verstehen auch Wartung falsch. Im Fall von externen Frameworks kann mangelnde Wartung die Reputation schädigen. Im Fall von internen Frameworks kann solch Passivität zur Folge haben, dass die mit dem Framework umgesetzen Seiten und Apps nicht mehr effektiv umgesetzt werden können, man damit die Kontrolle über das Framework verliert und man selbst und andere Teams in einen umfassenden, teuren Framework-Relaunch gezwungen werden.

Wartung heißt nicht, ein Framework kontinuierlich zu _verändern_. Das kann sogar schädlich sein, besonders bei externen Frameworks, weil hier das Echo stärker ausfallen kann und gleichzeitig weniger zu beeinflussen ist. Ein Frameworks sollte vielmehr kontinuierlich überwacht, getestet und punktuell verbessert werden, um es funktionsfähig und aktuell zu halten. Solch Pflege zahlt sich dann auf viele Arten aus, sei es dadurch, dass sie den Bedarf nach drastischeren Anpassungen minimiert (wie Relaunches, die immer kostspielig sind), oder weil jeder, ob Nutzer oder Entwickler, nah am Framework bleibt und damit vertraut mit ihm vertraut ist.

I> ### Eine Vision für Webentwicklung
I>
I> Es gibt eine Sache, die jeder Webentwickler anstreben sollte: minimales, semantisch angemessenes, valides HTML zu schreiben und dieses nie zu ändern. »Nie« nicht im Sinne von Leugnen und Ablehnen, weil strukturelle Änderungen natürlich immer notwendig sein und Anpassungen erfordern können, sondern im Sinne eines Leitsatzes. Die Idee minimalen, semantisch korrekten, validen Markups kitzelt das Optimimum aus uns heraus. Es führt uns dabei nicht nur zu hoher Qualität, sondern treibt uns an, größere Kräfte in unseren Stylesheets und Skripten zu erwerben und freizusetzen. Die Vision ist eine von höchster Effizienz, um präsentationsbezogene Anpassugen nur durch CSS- und verhaltensbezogene nur durch JavaScript-Änderungen vorzunehmen. HTML zu schreiben, designagnostisch wie dieses sein sollte, wurde schon immer unterschätzt – es ist am schwersten, wirklich gut zu schreiben.

## Mangel an Genauigkeit

Eine Annahme, die wir bisher getroffen haben, ist dass was unsere Frameworks machen, genau ist – d.h., dass sie den angepeilten Bedürfnissen und Designs tatsächlich entsprechen. Letzteres kann eine potentielle Fehlerquelle sein, wenn die Frameworks, die wir entwickelt haben oder die wir einsetzen nicht den Spezifikationen entsprechen, die unsere Designer von uns erwarten (sofern wir nicht selbst die Designer sind). Das kann zu allen möglichen Fehlern führen – von nicht dazu in der Lage sein, den ursprünglichen Plan zu erfüllen (also letztendlich kein externes Framework einsetzen zu können) über den Bedarf nach strukturellen, also HTML-Änderungen (aua) bis hin zum Ansatz, unsere Designer zu bitten, die Unterschiede wegzurationalisieren und sie mit Photoshop o.ä. wegzuwischen, alles, um nicht das Framework anzufassen. Wir müssen auf solche Design- und Style-Divergenzen achten.

## Mangel an Mut

Die letzte große Herausforderung ist, nicht in der Lage zu sein, den Stecker zu ziehen – selbst wenn das nur Unterstützung durch Vorgesetzte erfordert. Sich an etwas zu hängen, das nicht mehr relevant ist. Das nicht mehr verwendet wird. Das falsch verwendet wird. Das eine Bauruine ist. Das nicht mehr gewartet oder erweitert werden kann. Etwas in dieser Art.

Einem kaputten, fehlgeschlagenen, vielleicht nach ersten Erfolgen glorifizierten Framework die ewige Treue zu schwören, kann wirklich ein Problem sein. Wenn das passiert, müssen wir irgendwie darüber hinwegkommen, und den Mund abwischen. Als Profis haben wir immer ein ambitioniertes Ziel, wenn unser Code lange halten soll – und manchmal scheitern wir damit, und das ist okay.

Glücklicherweise, mag man sagen, gibt es immer mehr Code zu schreiben. Das nächste Framework – oder Stylesheet, oder Skript – wartet schon auf uns.
