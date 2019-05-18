# Frameworks entwickeln

Frameworks zu entwickeln ist eine Kunst, die mit einer Menge Verantwortung einhergeht. Externe Frameworks haben dabei etwas von Draufgängertum (gepaart mit einem Schuss Naivität). Wie das gesamte Buch bisher festhält, es ist notwendigerweise am schwierigsten, ein externes Framework zu bauen, weil wir die Bedürfnisse anderer Projekte nicht kennen _können_. Aus diesem Grund kommen Entwickler von externen Frameworks zwangsläufig in die Lage, etwas auszuliefern, dem es irgendwo mangelt – oder das vielzu viel ist.

Der folgende Abschnitt beschreibt die Grundlagen für die Entwicklung eines Frameworks, mit speziellem Bezug für die Arbeit in einer größeren Organisation.

## Prinzipien

Wir haben hierzu bereits alle Aufgaben erledigt und alle Prinzipien für die Framework-Entwicklung erarbeitet. Ein Framework sollte entsprechend die höchsten Qualitätsstandards anstreben, und:

1. Ein Framework sollte maßgeschneidert sein.
2. Ein Framework sollte benutzerfreundlich sein.
3. Ein Framework sollte erweiterbar sein.

Diese Prinzipien sollten die Hauptwerte für jedes Framework darstellen, und dazu können wir bereits auf Methoden zurückgreifen, die in vorherigen Abschnitten behandelt wurden.

@@

Customization, as identified under “1. A Framework Should Be Tail‐
ored” on page 10, plays a special role here, for it is the secret weapon
—and last line of defense—of the external framework developer.
Offering framework customization options is the only way to get
closer to tailoring for outside users, users whose projects we will
never know.

I decided against including a section about customization because
it’s not a magic pill for external frameworks, and can stack the whole
deck against the framework developer instead of the framework
user. This is because the more customization options there are, the
more complex the framework gets. Yet that’s still only talking frame‐
work development. The framework and all its customized subver‐
sions, as we’ll see shortly, still need to be tested, quality-managed,
maintained, and so on.

## Prototype

The single most important thing we need to build a successful
framework is a prototype. Here we benefit from our recognition that
we’re really only talking about plain-vanilla style sheets and scripts.
Large projects—projects like those for which we now talk frame‐
works—have always benefited from prototypes.

What do we mean by prototype? In its simplest form, it is a static
(internal) website or demo site. It should contain all document types
and elements we need in production: the prototype is where we code
all the structure (HTML), presentation (CSS), and behavior (Java‐
Script). And the prototype should include realistic (occasionally
intermingled with extreme) sample contents: that’s how we test that
everything works.

A prototype is an irreplaceable testing ground that we need to
obtain the end result we want.

Prototypes follow their own principles, however. They must be, as I
attempted to summarize in earlier years (slightly reworded):

* Complete
* Current
* Realistic
* Focused
* Accessible/available
* Managed with discipline
* Maintained
* Communicated/promoted
* Documented

Each of these points is important, but the first three are critical. The
prototype has to include everything (all document types and ele‐
ments), it must be current (any functionality changes must be reflec‐
ted immediately), and it needs to be realistic (the sample data must
be an as-good-as-possible approximation of how the framework is
going to be used outside of the prototype).

## Quality Management

In order to be sure that we deliver the quality we’re committing to as
professionals, we need to verify it. This is done through quality
assurance (which aims to prevent issues by focusing on the process),
and quality control (which aims to find and fix issues in the end
product).

Web development, as a still rather young discipline, knows more
quality control than quality assurance. Good examples are valida‐
tion, accessibility, and performance checks, of which there are
plenty. On the quality assurance end, the most prominent example is
the enactment of coding guidelines, but some organizations and
individuals go so far as to use elaborate infrastructure to continu‐
ously test and improve their code. (This is all related to web rather
than software development, since in software development, there is
a longer history and strong tradition of working with tests.)

For quality assurance, it’s useful to:

* Establish coding guidelines
* Define output quality criteria
* Run regular tests (over prototype and live implementations)

For quality control, test:

