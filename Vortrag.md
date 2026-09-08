<!--
version:  0.2.0
language: de

narrator: Deutsch Female

tags: Vortrag, OPAL, LiaScript, OER, KI

comment:  WeL'26 — LiaScript meets OPAL. Wie aus einer Textdatei ein
          interaktiver Kurs wird, wie KI beim Schreiben hilft und wie
          das Ergebnis nach OPAL kommt.
          Vortragender: Sebastian Zug (TU Bergakademie Freiberg).

author:   Sebastian Zug

import: https://raw.githubusercontent.com/LiaTemplates/LiveEdit-Embeddings/refs/tags/0.0.1/README.md
import: https://raw.githubusercontent.com/LiaTemplates/Pyodide/master/README.md

persistent: true

edit: true

@style
.cols {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  gap: 2rem;
}

.cols > * {
  flex: 1;
  min-width: 280px;
}
@end

-->

# LiaScript meets OPAL

<h2>„Ein Kurs ist Text — deshalb kann eine KI ihn schreiben.“</h2>

<div class="cols">
<div>

<h3>Prof. Dr. Sebastian Zug</h3>

<h4>TU Bergakademie Freiberg, Institut für Informatik</h4>

> __WeL'26 — Werkstatt eLearning__
>
> __Hochschule Zittau/Görlitz, 20. August 2026__

</div>
<div>

