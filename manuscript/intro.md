{sample: true}
# Einleitung

Frameworks prägen das Bild der Webentwicklung der letzten zehn Jahre. Fast jeder Entwickler hat mal ein Framework eingesetzt oder setzt eins ein, und von diesen haben die meisten auch einen Favoriten (Bootstrap?); einige Entwickler haben dazu bereits ein Framework (mit)entwickelt oder entwickeln eins.

Zu einer Zeit, als nicht jedes Stylesheet gleich einen Namen und das Suffix »-Framework« erhielt, hatte ich für meinen Hausverlag O’Reilly 2015 alles zusammengetragen, was mir zur Entwicklung und dem Gebrauch von Frameworks einfiel. Dieses Wissen fußte vor allem auf meiner Erfahrung als Architekt der internen Frameworks von GMX (2003–2006) und Google (2008–2013).

Das Ergebnis war etwas, mit dem ich recht zufrieden war – als jemand, der durchaus mal Dinge »husch-husch« herunterschreibt, ist das tatsächlich nicht mit jedem meiner Werke der Fall. Da O’Reilly sich strategisch aber neu ausgerichtet hatte und das Original, [_The Little Book of HTML/CSS Frameworks_](https://www.oreilly.com/library/view/the-little-book/9781492048121/), nicht für den deutschen Markt vorsah, bat ich 2018 um die Rechte, das Büchlein selbst auf Deutsch herauszubringen. Diesem Wunsch wurde entsprochen, und ich konnte mit Übersetzung und punktuellen Verbesserungen beginnen.

Was Sie in der Hand halten, ist in erster Linie immer noch eine Übersetzung der 2015er Originalausgabe. Aber auch wenn diese hier und da mal hakt – die Jahre gingen nicht spurlos am Material vorüber, und mein Deutsch, siehe spätere Bemerkungen, ächzt auch hier und da –, handelt es sich dabei, ähnlich wie bei [_CSS Optimization Basics_](https://leanpub.com/css-optimization-basics), um ein »lebendes Buch«, und so werden Sie, wenn Sie dieses Buch z.B. über Leanpub oder Google Play Books bezogen haben, Aktualisierungen erhalten. Wenn Sie selbst [Berichtigungen oder Verbesserungen](https://github.com/frontenddogma/html-css-frameworks/issues/) vorschlagen wollen, sind diese jederzeit sehr willkommen und können in das Buch einfließen.

Mehr, nun, vom Jens der früheren Jahre. Viel Vergnügen.

## Einleitung zur Originalausgabe

Dieser Tage basieren viele kommerzielle Websites auf Frameworks, und viele private Websites setzen ebenfalls Frameworks ein. Was aber sind Frameworks, warum und wann benötigen wir sie, und wie gebrauchen und bauen wir sie am besten?

Dieses kleine Buch dreht sich um Frameworks, die auf HTML und CSS basieren. Es konzentriert sich auf HTML und CSS, weil diese auch heute und auch weiterhin am Herzen jedes Webprojekts liegen. Die Prinzipien, die aufgezeigt werden, können jedoch auch auf andere Arten von Frameworks angewandt werden.

Das Ziel dieses Buchs ist, robuste und grundlegende Ideen zu Frameworks zu teilen, wobei etwas Spezifität für langfristigeren Nutzen eingetauscht wird. Wir könnten all die Frameworks analysieren, die dort draußen gerade rumschwirren, aber wie nützlich wäre eine solche Review, wenn es darum geht, sich zu entscheiden, was man für ein Framework benutzen oder schreiben möchte – in fünf Jahren?

Während das Buch versucht, alles abzudecken, kratzt es so einiges aber auch nur an. Webentwicklung ist ein großes Feld geworden. Dazu, wie wir in Kürze sehen werden, dreht sich Framework-Entwicklung um Maßschneidern, und Maßschneidern wiederum hängt von den Umständen ab. Wir kennen die Situation nicht um jedes Projekt da draußen, und so können wir nicht alles verallgemeinern. Und wenn auch in einfacher Sprache geschrieben, richtet sich dieses Buch an Expertenentwickler, die Leute, die darüber entscheiden, ob und wie ein Framework verwendet werden soll, oder ob eins selbst entwickelt wird.

Es ist dabei ebenso von einem Webentwickler geschrieben worden. Ich, Jens, habe während meiner Laufbahn Frameworks für [OPEN KNOWLEDGE](https://www.openknowledge.de/), [GMX](https://www.gmx.net/), [Aperto](https://www.aperto.com/) mit ihren Regierungs- und Geschäftskunden sowie für [Google](https://www.google.com/) entwickelt. In dieser Zeit ist es mir nicht gelungen, die Schnelllebigkeit unserer Branche zu überlisten, aber es sind mir einige Prinzipien, Methoden und Praktiken über den Weg gelaufen, die zu haltbarerem Code führen. Davon profitierten die Frameworks, an denen ich arbeitete, und ich hoffe, davon werden Sie durch dieses Buch ebenfalls profitieren.

I> ### Anmerkung zur Übersetzung
I>
I> Da der Kern dieses Buchs auf dem basiert, was ich ehemals für O’Reilly auf Englisch geschrieben habe, handelt es sich trotz einiger Ergänzungen und Neuerungen in weiten Teilen immer noch um eine Übersetzung. Wo es mir auffiel, habe ich Angleichungen vorgenommen, damit sich das Buch runder liest, aber aus Erfahrung mit dem Umgang mit zwei oder gar drei Sprachen (ich spreche auch etwas Spanisch, und das schlecht) weiß ich, dass manch eigenartige Formulierung solche Rückübersetzungen trotz vieler Schleifen überlebt. Über [Verbesserungsvorschläge](https://github.com/frontenddogma/html-css-frameworks/issues/) freue ich mich sehr.
I>
I> Allgemein benutze ich in meinen Veröffentlichungen gerne ein kollektives »wir«. In diesem Buch fiel es mir als etwas _sehr_ einschließend und umfassend auf, aber ich blieb in Schreibweise und Tonart nah am Original. Schließlich, ein Grund für diese Betonung der Gemeinschaft, _sind_ _wir_ hier technisch interessiert, und sehr wahrscheinlich eint uns sogar, dass wir nicht nur Entwickler, sondern Webentwickler sind. Denn das »wir« will nicht sagen, dass wir unbedingt alles gleich sehen – sondern dass wir ähnliche Berufungen und Leidenschaften haben.
I>
I> Ebenfalls zur Sprache: Ich spreche oft vereinfachend von »Webentwicklern« und benutze auch in anderen Fällen durchaus die jeweils sprachliche kürzere Form. Damit beziehe ich ganz ausdrücklich _alle_ ein, im Fall von Webentwicklern also sowohl Webentwicklerinnen als auch Webentwickler. Ich betrachte es als Selbstverständlichkeit, dass wir andere nicht anders behandeln oder ausschließen, weil diese ein anderes Geschlecht, eine andere sexuelle Orientierung, eine andere Religion oder andere Merkmale oder Vorlieben haben, die keinen Schaden für einen selbst oder andere Menschen bedeuten.