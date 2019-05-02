# Bekannte Probleme

@@

Since frameworks are most useful in larger projects, problems
involving frameworks tend to be bigger, too. Here are a few of the
most common and gravest issues, along with ideas on how to
address them.
Lack of Discipline
One of the most severe issues is lack of discipline. For the user, this
most commonly means not using frameworks as intended and vio‐
lating the two ground rules (following documentation and not over‐
writing framework code). For the developer, this usually means
becoming sloppy with quality standards, the prototype, or docu‐
mentation. The result is the same: sabotage, just from opposite sides
of the table.
The solution is not easy to come by. Users of external frameworks
are free to do what they want anyway; they may not even notice that
an external framework is very difficult to ride in the first place. It’s a
bit easier internally, where rules can be established, communicated,
and enforced. Personally, while I have observed many issues in prac‐
tice, I haven’t found a cure for this one yet. People are just very crea‐
tive, and watching how frameworks end up being used is like look‐
ing right into the face of human nature (and Murphy’s Law).
Lack of a Prototype
Not having a prototype is an equally critical problem, for all the
benefits outlined in “Prototype” on page 19. Apart from the fact that
framework development is so much harder without a contained
environment, maintenance complexity increases by the minute if
there is no prototype. A framework without a prototype is essen‐
tially freewheeling, out of control. As suggested earlier, a mere col‐
lection of static pages—as long as it’s complete, current, and realistic
—does help.
Lack of Maintenance
If we do not maintain (or stop to maintain), outside of major struc‐
tural changes or prolonged resource shortages, we miss great oppor‐
tunities. In the case of external frameworks, it can damage the repu‐
tation of those providing the framework. In the case of internal
frameworks, it can mean giving up control over the frameworkmanaged docs and apps, and thus slowly being forced into a costly,
full-blown relaunch.
Maintenance doesn’t mean we should continuously change a frame‐
work—that may even be hurtful, especially for external frameworks
because of the nuisance it creates. Rather, we should regularly moni‐
tor, test, and tweak the framework to keep it current. Such care pays
off in many ways, be it because it reduces the need for more drastic
changes (relaunches, which are pricey) or because everyone’s staying
in touch and familiar with the framework.
A Vision of Web Development
There is one thing every web developer should aspire to: writing
the most minimal, semantically appropriate, valid HTML, and then
never changing it. “Never” not in a sense of denial and refusal, since
structural changes can always require modifications, but in the
sense of a guiding light. The idea of minimal, semantically appro‐
priate, valid markup brings the most out of us as web developers. It
leads us not only to supreme markup quality, but pushes us to
acquire and exhibit bigger powers in our style sheets and scripts.
The vision is one of highest efficiency, to handle presentational
changes only through CSS updates and behavioral ones only
through JavaScript updates. Writing HTML, design-agnostic as it
should be, has always been underestimated; it’s the hardest to write
well.
Lack of Accuracy
An assumption we’ve made thus far is that what our frameworks do
is accurate—that is, that they match the underlying needs and
designs. That latter part can be a potential source of error if the
frameworks we coded or found ourselves using don’t match the
specs our designer friends sent us (if we’re not the designers our‐
selves). This can lead to all kinds of issues: from not being able to
accommodate the original plan (no use for our external framework)
to needing structural changes (ouch) to asking the designer folks to
rationalize and Photoshop the differences away instead of fixing the
framework. We need to watch out for design and style guide diver‐
gence.
Lack of Guts
The last big issue is to not have what it takes—even if that’s manager
support—to pull the plug. Clinging on to something that’s not rele‐
vant anymore. Something that’s not used anymore. That’s used
wrong. That’s a construction ruin. That can’t be maintained or
extended. Something like that.
Sticking with a broken framework, a failed one, or perhaps a glori‐
ous one that has just reached the end of its lifetime can be a chal‐
lenge. When that happens to us, we need to get over it. As professio‐
nals, we have big goals and we want our code to last—but sometimes
we fail, and then we need to…suck it up.
Fortunately, there’s always more code to write. The next framework
—or style sheet, or script—is already waiting for us.