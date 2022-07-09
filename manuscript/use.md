# Frameworks benutzen

Die zwei Arten, auf die wir normalerweise mit Frameworks zu tun haben, haben wir mit »Benutzen« und »Entwickeln« bestimmt (mitsamt ein wenig notwendiger Überschneidung). Die anfängliche Definition betrachtet dies aus einem speziellen Blickwinkel, da wir wie besprochen theoretisch _jedes_ Stylesheet oder Skript als »Framework« deklarieren könnten. Und in diesem Sinne hätte auch schon jeder, der mal mit Stylesheets oder Skripten gearbeitet hat, ein _grundsätzliches_ Verständnis davon, wie man mit Frameworks arbeitet.

Nach allem, was wir wissen, kann Benutzen nicht so kompliziert sein wie Entwickeln, und muss wenn überhaupt vom Framework abhängen. Benutzen erfordert also die Wahl eines Frameworks – und die Befolgung von ein paar Grundregeln.

## Ein Framework auswählen

Die Entscheidung »pro Qualität« sollte dahin führen, ein _internes_ Framework zu benutzen oder zu entwickeln. Die _Auswahl_ eines Frameworks bezieht sich fast ausschließlich auf externe Frameworks, und sie hängt von zwei Faktoren ab:

1. Erfüllt es unsere Bedürfnisse und Anforderungen?
2. Ist es von hoher Qualität? (Ist es maßgeschneidert – zumindest zuschneidbar –, benutzerfreundlich und erweiterbar?)

An dieser Stelle wird also wiederholt die Wichtigkeit betont, unsere genauen Bedürfnisse zu kennen. Dies ist auch bei der _Wahl_ eines Frameworks wichtig, da nur Kenntnis unserer Anforderungen hilft, sagen zu können, welches Framework passt (Stichwort Maßschneiderung) und unseren Ansprüchen im Hinblick auf Erweiterbarkeit genügt (wobei die Komplexität unserer Bedürfnisse in der Regel mit dem Bedarf nach Erweiterbarkeit korreliert). 

## Die zwei Grundregeln für den Gebrauch eines Frameworks

…&nbsp;und _jedes_ Frameworks. Diese beiden Regeln sind golden:

### 1. Befolgen Sie die Dokumentation

Ob internes oder externes Framework, ob Experte oder Anfänger, lesen und folgen Sie der Dokumentation.

Diese Regel scheint so offensichtlich wie unbedeutend, ist aber kritisch. Bedienfehler (oder Bedienfehlverhalten) sind nach Framework-Bloat die zweitgrößte Ursache für Qualitätsprobleme mit Frameworks und den damit erstellten Arbeiten. Beispiele dafür sind oft unschuldig wirkende »Hacks« für Seitenelemente oder Eigenentwicklungen für Funktionen, die _bereits Teil_ des Frameworks sind.

[»RTFM«](https://de.wikipedia.org/wiki/Liste_von_Abk%C3%BCrzungen_(Netzjargon)#R) gilt auch bei Frameworks: Sobald wir ein Framework verwenden, sollten wir die Dokumentation beachten.

### 2. Überschreiben Sie keinen Framework-Code

Aus Gründen, auf die wir noch näher eingehen, sollte framework-eigener Code nie einfach überschrieben werden.

Was externe Frameworks anbelangt, kann das Überschreiben von Framework-Code unvorhersehbare Konsequenzen haben und leicht Probleme mit zukünftigen Updates nach sich ziehen. Hier ist ein Beispiel:

```css
header {
  /* Keine Layout-Deklarationen */
}
```

Unschuldiges Überschreiben:

```css
header {
  position: relative;
  top: 1rem;
}
```

Framework-Update:

```css
header {
  left: 0;
  position: absolute;
  top: 0;
}
```

Das Beispiel, einfach wie es ist, zeigt wie eine scheinbar triviale Änderung gravierende Folgen haben kann. Hier wird ein Header einfach ein `rem` verschoben. (Da der Framework-Header implizit statisch »positioniert« war, handelt es sich tatsächlich um ein Überschreiben.) Das nächste Framework-Update stellt jedoch auf absolute Positionierung um. Da die überschreibenden Deklarationen später in der Kaskade folgen, verhindern sie das Update (mit der Ausnahme von `left: 0`). In Fällen wie diesen sind die Effekte von Überschreibungen unvorhersehbar, und sie sollten aus diesem Grund so weit es geht vermieden werden.

Was kann man statt dessen tun? Bei internen Frameworks sollte man selbstverständlich nicht irgendwo Dinge überschreiben, sondern entweder das Framework direkt anpassen oder die Dinge so lassen, wie sie sind. Bei externen Frameworks sollte man entweder dasselbe tun – die Dinge so lassen – oder ein separates Pattern, ein anderes Element entwickeln, das die entsprechende Aufgabe übernimmt (wie z.B. ein alternativer Header, mit anderem Markup). Framework-Forks oder -Patches sollte man vermeiden. Es ist besser, wenn wir versuchen, die Dinge direkt an der Wurzel zu lösen – oder überhaupt nicht, was uns zu Handlungen motivieren kann, die _auf lange Sicht besser_ sind (wie das Framework doch direkt zu verbessern, es zu wechseln oder eins zu bauen, das auf uns zugeschnitten ist).

D> Je komplexer das Projekt und je größer die Organisation, desto schwieriger ist es, die hier nötige Disziplin aufzubringen. Aber jeder, der mit einem Framework arbeitet, tut gut daran, diese Regeln in Erinnerung zu behalten und zu befolgen, um höchstmögliche Konsistenz und Qualität zu erreichen.

I> ### Überschreiben vs. Erweitern
I>
I> In früheren Fassungen dieses Buchs gab es hier einen Info-Kasten, der aufschlüsselte, welche Formen es gibt, Code zu überschreiben und zu erweitern. Dieser meinte es etwas sehr gut, und machte die Sache unnötig kompliziert. Der Info-Kasten schloss aber mit einem Absatz, der wenig verändert bleiben soll:
I> 
I> Der Punkt ist, dass besonders im Fall von CSS Überschreiben zu Nebeneffekten und Inkonsistenzen führen und unsere Arbeit erschweren kann. An anderer Stelle – in derselben oder einer anderen Datei – CSS-Regeln zu überschreiben führt leicht zu zwei Herausforderungen: Zum einen, was passiert genau (warum greift der ursprüngliche Code nicht mehr?); zum anderen, wo passiert was? Diesem Drang zu widerstehen, ansonsten aber möglichst nah an der Ursprungsstelle Anpassungen vorzunehmen, verursacht deutlich weniger Probleme.