* Accessibility
* Links (if applicable)
* Performance
* Responsiveness
* Maintainability
* Validation
* Linting
* Formatting

(Incidentally, I run a website hub dedicated to web development
testing tools. Check uitest.com/en/analysis/ for a large selection of
them.)

To take a page out of Google’s book, it’s best to automate such
checks. Reviewing tool documentation can give valuable pointers, as
a number of tools can be installed locally or come with an API. In
addition, there are instruments like Selenium and ChromeDriver
that facilitate automated browser testing. As with many of the more
complex topics, this book will resort to just showing directions.

## Maintenance

We’ve so far noted how principles, a prototype, and quality manage‐
ment are important in framework development. The last key item to
stress is maintenance. Maintenance here primarily means (similar to
prototypes) a strong commitment to move forward with a frame‐
work. This is important for two reasons.

For one, in the case of external frameworks, maintenance is crucial
because publishing a framework is a promise to the user base. That
promise is precisely that it’s going to be maintained. It’s also a
promise in how it’s going to be maintained, in that we do everything
in our power not to change any structure, but only the framework
style sheets and scripts.

For another, in any framework, a commitment to maintenance acts
like another form of safety. The general idea in web development is
that the HTML is most important to get right, because it’s more
expensive—think our cost definition—to change than style sheets
and scripts. An explicit commitment to maintenance will keep us
from discarding a framework to just “build another,” and thus lives
up to the vision of CSS-only design iterations and refactorings. (Of
course, true structural changes will still always require HTML
changes, and with that, eventually, CSS and JavaScript edits.)

A framework, solving widespread and complex development and
design issues, comes with an express obligation to maintenance.

I> ### Maintaining and Breaking
I> 
I> A word of caution: while we, as framework developers, need to
show responsibility and exercise thorough care not to break any‐
thing with framework updates, we must also not worry too much
about breaking something. On the question what the most impor‐
tant thing was when creating and maintaining frameworks, I
responded a few years ago:
I> 
I> “The more used and hence successful a framework is, the more
likely it is that things will break over regular maintenance. […]
maintenance is key, yet avoiding things to break is impossible,
and the attempt alone unbelievably expensive. And then, while
things go wrong, things never go wrong badly. And that leads
back to setting expectations: […] people should embrace, not
fear, updates to them.”
I> 
I> I believe that this advice is still sound. Code can’t afford anxiety. If
we developers do our homework, occasional breaks can even be a
good thing (and maybe the only thing) to educate framework users
about ground rules and proper framework usage, and to expose
other coding-related issues. As developers we sometimes have to
make tough choices.

### Updates

The handling of framework updates is delicate enough to deserve a
separate section. Updates are generally easier to manage for internal
frameworks than for external ones, though updates in a large orga‐
nization with many developers spread out over many places can be
challenging, too.

Here are a few tricks to make framework updates easier:

* Try to avoid HTML changes because of their comparatively
high cost. An update should only consist of styling or scripting
changes and impart no actual work for users (which, to counter
the aforementioned definition blurriness, also means developers
who work with the framework). The update of framework refer‐
ences can be OK.
* Announce updates in advance.
* Provide a way to test whether the update would have any ill
effects. This can happen through something simple like book‐
marklets (see “Test Bookmarklets” on page 23), or something
more sophisticated like proxying (using a proxy to intercept and
change requests to framework files in order to feed updated files
for testing).
* Inform users about possible side effects (and use this as an
opportunity to educate them about, for example, the problems
of overwrites, as explained in “2. Don’t overwrite framework
code” on page 15).
* Communicate the status of ongoing updates.

What we’re assuming here is that we’re not just “versioning” frame‐
works. That’s the practice of shipping a framework—let’s say, foo—
and when the first changes come, not updating foo, but shipping
foo-2. And then foo-3. And so on. This practice may be an option for
us, but not a rule. The rule should be to update the framework itself,
per the ideas listed here. The reason is that versioning defeats the
purpose and advantage of CSS (similarly for JavaScript), which are
immediate changes, supported by separation of concerns (HTML
for structure, CSS for presentation, and JavaScript for behavior).
We’ll touch on the vision behind this shortly, but we should strive to
do all updates through what we already have. And only for major
changes do we look into our toolbox and, always carefully, recon‐
sider versioning.