![OER](https://github.com/LiaPlayground/Saechsischer_Schulinformatik_Tag_2026/blob/main/pic/LiaScript_Meets_OER.png?raw=true "OER-Logo — Quelle: Jonathasmello, Eigenes Werk, CC BY 3.0, [https://commons.wikimedia.org/w/index.php?curid=18460156](https://commons.wikimedia.org/w/index.php?curid=18460156), erweitert um das LiaScript-Logo")

</div>
</div>

---

<!-- class="reference" -->
> Dieser Foliensatz steht unter einer Creative-Commons-Lizenz (CC BY 4.0). Der
> Quelltext liegt auf [GitHub](https://github.com/LiaPlayground/WEL_2026_LiaScriptMeetsOPAL).

--{{0}}--
Herzlich willkommen! In der nächsten Stunde zeige ich Ihnen, wie aus einer
einfachen Textdatei ein interaktiver Kurs wird — und wie eine KI Ihnen dabei
die erste Fassung schreibt. Am Ende steht das Ergebnis in OPAL.


# Was Sie hier gerade sehen

> [!IMPORTANT]
> **Dieser Vortrag ist kein PowerPoint. Er ist eine Textdatei.**

Eine einzige Markdown-Datei, die in Ihrem Browser gerendert wird. Kein Server,
keine Installation, kein Konto.

--{{0}}--
Bevor wir über LiaScript sprechen, ein Hinweis in eigener Sache: Was Sie gerade
sehen, ist selbst ein LiaScript-Kurs. Keine Präsentationssoftware, sondern eine
Textdatei auf GitHub, die Ihr Browser darstellt. Sie können sie sofort öffnen.

     {{1}}
**Öffnen Sie den Vortrag auf Ihrem eigenen Gerät:**

     {{1}}
[qr-code](https://liascript.github.io/course/?https://raw.githubusercontent.com/LiaPlayground/WEL_2026_LiaScriptMeetsOPAL/main/Vortrag.md "Diesen Vortrag im Browser öffnen")

--{{1}}--
Scannen Sie gern den Code. Alles, was Sie heute sehen, können Sie danach
nachlesen und weiterverwenden — die Materialien stehen unter einer offenen
Lizenz.

     {{2}}
**Unser Weg durch die nächsten 60 Minuten**

     {{2}}
1. **Drei Ideen** — was LiaScript im Kern ausmacht
2. **Eine Werkstatt** — wir lassen eine KI live einen Kurs schreiben
3. **Der Weg nach OPAL** — drei Varianten, eine Empfehlung

--{{2}}--
Wir gehen in drei Schritten vor. Zuerst die Konzepte — kompakt, das dauert
keine Viertelstunde. Dann der Hauptteil: Wir erzeugen gemeinsam einen Kurs, mit
KI-Unterstützung, live. Und zum Schluss bringen wir das Ergebnis nach OPAL.


# Drei Ideen

> [!IMPORTANT]
> **LiaScript ist Markdown — erweitert um genau die Elemente, die für
> interaktive Lehre fehlen.**

Markdown kennen viele bereits: aus GitHub, aus Obsidian, oder von der
Sternchen-Schreibweise in Messengern. LiaScript nimmt diese vertraute
Textsprache und ergänzt sie um **drei Kernkonzepte**.

--{{0}}--
Kommen wir zu den Konzepten. LiaScript baut auf Markdown auf — einer
Textauszeichnung, die viele von Ihnen schon einmal gesehen haben. Und es
ergänzt drei Ideen, die für Lehre entscheidend sind.

## Idee 1 — Inhalt und Darstellung sind getrennt

> __Alles wird als reiner Text geschrieben. Wie es am Ende aussieht, entscheidet
> der Player — nicht der Autor.__

```markdown @embed.style(height: 550px; min-width: 100%; border: 1px black solid)
# Vom Text zur Darstellung

__Formatierter Text__

Ein Sortierverfahren ist **effizient**, wenn es mit wachsender
Datenmenge nicht ~~überproportional~~ langsamer wird.

__Mathematik__ — einfach in Dollarzeichen setzen:

Bubble Sort benötigt $\mathcal{O}(n^2)$ Vergleiche.

__Tabellen__ — wie in Markdown gewohnt:

| Verfahren      | Vergleiche              | stabil |
| -------------- |:-----------------------:| ------:|
| Bubble Sort    | $\mathcal{O}(n^2)$      | ja     |
| Merge Sort     | $\mathcal{O}(n \log n)$ | ja     |
| Quick Sort     | $\mathcal{O}(n \log n)$ | nein   |
```

> [!NOTE]
> **Warum das zählt:** Wer den Quelltext hat, hat alles. Keine versteckten
> Formate, kein „nur im LMS editierbar", keine Layout-Reste beim Export. Der
> Markdown-Text *ist* das Material — und passt in jedes Repository, jeden
> Mail-Anhang, jeden USB-Stick.

--{{0}}--
Die erste Idee: Sie schreiben nur, was Sie sagen möchten. Wie es dargestellt
wird, entscheidet später der Player. Links sehen Sie den Quelltext, rechts das
Ergebnis — und Sie können links sofort etwas ändern und rechts zusehen.

## Idee 2 — Interaktion gehört zum Inhalt

> __Quizze, Animationen und Selbsttests sind keine Plugins — sie sind Teil der
> Auszeichnungssprache selbst.__

```markdown @embed.style(height: 550px; min-width: 100%; border: 1px black solid)
# Lehre lebt von Interaktion

__Quiz mit automatischer Rückmeldung__

Wie viele Vergleiche braucht Bubble Sort für 4 Elemente
im schlechtesten Fall?

[[6]]
[[?]] Hinweis: In jedem Durchlauf einer weniger — 3 + 2 + 1.

__Animationsstufen__ — wie an der Tafel:

    {{1}}
Erst die Idee: benachbarte Elemente vergleichen,

    {{2}}
dann das Vorgehen: bei falscher Reihenfolge tauschen,

    {{3}}
schließlich die Pointe: der Größte „blubbert" nach oben.
```

> [!NOTE]
> **Vergleich zum LMS-Ansatz:** Ein ONYX-Test lebt *in* OPAL. Verlassen Sie
> OPAL, ist die Aufgabe weg. Ein LiaScript-Quiz lebt im Markdown-Text — und
> reist überall mit.

--{{0}}--
Die zweite Idee: Interaktivität ist keine Erweiterung, sondern Bestandteil der
Sprache. Das Quiz, das Sie rechts sehen, sind drei Zeilen Text. Keine
Datenbank, keine Aufgaben-ID, keine Plugin-Installation.

## Idee 3 — Der Browser ist die Laufzeitumgebung

> __Was der Browser kann, kann LiaScript. Und der Browser kann heute erstaunlich
> viel.__

````markdown @embed.style(height: 550px; min-width: 100%; border: 1px black solid)
<!--
import: https://raw.githubusercontent.com/LiaTemplates/Pyodide/master/README.md
-->

# Der Browser als Plattform

__Sprachausgabe__ — einfach per Tag:

> {{|> Deutsch Female}}
> Willkommen zur Einführung in Sortierverfahren!

__Echtes Python__ — ohne Installation, im Browser:

```python
zahlen = [5, 1, 4, 2, 8]

for i in range(len(zahlen)):
    for j in range(len(zahlen) - i - 1):
        if zahlen[j] > zahlen[j + 1]:
            zahlen[j], zahlen[j + 1] = zahlen[j + 1], zahlen[j]
    print(f"Durchlauf {i + 1}: {zahlen}")
```
@Pyodide.eval
````

> [!NOTE]
> **Warum das zählt:** *Kein lokales Setup.* Die Studentin am eigenen Laptop,
> der Student im Rechnerpool, die Teilnehmerin mit dem Tablet — alle sehen
> denselben Kurs. Nur einen Browser braucht es.

--{{0}}--
Die dritte Idee: Der Browser ist die Ausführungsumgebung. Rechts läuft echtes
Python — nicht simuliert, sondern wirklich ausgeführt, direkt in Ihrem Browser.
Ohne Installation, ohne Server, ohne Administratorrechte.

## Eine Syntax, fünf Medientypen

> [!IMPORTANT]
> **Der Unterschied zwischen einem Link und einer 3D-Simulation sind ein bis
> zwei Zeichen am Zeilenanfang.**

| Schreibweise     | Ergebnis  |
| ---------------- | --------- |
| ` [Titel](URL)`  | Link      |
| `![Titel](URL)`  | Bild      |
| `?[Titel](URL)`  | Audio     |
| `!?[Titel](URL)` | Video     |
| `??[Titel](URL)` | Anwendung |

Dieselbe URL, ein Zeichen mehr — und aus dem Verweis wird eingebetteter Inhalt.

--{{0}}--
Und jetzt der Punkt, der viele überrascht: Multimedia einzubinden ist keine
technische Hürde. Kein Einbettungscode, kein iframe-Gebastel, keine
Plugin-Rechte. Sie schreiben denselben Link wie immer — und stellen ein bis
zwei Zeichen davor.

     {{1}}
**Ein Beispiel: Sortierverfahren visualisiert**

     {{1}}
```markdown
??[Sortier-Visualisierung](https://www.sortvisualizer.com/bubblesort/)
```

     {{1}}
wird zu einer eingebetteten, bedienbaren Anwendung:

     {{1}}
??[Sortier-Visualisierung](https://www.sortvisualizer.com/bubblesort/ "Interaktive Visualisierung von Bubble Sort")

     {{2}}
> [!TIP]
> Merken Sie sich das Fragezeichen — es begegnet uns gleich in der Werkstatt
> wieder, wenn die KI genau diese Schreibweise verwendet.

--{{1}}--
Zwei Fragezeichen machen aus dem Link eine eingebettete Anwendung. Sie sehen
eine Sortier-Visualisierung, die Sie direkt bedienen können — eingebunden mit
einer einzigen Zeile Text.

--{{2}}--
Merken Sie sich diese Schreibweise; sie kommt gleich wieder.


# Die Werkstatt

> [!IMPORTANT]
> **Jetzt drehen wir den Spieß um: Wir schreiben den Kurs nicht — wir lassen
> ihn schreiben.**

--{{0}}--
Kommen wir zum Hauptteil. Bis hierher habe ich Ihnen gezeigt, wie LiaScript
funktioniert. Jetzt die eigentliche Frage: Muss ich das alles selbst schreiben?
Die Antwort lautet: nein. Und das führen wir jetzt live vor.

## Warum ausgerechnet KI und LiaScript zusammenpassen

     {{1}}
**Erinnern Sie sich an Idee 1?**

     {{1}}
Ein LiaScript-Kurs ist **Text**. Kein Binärformat, keine Datenbank, keine
verschachtelte XML-Struktur.

     {{2}}
**Und was können Sprachmodelle am besten?**

     {{2}}
**Text schreiben.** Genau deshalb ist ein LiaScript-Kurs für eine KI eine
dankbare Aufgabe — und ein ONYX-Test nicht.

     {{3}}
> [!NOTE]
> **Die Konsequenz:** Was eine KI erzeugt, können Sie sofort lesen, prüfen und
> korrigieren. Sie brauchen kein Werkzeug dafür — nur einen Texteditor und Ihr
> Fachwissen.

--{{1}}--
Warum passt das zusammen? Erinnern Sie sich an die erste Idee: Ein Kurs ist
Text. Kein proprietäres Format, keine Datenbank.

--{{2}}--
Und was können Sprachmodelle besser als alles andere? Text schreiben. Deshalb
ist ein LiaScript-Kurs eine dankbare Aufgabe für eine KI — während ein
klassischer LMS-Test es nicht ist.

--{{3}}--
Der entscheidende Punkt ist aber ein anderer: Weil das Ergebnis Text ist,
können Sie es lesen und beurteilen. Sie bleiben die Fachperson. Genau das
sehen wir jetzt.

## Schritt 1 — Der Auftrag

> **Aufgabe an die KI:** Erzeuge einen kurzen LiaScript-Kurs zum Thema
> *Bubble Sort* für Studierende im ersten Semester.

     {{1}}
**Der Prompt im Wortlaut:**

     {{1}}
```text
Erstelle einen LiaScript-Kurs zum Thema Bubble Sort für Studierende
im ersten Semester ohne Vorkenntnisse.

Anforderungen:
- Kurzer Einstieg: Warum sortieren wir überhaupt?
- Erklärung des Verfahrens Schritt für Schritt, mit Animationsstufen
- Ein lauffähiges Python-Beispiel
- Zwei Quizfragen mit Rückmeldung
- Eine eingebettete Visualisierung
```

     {{2}}
> [!TIP]
> **Beachten Sie:** Der Prompt enthält kein einziges Stück LiaScript-Syntax.
> Er beschreibt, was der Kurs leisten soll — nicht, wie er geschrieben wird.

--{{0}}--
Schritt eins: der Auftrag. Ich formuliere jetzt vor Ihren Augen, was der Kurs
enthalten soll.

--{{1}}--
Hier steht der Prompt im Wortlaut. Ein Einstieg, eine schrittweise Erklärung,
lauffähiger Code, zwei Quizfragen, eine Visualisierung.

--{{2}}--
Und beachten Sie: In diesem Auftrag steht keine einzige Zeile LiaScript-Syntax.
Ich beschreibe das Lernziel, nicht die Technik. Genau das ist der Punkt für
Lehrende, die nicht programmieren.

## Schritt 2 — Der Rohentwurf

> [!CAUTION]
> **Achtung: Was jetzt kommt, ist nicht fertig.**
>
> Wir schauen gemeinsam hin — und finden die Schwachstellen.

     {{1}}
**Woran erkennen Sie einen KI-Rohentwurf?**

     {{1}}
| Typisches Muster                   | Warum problematisch                       |
| ---------------------------------- | ----------------------------------------- |
| Formal korrekt, didaktisch flach   | Definition statt Verständnis              |
| Quiz prüft Auswendiglernen         | „Wie heißt das Verfahren?" statt Transfer |
| Beispiel ohne Bezug zur Zielgruppe | Abstrakte Zahlenreihe statt Anwendung     |
| Fachlich fast richtig              | *Fast* ist im Lehrmaterial nicht genug    |

--{{0}}--
Schritt zwei: der Rohentwurf. Ich sage es vorweg — das Ergebnis ist nicht
fertig, und das ist Absicht. Ich zeige Ihnen bewusst nicht das geschönte
Resultat.

--{{1}}--
Denn genau hier liegt Ihre Arbeit. Diese vier Muster sehen Sie fast immer:
formal korrekt, aber didaktisch flach. Quizfragen, die Auswendiglernen prüfen
statt Verständnis. Beispiele ohne Bezug zur Zielgruppe. Und Aussagen, die fast
richtig sind — was bei Lehrmaterial eben nicht genügt.

## Schritt 3 — Die Redaktion

> [!IMPORTANT]
> **Hier passiert die eigentliche Lehre.**

     {{1}}
| Die KI liefert            | Sie liefern                  |
| ------------------------- | ---------------------------- |
| Struktur                  | fachliche Korrektheit        |
| Syntax                    | didaktische Reihenfolge      |
| Formulierungsvorschläge   | Bezug zu *Ihrer* Zielgruppe  |
| lauffähigen Code          | die guten Fragen             |
| Rohmaterial in Minuten    | Verantwortung                |

     {{2}}
> [!NOTE]
> **Das Verhältnis stimmt, wenn Sie den Entwurf kritisch lesen können.** Wer
> ein Thema unterrichten kann, kann auch beurteilen, ob ein Text dazu taugt.
> Genau diese Kompetenz brauchen Sie — und keine andere.

--{{0}}--
Schritt drei, und das ist der wichtigste: die Redaktion. Ich gehe jetzt durch
den Entwurf und korrigiere.

--{{1}}--
Und damit ist die Arbeitsteilung klar: Die KI liefert Struktur, Syntax und
Rohmaterial — in Minuten statt Stunden. Sie liefern fachliche Korrektheit, die
didaktische Reihenfolge, den Bezug zu Ihrer konkreten Zielgruppe und die guten
Fragen.

--{{2}}--
Und die beruhigende Nachricht: Sie brauchen dafür keine neue Kompetenz. Wer ein
Thema unterrichten kann, kann auch beurteilen, ob ein Text dazu taugt.

## Und die drei Ideen?

> [!TIP]
> **Schauen wir noch einmal auf das, was gerade entstanden ist.**

| Was die KI getan hat                             | Welche Idee dahintersteckt                   |
| ------------------------------------------------ | -------------------------------------------- |
| Sie hat **Text** geschrieben                     | **Idee 1** — deshalb konnte sie es überhaupt |
| Sie hat ein **Quiz** in drei Zeilen gesetzt      | **Idee 2** — Interaktion ist Sprachbestandteil |
| Der **Python-Code läuft** im Browser             | **Idee 3** — der Browser als Laufzeitumgebung |
| Sie hat `??[...]` für die Visualisierung genutzt | Die Schreibweise von vorhin                  |

--{{0}}--
Und jetzt schließt sich der Kreis. Schauen Sie, was gerade passiert ist: Die KI
konnte diesen Kurs schreiben, weil ein Kurs Text ist — das war Idee eins. Sie
hat ein Quiz gesetzt, weil Interaktion zur Sprache gehört — Idee zwei. Der Code
läuft im Browser — Idee drei. Und für die Visualisierung hat sie genau die
zwei Fragezeichen verwendet, die ich Ihnen vorhin gezeigt habe.


# Der Weg nach OPAL

>[!CAUTION]
> LiaScript wird im Browser gerendert und ist damit grundsätzlich ohne
> Lern-Managementsystem einsetzbar.

Der Interpreter lädt die Markdown-Datei direkt von GitHub oder einem beliebigen
Webserver und stellt sie dar.

> Warum dann doch ein LMS? Weil Lehrende die Infrastruktur gewohnt sind — und
> weil es Vorteile bringt, den Inhalt im LMS zu haben: Kursstruktur,
> Zugriffskontrolle, Ergebnisrückmeldung.

--{{0}}--
Kommen wir zum letzten Teil: Wie kommt dieser Kurs nun nach OPAL? Vorweg —
LiaScript braucht kein LMS. Der Browser genügt. Aber es gibt gute Gründe, den
Inhalt trotzdem in OPAL zu haben.

## Drei Wege

     {{1}}
**Weg 1 — SCORM**

     {{1}}
Import als Standard-Lernobjekt in OPAL und jedes andere
[SCORM](https://de.wikipedia.org/wiki/SCORM)-fähige LMS.

- **Stärke:** Ergebnisrückmeldung der Teilnehmenden ans LMS.
- **Schwäche:** Bei jeder Änderung neu exportieren und importieren.

     {{2}}
**Weg 2 — Natives Interface**

     {{2}}
OPAL unterstützt LiaScript direkt — ohne Export, ohne iFrame.

- **Stärke:** Einfache Integration, keine URL-Konfiguration, Pflege in OPAL.
- **Schwäche:** Keine Rückmeldung von Nutzendendaten an das LMS.

     {{3}}
**Weg 3 — Git / Codeberg**

     {{3}}
Der Kurs bleibt offen im Netz, OPAL verweist darauf.

- **Stärke:** Maximale Offenheit, echte OER, Versionierung, Kollaboration.
- **Schwäche:** Erfordert ein Repository.

--{{1}}--
Weg eins: SCORM. Das ist die allgemeine Lösung für Lernmanagementsysteme. Der
große Vorteil: Ergebnisse fließen ans LMS zurück.

--{{2}}--
Weg zwei: das native Interface. OPAL kann LiaScript inzwischen direkt anzeigen
— ohne Export, ohne Bastelei. Das ist das Alleinstellungsmerkmal von OPAL.

--{{3}}--
Und Weg drei: Der Kurs liegt offen in einem Repository, OPAL verweist nur
darauf. Das ist der Weg für echte offene Bildungsressourcen.

## Welcher Weg wann?

| Wenn …                                          | … dann                |
| ----------------------------------------------- | --------------------- |
| maximale Offenheit, OER-Verbreitung             | **Git / Codeberg**    |
| Standard-LMS-Objekt, Ergebnis ans LMS           | **SCORM**             |
| Inhalt in OPAL, schnelle Pflege, native Anzeige | **Natives Interface** |

--{{0}}--
Die Faustregel: für offene Verbreitung Git, für ein klassisches LMS-Objekt
SCORM, und wenn der Inhalt bequem in OPAL leben und dort gepflegt werden soll,
das native Interface.


# Einordnung

> [!IMPORTANT]
> **Was heißt das nun für Ihre Lehre?**

--{{0}}--
Bevor wir zu den Fragen kommen, drei Punkte zur ehrlichen Einordnung.

## Was bleibt Ihre Aufgabe

     {{1}}
**Die Grenzen der Maschine**

     {{1}}
- Sie kennt Ihre Studierenden nicht.
- Sie kennt Ihr Curriculum nicht.
- Sie weiß nicht, was letzte Woche dran war.
- Sie erkennt nicht, was Ihre Gruppe schwierig findet.
- Fachlich *fast* richtig genügt nicht.

     {{2}}
**Redaktion ist kein Mehraufwand**

     {{2}}
Es ist die Arbeit, die Sie ohnehin leisten — nur an anderer Stelle. Statt eine
leere Seite zu füllen, prüfen und schärfen Sie einen Entwurf.

     {{2}}
> Die Zeitersparnis liegt nicht im Weglassen, sondern im **anderen Startpunkt**.

--{{1}}--
Erstens die Grenzen: Die KI kennt Ihre Studierenden nicht, Ihr Curriculum
nicht, und sie weiß nicht, was Ihre Gruppe erfahrungsgemäß schwierig findet.
Und fachlich fast richtig ist bei Lehrmaterial eben nicht gut genug.

--{{2}}--
Zweitens: Redaktion ist kein zusätzlicher Aufwand. Es ist die Arbeit, die Sie
ohnehin leisten — nur beginnen Sie nicht mehr bei der leeren Seite.

## Offen heißt nachnutzbar

> [!NOTE]
> **Alles, was Sie heute gesehen haben, steht unter CC BY 4.0.**

**Was das bedeutet**

- frei nutzbar, auch kommerziell
- anpassbar an Ihren Kontext
- weitergebbar an Kolleginnen und Kollegen
- Bedingung: Namensnennung

     {{1}}
**Warum das zu LiaScript passt**

     {{1}}
Ein Kurs, der aus Text besteht, lässt sich tatsächlich weiterverwenden — nicht
nur formal, sondern praktisch. Kopieren, ändern, ergänzen: alles mit einem
Texteditor.

--{{0}}--
Und drittens: Offenheit. Alles, was Sie heute gesehen haben, steht unter einer
Creative-Commons-Lizenz.

--{{1}}--
Aber Lizenz allein genügt nicht — Nachnutzung funktioniert nur, wenn das Format
sie zulässt. Bei Text ist das der Fall.


# Vielen Dank!

**Die drei Ideen**

1. Inhalt und Darstellung sind getrennt
2. Interaktion gehört zum Inhalt
3. Der Browser ist die Laufzeitumgebung

**Der Weg nach OPAL** — SCORM · natives Interface · Git

---

> **Die Kernbotschaft**
>
> Ein Kurs ist Text.
>
> Deshalb kann eine KI ihn schreiben — und deshalb bleiben **Sie** die
> Fachperson, die ihn verantwortet.

---

**Alle Materialien**

[qr-code](https://github.com/LiaPlayground/WEL_2026_LiaScriptMeetsOPAL "Repository mit Vortrag und Demo-Dateien")

**Fragen?**

**Prof. Dr. Sebastian Zug** · TU Bergakademie Freiberg · Institut für Informatik

--{{0}}--
Damit bin ich am Ende. Die drei Ideen, die drei Wege nach OPAL — und die
Botschaft, die mir am wichtigsten ist: Ein Kurs ist Text. Deshalb kann eine KI
ihn schreiben, und deshalb bleiben Sie die Fachperson, die ihn verantwortet.
Vielen Dank für Ihre Aufmerksamkeit — ich freue mich auf Ihre Fragen.
