# Frameworks benutzen

Die zwei Arten, wie wir Frameworks ausgesetzt sein können, haben wir mit »Benutzen« und »Entwickeln« bestimmt (mit ein bisschen notwendiger Überschneidung). Die anfängliche Definition gibt diesem einen interessanten Blickwinkel, da wir wie besprochen jedes Stylesheet oder Skript als »Framework« betrachten können. Und in diesem Sinne hätte auch schon jeder, der mal mit Stylesheets oder Skripten gearbeitet hat, schon ein _grundsätzliches_ Verständnis davon, wie man mit Frameworks arbeitet.

Nach allem, was wir wissen, kann Benutzen nicht so kompliziert sein wie Entwickeln, und muss wenn überhaupt vom Framework abhängen. Benutzung erfordert also die Wahl eines Frameworks – und dann die Befolgung zweier Grundregeln.

## Ein Framework auswählen

Eine Entscheidung »pro Qualität« wurde damit beschlossen, ein _internes_ Framework zu benutzen oder zu entwickeln. Die _Auswahl_ eines Frameworks bezieht sich nun eher auf externe Frameworks, und sie hängt von zwei Faktoren ab:

1. Befriedigt es unsere Bedürfnisse?
2. Ist es von hoher Qualität (d.h., ist es maßgeschneidert – oder zuschneidbar –, benutzerfreundlich und erweiterbar)?

An dieser Stelle wird also nochmals die Wichtigkeit betont, unsere genauen Bedürfnisse zu kennen. Dies ist selbst – oder selbstredend – bei der _Wahl_ eines Frameworks wichtig, da nur Kenntnis unserer Anforderungen hilft, überhaupt sagen zu können, welches Framework besser passt (Stichwort Maßschneiderung) und unseren Ansprüche im Hinblick auf Erweiterbarkeit genügt (wobei die Komplexität unserer Bedürfnisse in der Regel mit dem Bedarf nach Erweiterbarkeit korreliert). 

## Die zwei Grundregeln für den Gebrauch eines Frameworks

…&nbsp;und _jeden_ Frameworks. Diese beiden Regeln sind aus Gold:

### 1. Befolgen Sie die Dokumentation

Ob internes oder externes Framework, ob Experte oder Anfänger, lesen und folgen Sie der Dokumentation.

Diese Regel scheint so unbedeutend, ist aber kritisch, da nach Framework-Bloat die zweitgrößte Ursache für Qualitätsprobleme mit Frameworks und den damit erstellten Arbeiten Bedienfehler sind – oder Bedienfehlverhalten. Beispiele dafür sind oft erst unschuldig wirkende »Hacks« für Seitenelemente oder Eigenentwicklungen für Funktionen, die bereits Teil des Frameworks sind.

»RTFM« gilt auch bei Frameworks: Wenn wir ein Framework verwenden, sollten wir immer die Dokumentation beachten.

### 2. Überschreiben Sie keinen Framework-Code

Aus Gründen, auf die wir sofort etwas näher eingehen, sollte framework-eigener Code nie einfach überschrieben werden.

Ein Teil des Dilemmas des Experten, was externe Frameworks anbelangt, kann das Überschreiben von Framework-Code unvorhersehbare Konsequenzen haben und leicht Probleme mit zukünftigen Updates nach sich ziehen. Hier ist ein kleines Beispiel:

```css
header {
  /* Keine Layout-Deklarationen */
}
```

Unschuldiges Überschreiben:

```css
header {
  position: relative;
  top: 1em;
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

Das Beispiel, einfach wie es ist, zeigt wie eine scheinbar unschuldige Änderungen deutliche Folgen haben kann. Hier wird ein Header einfach ein `em` verschoben. (Da der Framework-Header implizit statisch »positioniert« war, handelt es sich tatsächlich um ein Überschreiben.) Das nächste Framework-Update stellt jedoch auf absolute Positionierung um. Da die überschreibenden Deklarationen später in der Kaskade folgen, verhindern sie das Update (mit der Ausnahme von `left: 0;`). In Fällen wie diesen sind die Effekte von Überschreibungen unvorhersehbar, und sie sollten aus diesem Grund so weit es geht vermieden werden.

Was sollte man wirklich tun? Bei internen Frameworks sollte man selbstverständlich nichts irgendwo anders überschreiben, sondern entweder das Framework direkt anpassen oder die Dinge so lassen, wie sie sind. Bei externen Frameworks sollte man genau das ebenfalls tun – die Dinge so lassen – oder ein separates Pattern, ein anderes Element entwickeln, dass die entsprechende Aufgabe übernimmt (wie z.B. ein alternativer Header, mit anderem Markup). Frameworks-Forks oder -Patches sollte man vermeiden. Es ist besser, wenn wir versuchen, die Dinge direkt an der Wurzel zu lösen – oder gar nicht, was uns evtl. irgendwann zu Handlungen zwingt, die auf lange Sicht besser sind, wie das Framework doch direkt zu verbessern, es zu wechseln oder eins zu bauen, das auf uns zugeschnitten ist. 

D> Je komplexer das Projekt und je größer die Organisation, desto schwieriger wird es, die hier nötige Disziplin aufzubringen. Aber jeder, der mit einem Framework arbeitet, sollte diese Regeln im Kopf behalten und wenn irgend möglich befolgen, um höchstmögliche Konsistenz und Qualität zu erreichen.

I> ### Überschreiben vs. Erweitern
I>
I> Es liegt nicht viel zwischen dem Überschreiben und Erweitern von Code, besonders wenn man bedenkt, dass Überschreiben nicht unbedingt heißt, Code direkt zu verändern – siehe Beispiel. Hier sind ein paar Beispiele – sehr CSS-spezifisch, aber auch anwendbar auf andere Sprachen.
I>
I> Überschreiben:
I>
I> * A → B: Code A zu Code B geändert oder durch diesen ersetzt.
I> * A~1~ → A~2~: Code A, z.B. Regel oder Funktion, die eine Sache 1 macht, angepasst, so dass sie Sache 2 macht.

@@

I> * [A~1~ + B~1~]: code A doing 1 extended by code B doing 1, too or
differently, in the same file (this is overwriting because the
eect of the original code changed).
I> * [A~1~] + [B~1~]: code A doing 1 extended by code B doing 1, too or
differently, in a different file (this is also overwriting because
the eect of the original code changed).
I> * (A~1~ + B~2~: not a case of overwriting nor extending, because it’s
exemplifying different code doing different things.)
I> 
I> Extending:
I> 
I> * [A + B]: code A extended by code B, in the same file.
I> * [A] + [B]: code A extended by code B, in a different file.
I> 
I> There are more cases, especially if we consider additional code
snippets (not just “B,” but also “C,” “D,” “E,” etc.) affecting code
written elsewhere (“A”). And sometimes, overwriting can be inten‐
tional or even elegant, so we don’t want to rule it out entirely!
I> 
I> The point is, especially for CSS, overwriting can not only have side
effects and introduce inconsistencies, but it can make our work
extremely complicated. When we look at the case [A~1~] + [B~1~], for
example, we notice that we can face two challenges on debugging:
first, what happens exactly (why is A not in effect anymore?), and
second, where does it happen? Extending in the same file, or in
another well-defined manner, causes fewer issues.