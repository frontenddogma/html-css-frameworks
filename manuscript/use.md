# Frameworks benutzen

Die zwei Arten, wie wir Frameworks ausgesetzt sein können, haben wir mit »Benutzen« und »Entwickeln« bestimmt (mit ein bisschen notwendiger Überschneidung). Die anfängliche Definition gibt diesem einen interessanten Blickwinkel, da wir wie besprochen jedes Stylesheet oder Skript als »Framework« betrachten können. Und in diesem Sinne hätte auch schon jeder, der mal mit Stylesheets oder Skripten gearbeitet hat, schon ein _grundsätzliches_ Verständnis davon, wie man mit Frameworks arbeitet.

Nach allem, was wir wissen, kann Benutzen nicht so kompliziert sein wie Entwickeln, und muss wenn überhaupt vom Framework abhängen. Benutzung erfordert also die Wahl eines Frameworks – und dann die Befolgung zweier Grundregeln.

## Ein Framework auswählen

@@

The “pro-quality” choice has been explained as using or developing
an internal framework, and choosing a framework generally applies
to external ones. The choice of an external framework depends on
two factors:

1. Which one meets our needs the best?
2. Which one is of the best quality (that is, which one is as tail‐
ored/customizable, usable, and extensible as possible)?

These questions underline the importance of knowing our precise
needs. It is even important in order to pick a framework, as knowing
our needs helps determine which framework fits better (tailoring)
and comes closer to our extensibility needs (though simple needs
don’t require extensibility as frequently as comprehensive needs).

## The Two Ground Rules of Using a Framework

And of any framework at that. These two rules are golden:

### 1. Follow the documentation

Whether internal or external framework, whether expert or begin‐
ner, read and follow the documentation.

This rule is paramount because the second source of quality issues
with frameworks and the works created with them (after framework
bloat) is user and developer error. Or user and developer miscon‐
duct! Some scenarios that illustrate this might be when a pattern is
hacked to work, when something has been developed that’s actually
already part of the framework, when things get overwritten without
regard for framework updates, or when something has just been
“made working.”

When using frameworks, always follow the documentation.

### 2. Don’t overwrite framework code

For reasons that will become clearer in the next section, never over‐
write framework code.

Contributing to the expert’s dilemma with external frameworks,
overwriting framework code can have unforeseen consequences and
break things with future updates. Here’s an example:
Framework:

```css
header {
  /* No layout declarations */
}
```

Overwrite:

```css
header {
  position: relative;
  top: 1em;
}
```

Framework update:

```css
header {
  left: 0;
  position: absolute;
  top: 0;
}
```

The example, simplified as it is, shows how a seemingly innocent
change can have acute consequences. Here, a header is moved by
one em. (Note that the example constitutes an overwrite because the
framework header is inherently “positioned” and also rests on the
initial values for position and top.) The next framework update,
however, switches to absolute positioning. As the overwriting rules
come later in the cascade, they prevent the update from working
(with the exception of left: 0;). In cases like this, overwrites are
unpredictable. Overwrites should hence be avoided where possible.

The remedy: For internal frameworks, update the framework, or
leave things as they are (as in, no overwriting). For external frame‐
works, leave things as they are, or create a separate pattern that does
the job (like an alternative header, with different markup). Stay away
from forking or “patch improvements”; solve issues at the core, or
not at all.

D> The more complex the project and the bigger the orga‐
nization, the harder it can be to display the necessary
discipline. Everyone working with a framework needs
to follow these two rules, however, to achieve the high‐
est levels of quality and consistency possible.

I> ### Overwriting Versus Extending
I>
I> There is a fine line between overwriting and extending code, espe‐
cially since overwriting doesn’t necessarily mean changing code.
Here are conceptual examples for both (with a CSS twist but appli‐
cable to other languages):
I>
I> Overwriting:
I>
I> * A → B: code A changed to, or replaced by, B.
I> * A1 → A2: code A, like a rule or function, doing 1 changed to
doing 2.
I> * [A1 + B1]: code A doing 1 extended by code B doing 1, too or
differently, in the same file (this is overwriting because the
eect of the original code changed).
I> * [A1] + [B1]: code A doing 1 extended by code B doing 1, too or
differently, in a different file (this is also overwriting because
the eect of the original code changed).
I> * (A1 + B2: not a case of overwriting nor extending, because it’s
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
extremely complicated. When we look at the case [A1] + [B1], for
example, we notice that we can face two challenges on debugging:
first, what happens exactly (why is A not in effect anymore?), and
second, where does it happen? Extending in the same file, or in
another well-defined manner, causes fewer issues.