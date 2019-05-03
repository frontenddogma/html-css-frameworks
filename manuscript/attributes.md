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

@@

Now, some frameworks like Bootstrap or Gumby have begun to
address these problems by offering sophisticated customization wiz‐
ards. This is smart, because it significantly alleviates the issues of
non-tailored solutions. Framework developers should offer and
users use such functionality.

By the way, there’s another problem we need to consider: while we’re
benefiting from either our decision to save cost or to improve qual‐
ity, our end users benefit mostly from quality. Technically speaking,
they are rarely on the list of beneficiaries if we decide to deploy a
framework that’s bloated but easy to churn out.

To tailor internal frameworks:

* Be clear about needs.
* Build the framework to these needs.

To tailor external frameworks:

* Be clear about needs.
* Customize or modify the framework to these needs (or abstain
from the framework).

## 2. A Framework Should Be Usable

A good framework is not only tailored but also usable. But what is
usability for frameworks? It starts with applying the common defini‐
tion of usability: ease of use and learnability. And with a universal
rule: keep it simple. Simplicity helps everything.

But that’s not quite a complete answer, and so we need to differenti‐
ate again. The distinction that serves us here is not one between
frameworks, but between roles: framework users and framework
developers.

For the framework user (who may be a developer himself but is now
concerned with working with the framework), a usable framework is
also easy to understand. That ease of understanding is primarily
achieved through clear framework documentation and, where appli‐
cable, concise code.

For the framework developer, there’s much more emphasis on usable
code. Luckily, there are two things we can firmly link with helping
code usability: maintainability practices and code conventions (cod‐
ing guidelines). Adherence to maintainability practices and consis‐
tent style are the backbone for usable code.

With slightly smaller boundaries than developer experience, I gener‐
ally believe there is a subfield of usability: developer usability. It
could be defined as “the ease of use and learnability of code.” Per‐
haps this field doesn’t get much attention because usable code goes
under different names, as we just found, but perhaps it would bene‐
fit from being treated separately.

To make frameworks more usable for users:

* Keep it simple.
* Follow usability conventions.
* Perform usability tests.
* Provide documentation for framework users.

To make frameworks more usable for developers:

* Keep it simple.
* Aim for self-explanatory code.
* Format code legibly and consistently.
* Follow maintainability best practices.
* Provide documentation for framework developers.

### 3. A Framework Should Be Extensible

The final attribute to underscore is extensibility. Extensibility for a
framework means that it’s not just possible, but well-defined and
easy to extend it.

Extensibility is necessary for two reasons. First, external frameworks
in particular won’t offer everything we need, so there needs to be a
way to add functionality. Second, especially in large projects, there’s
a tendency for new patterns to pop up. The problem with these is
their uncertainty and uniqueness: they may only be used once or
twice and don’t warrant a place in the framework core or even near
more common extensions. Both their location and handling have to
be thought of.

To make up for lacking functionality in a framework, users typically
help themselves by pretending they don’t use a framework in the
first place. That is, they have a style sheet or script that handles
everything the framework doesn’t cover. That’s actually quite OK;
the point here is to be clear about how such “non-framework func‐
tionality” or extensions are handled (and we notice how extensibil‐
ity is also a user responsibility). If nothing else, extensibility stresses
the need for the most basic of all code safeties: a namespace (a
framework-specific ID and class name prefix, and the same name‐
space in JavaScript).

Next, new and rarely used patterns are a challenge that runs in the
best families. There tends to always be a need for something new,
and there are always document types or elements that are used infre‐
quently. They’re one of the biggest contributing factors to code
bloat. They are hard to control if they don’t get watched and reigned
in vigorously. Though I could give a longer dissertation about the
matter, an effective counter-practice is to either designate style sheet
and script sections for new and experimental code, as well as rare
elements—or to even put aside a separate style sheet and script for
such purposes. The framework developers should anticipate this and
make recommendations, but users should come up with their own
guidelines if this piece has not been covered. A documented stan‐
dard for new code allows better monitoring and better decisions on
whether to keep (and relocate) the code, or to remove it.

We’ve very successfully applied this principle with Google’s
HTML/CSS framework Go—not to be confused with the program‐
ming language, which was conceived two years later. Go came with a
“backpack” library, Go X, which included elements that we used
only occasionally. This kept the core very small—4,250 bytes includ‐
ing the Google logo—but offered the use of additional, common
enough elements. Project-specific code made for a third layer that
had to be carried by each project style sheet itself.

To make frameworks more extensible:

* Use a framework namespace.
* Define handling of non-framework code.
* Specify where new and rarely used code should be located (also
a framework-user responsibility).
* Regularly review new and rarely used code, to either make part
of framework or remove (also a framework-user responsibility).

I> Please note that despite all my experience and convic‐
tions, I’ve phrased these rules as strong suggestions. I
was tempted to say “must,” “must,” “must.” Whenever
we like more dogma in our web development life, we
use this verb.
I> 
I> Another thing before we move on: note that no matter
the quality of the framework, the goal for its use is
always on the owners and developers. Frameworks can
be likened to cars: a good car should be, say, safe, easy
to handle, and economical. And so a good framework
should be tailored and usable and extensible. But just
as we look at the driver to know the destination for her
car, we look at the developer to know the goals for the
framework she’s using. We can drive a framework
against the wall just as we can a car, which is the reason
we differentiate between experts and novices. Just to
get this out there: a framework doesn’t drive itself.