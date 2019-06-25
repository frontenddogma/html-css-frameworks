# Frameworks benutzen

Die zwei Arten, auf die wir normalerweise mit Frameworks zu tun haben, haben wir mit »Benutzen« und »Entwickeln« bestimmt (mitsamt ein wenig notwendiger Überschneidung). Die anfängliche Definition betrachtet dies aus einem speziellen Blickwinkel, da wir wie besprochen theoretisch _jedes_ Stylesheet oder Skript als »Framework« deklarieren könnten. Und in diesem Sinne hätte auch schon jeder, der mal mit Stylesheets oder Skripten gearbeitet hat, ein _grundsätzliches_ Verständnis davon, wie man mit Frameworks arbeitet.

Nach allem, was wir wissen, kann Benutzen nicht so kompliziert sein wie Entwickeln, und muss wenn überhaupt vom Framework abhängen. Benutzen erfordert also die Wahl eines Frameworks – und dann die Befolgung von Grundregeln.

## Ein Framework auswählen

Die Entscheidung »pro Qualität« sollte dahin führen, ein _internes_ Framework zu benutzen oder zu entwickeln. Die _Auswahl_ eines Frameworks bezieht sich fast ausschließlich auf externe Frameworks, und sie hängt von zwei Faktoren ab:

1. Befriedigt es die Bedürfnisse?
2. Ist es von hoher Qualität? (Ist es maßgeschneidert – zumindest zuschneidbar –, benutzerfreundlich und erweiterbar?)

An dieser Stelle wird also nochmals die Wichtigkeit betont, unsere genauen Bedürfnisse zu kennen. Dies ist auch bei der _Wahl_ eines Frameworks wichtig, da nur Kenntnis unserer Anforderungen hilft, sagen zu können, welches Framework passt (Stichwort Maßschneiderung) und unseren Ansprüchen im Hinblick auf Erweiterbarkeit genügt (wobei die Komplexität unserer Bedürfnisse in der Regel mit dem Bedarf nach Erweiterbarkeit korreliert). 

## Die zwei Grundregeln für den Gebrauch eines Frameworks

…&nbsp;und _jeden_ Frameworks. Diese beiden Regeln sind golden:

### 1. Befolgen Sie die Dokumentation

Ob internes oder externes Framework, ob Experte oder Anfänger, lesen und folgen Sie der Dokumentation.

Diese Regel scheint so offensichtlich wie unbedeutend, ist aber kritisch, da nach Framework-Bloat die zweitgrößte Ursache für Qualitätsprobleme mit Frameworks und den damit erstellten Arbeiten Bedienfehler sind – oder Bedienfehlverhalten. Beispiele dafür sind oft erst unschuldig wirkende »Hacks« für Seitenelemente oder Eigenentwicklungen für Funktionen, die _bereits Teil_ des Frameworks sind.