I> ### Test Bookmarklets
I> 
I> CSS bookmarklets are a great low-tech way of allowing users to test
framework changes. A short example:
I> 
I> Framework:
I> 
I> ```css
I> article {
I>   margin: auto;
I>   width: 50%;
I> }
I> ```
I> 
I> Framework after update:
I> 
I> ```css
I> article {
I>   width: 90%;
I> }
I> ```
I> 
I> To prepare a test for the update and make sure everything keeps
working as intended, take all the changed declarations and all the
removed declarations, set the removed declarations’ properties to
their defaults, and on that basis, generate the testing rules:
I> 
I> Test style sheet:
I> 
I> ```css
I> article {
I>   margin: 0;
I>   width: 90%;
I> }
I> ```
I> 
I> We’re simplifying here by assuming that <article> doesn’t pick up
other margin values from anywhere else. margin has to be set
because while it’s been removed from the new framework, it would
still be applied through the old framework, which is in effect on the
pages where we want to test the new code. So the test style sheet
needs to neutralize all old code—something we could in really
tricky cases, as a last resort, also attempt through the all property.
I> 
I> Jesse Ruderman’s bookmarklet generator is minimal but a fine tool
to turn test code into a bookmarklet (by pasting the test CSS and
copying bookmarklet code). That bookmarklet can then be pro‐
vided to any framework user, along with a way to report problems.

## Documentation

Though not technically a part of the development process, docu‐
mentation must be discussed. Anchoring documentation where the
development happens has many advantages, from increasing the
chances that it’s actually done, to being more comprehensive and
accurate because it’s fresh on the mind.

There are several ways to document, but one of the more effective
ones is using a prototype for this purpose too. Sample contents can
be turned into documentation describing the page types and ele‐
ments they’re forming, but it’s also possible to use hover-style info
boxes that share background information and explain the code. (A
properly maintained prototype enriched this way may even do most
of the lifting of any framework site!)

Documentation begins in the code, however, and there, too, we need
to exercise discipline. Our coding guidelines should underline this;
documentation standards like CSSDOC and JSDOC, as well as tools
that automatically pull such documentation from our code, can be
of great help.

The idea behind documentation is to make life easier for ourselves,
our colleagues, framework users, and any people interested in the
work. Thus, making it part of the development process goes a long
way.

## Logistics

Our journey, now that we diligently worked through everything rel‐
evant to frameworks, is soon over. A bonus aspect concerns logis‐
tics. We have covered a few pieces that can be considered logistics:

* Coding guidelines
* Quality-control tools
* Documentation

What we haven’t touched are:

* Framework development plans or roadmaps
* Version control systems (like Git, Mercurial, or Subversion)
* Request and bug management systems (like Bugzilla)
* Framework sites (public for external frameworks) with news feeds
* Mailing lists for
** Developers (framework development team)
** Users (open to everyone interested)
** Announcements (low-volume essentials which should go to
the developers and users lists, too)
* Trackers for live implementations

A framework site and an announcements list are particularly note‐
worthy, as they can pay good dividends to framework owners and
developers. The site serves as a hub for information and documenta‐
tion. An announcements list is indispensable to inform customers
about new releases and guide framework users.

Support also falls into the logistics category. It does not get more
attention here because, for one, we “embed” support at several land‐
marks along the way—in quality goals and principles, in documen‐
tation and logistics—and for another, support is more of a tangential
topic that depends on the complexity and circumstances of the
framework and the problems it tries to solve.

D> To repeat, for expert framework development, we need
to pay special attention to:
D> 
D> * Principles
D> * A prototype
D> * Quality management
D> * Maintenance
D> * Documentation
D> * Logistics
D> 
D> As these are ordered in descending order of impor‐
tance, our frameworks can probably survive with poor
support and gaping docs, but sacrifices in vision, test‐
ing, and commitment will break their necks.