[»RTFM«](https://de.wikipedia.org/wiki/Liste_von_Abk%C3%BCrzungen_(Netzjargon)#R) gilt auch bei Frameworks: Wenn wir ein Framework verwenden, sollten wir immer die Dokumentation beachten.

### 2. Überschreiben Sie keinen Framework-Code

Aus Gründen, auf die wir noch näher eingehen, sollte framework-eigener Code nie einfach überschrieben werden.

Was externe Frameworks anbelangt, kann das Überschreiben von Framework-Code unvorhersehbare Konsequenzen haben und leicht Probleme mit zukünftigen Updates nach sich ziehen. Hier ist ein kleines Beispiel:

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

Das Beispiel, einfach wie es ist, zeigt wie eine scheinbar triviale Änderung gravierende Folgen haben kann. Hier wird ein Header einfach ein `rem` verschoben. (Da der Framework-Header implizit statisch »positioniert« war, handelt es sich tatsächlich um ein Überschreiben.) Das nächste Framework-Update stellt jedoch auf absolute Positionierung um. Da die überschreibenden Deklarationen später in der Kaskade folgen, verhindern sie das Update (mit der Ausnahme von `left: 0;`). In Fällen wie diesen sind die Effekte von Überschreibungen unvorhersehbar, und sie sollten aus diesem Grund so weit es geht vermieden werden.

Was sollte man tun? Bei internen Frameworks sollte man selbstverständlich nicht irgendwo Dinge überschreiben, sondern entweder das Framework direkt anpassen oder die Dinge so lassen, wie sie sind. Bei externen Frameworks sollte man entweder dasselbe tun – die Dinge so lassen – oder ein separates Pattern, ein anderes Element entwickeln, das die entsprechende Aufgabe übernimmt (wie z.B. ein alternativer Header, mit anderem Markup). Framework-Forks oder -Patches sollte man vermeiden. Es ist besser, wenn wir versuchen, die Dinge direkt an der Wurzel zu lösen – oder gar nicht, was uns evtl. irgendwann zu Handlungen zwingt, die _auf lange Sicht besser_ sind, wie das Framework doch direkt zu verbessern, es zu wechseln oder eins zu bauen, das auf uns zugeschnitten ist. 

D> Je komplexer das Projekt und je größer die Organisation, desto schwieriger ist es, die hier nötige Disziplin aufzubringen. Aber jeder, der mit einem Framework arbeitet, tut gut daran, diese Regeln in Erinnerung zu behalten und wenn irgend möglich zu befolgen, um höchstmögliche Konsistenz und Qualität zu erreichen.

I> ### Überschreiben vs. Erweitern
I>
I> Es liegt nicht viel zwischen dem Überschreiben und Erweitern von Code, besonders wenn man bedenkt, dass Überschreiben nicht unbedingt heißt, Code direkt zu verändern – siehe vorheriges Beispiel. Hier sind ein paar weitere Szenarien – bezogen auf CSS, aber auch anwendbar auf andere Sprachen.
I>
I> Überschreiben:
I>
I> * A → B: Code A zu Code B geändert oder durch diesen ersetzt.
I> * A1 → A2: Code A, z.B. Regel oder Funktion, die eine Sache 1 macht, angepasst, so dass sie Sache 2 macht.
I> * \[A1 + B1]: Code A, der 1 macht, erweitert durch Code B, der in derselben Datei 1 auf dieselbe oder eine andere Weise macht (das ist Überschreiben, weil der ursprüngliche Code nun nicht mehr greift).
I> * \[A1] + \[B1]: Code A, der 1 macht, erweitert durch Code B, der in einer anderen _Datei_ 1 auf dieselbe oder eine andere Weise macht.
I> * (A1 + B2: kein Überschreiben oder Erweitern, weil nur ein Beispiel dafür, wie unterschiedlicher Code unterschiedliche Sachen macht.) 
I> 
I> Erweitern:
I> 
I> * \[A + B]: Code A erweitert durch Code B, in derselben Datei.
I> * \[A] + \[B]: Code A erweitert durch Code B, in einer anderen Datei.
I> 
I> Es gibt viele weitere Fälle, vor allem wenn wir beginnen, weitere Code-Snippets in Bezug zu setzen (nicht nur »B«, sondern auch »C«, »D«, »E« &c.), die Code an anderer Stelle (»A«) berührt. Und manchmal kann dies beabsichtigt sein, vielleicht sogar elegant, und so soll Überschreiben und Erweitern hier nicht pauschal verurteilt werden.
I> 
I> Der Punkt ist vielmehr, dass besonders im Fall von CSS Überschreiben zu Nebeneffekten und Inkonsistenzen führen und unsere Arbeit extrem verkomplizieren und erschweren kann. Wenn wir uns z.B. den Fall \[A1] + \[B1] nochmal ansehen, bemerken wir, wie er leicht zu zwei Herausforderungen führt: Zum einen, was passiert genau (warum ist A nicht mehr in Kraft?); zum anderen, wo passiert was? Allein in derselben Datei zu erweitern mag schon weniger Probleme verursachen.