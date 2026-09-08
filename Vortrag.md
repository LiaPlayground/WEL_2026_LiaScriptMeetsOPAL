<!--
version:  0.2.0
language: de

narrator: Deutsch Female

tags: Vortrag, OPAL, LiaScript, OER, KI

comment:  Ein Kurs ist ein Text — KI-unterstützte Erzeugung interaktiver
          Materialien für das sächsische LMS. Workshop auf der WeL'26,
          Hochschule Zittau/Görlitz.
          Vortragender: Sebastian Zug (TU Bergakademie Freiberg).

author:   Sebastian Zug

import: https://raw.githubusercontent.com/LiaTemplates/LiveEdit-Embeddings/refs/tags/0.0.1/README.md

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

[![LiaScript](https://raw.githubusercontent.com/LiaScript/LiaScript/master/badges/course.svg)](https://liascript.github.io/course/?https://raw.githubusercontent.com/LiaPlayground/WEL_2026_LiaScriptMeetsOPAL/main/Vortrag.md)

# LiaScript meets OPAL

<h2>Ein Kurs ist ein Text — KI-unterstützte Erzeugung interaktiver Materialien für das sächsische LMS</h2>

<h4>Prof. Dr. Sebastian Zug, Dr. André Dietrich</h4>

<h4>TU Bergakademie Freiberg, Institut für Informatik</h4>

<div class="cols">
<div>

> __WeL'26 — Werkstatt eLearning__
>
> __Hochschule Zittau/Görlitz, 20. August 2026__

Dieser Foliensatz steht unter einer Creative-Commons-Lizenz (CC BY 4.0). Der Quelltext liegt auf [GitHub](https://github.com/LiaPlayground/WEL_2026_LiaScriptMeetsOPAL).

</div>
<div>

![OER](https://github.com/LiaPlayground/Saechsischer_Schulinformatik_Tag_2026/blob/main/pic/LiaScript_Meets_OER.png?raw=true "OER-Logo — Quelle: Jonathasmello, Eigenes Werk, CC BY 3.0, [https://commons.wikimedia.org/w/index.php?curid=18460156](https://commons.wikimedia.org/w/index.php?curid=18460156), erweitert um das LiaScript-Logo")

</div>
</div>

---

--{{0}}--
Herzlich willkommen! In der nächsten Stunde zeige ich Ihnen, wie aus einer
einfachen Textdatei ein interaktiver Kurs wird — und wie eine KI Ihnen dabei
die erste Fassung schreibt. Am Ende steht das Ergebnis in OPAL.


## Was Sie hier gerade sehen

> [!IMPORTANT]
> **Dieser Vortrag ist selbst ein LiaScript-Dokument und damit eine Textdatei.**

Eine einzige Markdown-Datei, die in Ihrem Browser gerendert wird. Kein Server,
keine Installation, kein Konto.

--{{0}}--
Was Sie gerade
sehen, ist selbst ein LiaScript-Kurs. Keine Präsentationssoftware, sondern eine
Textdatei, die Ihr Browser darstellt. Sie können sie sofort öffnen, editieren und selbst in OPAL teilen.

     {{1}}
**Öffnen Sie den Vortrag auf Ihrem eigenen Gerät:**

     {{1}}
<div class="cols">
<div>

[qr-code](https://liascript.github.io/course/?https://raw.githubusercontent.com/LiaPlayground/WEL_2026_LiaScriptMeetsOPAL/main/Vortrag.md "Diesen Vortrag im Browser öffnen")

</div>
<div>

__… oder abtippen:__

# <https://bit.ly/4cxGLcg>

</div>
</div>

     {{1}}
> [!IMPORTANT]
> **LiaScript definiert 3 Modi für die Darstellung - Lehrbuch, Präsentation, Folien.**

--{{1}}--
Scannen Sie gern den Code — oder tippen Sie die kurze Adresse rechts ab, wenn
Ihnen das lieber ist. Klicken Sie dann rechts oben auf den Button, um den
Online-Editor zu öffnen.

## Agenda

**Unser Weg durch die nächsten 60 Minuten**

     {{0}}
1. **Drei Ideen** — was LiaScript im Kern ausmacht
2. **Eine Werkstatt** — wir lassen eine KI live einen Kurs schreiben
3. **Der Weg nach OPAL** — drei Varianten, eine Empfehlung

--{{0}}--
Wir gehen in drei Schritten vor. Zuerst die Konzepte — kompakt, das dauert
keine Viertelstunde. Dann der Hauptteil: Wir erzeugen gemeinsam einen Kurs, mit
KI-Unterstützung, live. Und zum Schluss bringen wir das Ergebnis nach OPAL.

> Am Ende kennen Sie den Weg, um eigene Materialien KI-gestützt zu generieren, zu editieren und zu publizieren.

# Drei Ideen

> [!IMPORTANT]
> **LiaScript ist Markdown — erweitert um genau die Elemente, die für
> interaktive Lehre fehlen.**

Markdown kennen viele bereits: aus Chat-Apps, von Blog-Editoren, GitHub, usw. - LiaScript nimmt diese vertraute
Textsprache und ergänzt sie um **drei Kernkonzepte**.

--{{0}}--
LiaScript baut auf Markdown auf — einer
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
# Der Browser als Plattform

__Sprachausgabe__ — einfach per Tag:

> {{|> Deutsch Female}}
> Willkommen zur Lehrveranstaltung!

__Ein 3D-Modell__ — der Familienschacht in Freiberg, drehbar im Browser:

??[Familienschacht Freiberg](https://sketchfab.com/3d-models/familienschacht-freiberg-germany-7c7d30506c554385a4a4321366e2e601 "Quelle: sketchfab.com")
````

> [!NOTE]
> **Warum das zählt:** *Kein lokales Setup.* Die Studentin am eigenen Laptop,
> der Student im Rechnerpool, die Teilnehmerin mit dem Tablet — alle sehen
> denselben Kurs, drehen dasselbe Modell. Nur einen Browser braucht es.
>
> Und was hier ein Grubengebäude ist, kann in Ihrem Fach eine Maschine, ein
> Molekül, eine Schaltung oder eine Messreihe sein.

--{{0}}--
Die dritte Idee: Der Browser ist die Ausführungsumgebung. Rechts sehen Sie den
Freiberger Familienschacht als 3D-Modell — Sie können es drehen und
heranzoomen. Eine Zeile Text im Quelltext, keine Installation, kein Plugin.
Und das ist nur ein Beispiel: Genauso lassen sich Simulationen, Messdaten oder
ausführbarer Programmcode einbetten.

## Ich mag keinen Code!

> [!IMPORTANT]
> **Der Unterschied zwischen einem Link und einer 3D-Simulation sind ein bis
> zwei Zeichen am Zeilenanfang.**

Dieselbe URL, ein Zeichen mehr — und aus dem Verweis wird eingebetteter Inhalt.
Probieren Sie es aus: Ergänzen Sie links ein Zeichen und sehen Sie rechts zu.

````markdown @embed.style(height: 600px; min-width: 100%; border: 1px black solid)
# Systematik hinter den Befehlen

__Ein Link__
+ https://tu-freiberg.de/
+ [TUBAF](https://tu-freiberg.de/)

__Ein externes Bild__ (!)
[image](https://tu-freiberg.de/sites/default/files/2024-04/732_Silber_Calcit_01_HM.jpg)

__Ein Tondokument__ (?)
[sound](https://open.spotify.com/album/69cO89tra0gETaDHwsKZo5)

__Ein Video__ (!?)
[video](https://www.youtube.com/watch?v=TJHEDKSahoM)

__Ein Irgendwas__ (??)
[webapp](https://www.falstad.com/circuit/circuitjs.html?startCircuit=cap.txt)
````

--{{0}}--
Multimedia einzubinden ist keine
technische Hürde. Kein Einbettungscode, kein iframe-Gebastel, keine
Plugin-Rechte. Sie schreiben denselben Link wie immer — und stellen ein bis
zwei Zeichen davor. Ein Ausrufezeichen macht daraus ein Bild, ein Fragezeichen
ein Tondokument, beide zusammen ein Video, zwei Fragezeichen eine beliebige
Webanwendung — unten im Beispiel eine Schaltungssimulation, in der Sie den
Stromfluss tatsächlich laufen sehen. Links steht der Quelltext, rechts das
Ergebnis — und Sie können die Zeichen jetzt selbst ergänzen und zusehen, was
passiert.

# Die Werkstatt

> [!IMPORTANT]
> **Texte sind die Ausgabe von KIs ... und ein LiaScript-Kurs ist Text - kein Binärformat, keine Datenbank, keine verschachtelte XML-Struktur.

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
> **Beachten Sie:** Der Prompt enthält kein einziges Stück LiaScript-Syntax. Die großen Sprachmodelle kennen diese aber. 
> Der Auftrag beschreibt nur, was der Kurs leisten soll — nicht, wie er geschrieben wird.

--{{0}}--
Schritt eins: der Auftrag. Ich formuliere jetzt vor Ihren Augen, was der Kurs
enthalten soll.

--{{1}}--
Hier steht der Prompt im Wortlaut. Ein Einstieg, eine schrittweise Erklärung,
lauffähiger Code, zwei Quizfragen, eine Visualisierung.

     {{2}}
> [!TIP]
> **Selbst nachlesen:**
> [Prompt im Wortlaut](https://github.com/LiaPlayground/WEL_2026_LiaScriptMeetsOPAL/blob/main/demo/00_prompt.md)

--{{2}}--
Und beachten Sie: In diesem Auftrag steht keine einzige Zeile LiaScript-Syntax.
Ich beschreibe das Lernziel, nicht die Technik. Genau das ist der Punkt für
Lehrende, die nicht programmieren.

## Schritt 2 — Der Rohentwurf

      {{0}}
> [!CAUTION]
> **Achtung: Was jetzt kommt, ist nicht fertig.**
>
> Wir schauen gemeinsam hin — und finden die Schwachstellen.

      {{0}}
> [!TIP]
> **Selbst nachlesen:**
> [Rohentwurf im LiaScript-Editor öffnen](https://liascript.github.io/LiveEditor/?/show/file/https://raw.githubusercontent.com/LiaPlayground/WEL_2026_LiaScriptMeetsOPAL/main/demo/01_rohentwurf.md)

--{{0}}--
Schritt zwei: der Rohentwurf. Ich sage es vorweg — das Ergebnis ist nicht
fertig, und das ist Absicht. Ich zeige Ihnen bewusst nicht das geschönte
Resultat.

     {{1}}
**Was sind wiederkehrende Probleme im KI-Rohentwurf?**

     {{1}}
| Typisches Muster                   | Warum problematisch                       |
| ---------------------------------- | ----------------------------------------- |
| Formal korrekt, didaktisch flach   | Definition statt Verständnis              |
| Quiz prüft Auswendiglernen         | „Wie heißt das Verfahren?" statt Transfer |
| Beispiel ohne Bezug zur Zielgruppe | Abstrakte Zahlenreihe statt Anwendung     |
| Fachlich fast richtig              | *Fast* ist im Lehrmaterial nicht genug    |


--{{1}}--
Denn genau hier liegt Ihre Arbeit. Diese vier Muster sehen Sie fast immer:
formal korrekt, aber didaktisch flach. Quizfragen, die Auswendiglernen prüfen
statt Verständnis. Beispiele ohne Bezug zur Zielgruppe. Und Aussagen, die fast
richtig sind — was bei Lehrmaterial eben nicht genügt. Über den Link können Sie
den Entwurf jederzeit selbst öffnen und die vier Stellen suchen.

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
> **Das Verhältnis stimmt, wenn Sie den Entwurf kritisch hinterfragen.** Wer
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

     {{3}}
> [!TIP]
> **Selbst vergleichen:**
> [Überarbeitete Fassung](https://liascript.github.io/LiveEditor/?/show/file/https://raw.githubusercontent.com/LiaPlayground/WEL_2026_LiaScriptMeetsOPAL/main/demo/02_ueberarbeitet.md)
> · [Endfassung mit OER-Metadaten](https://liascript.github.io/LiveEditor/?/show/file/https://raw.githubusercontent.com/LiaPlayground/WEL_2026_LiaScriptMeetsOPAL/main/demo/03_final.md)

--{{2}}--
Und die beruhigende Nachricht: Sie brauchen dafür keine neue Kompetenz. Wer ein
Thema unterrichten kann, kann auch beurteilen, ob ein Text dazu taugt.

--{{3}}--
Beide Fassungen liegen im Editor nebeneinander — Sie können den Rohentwurf und
das Ergebnis in Ruhe vergleichen und sehen genau, was die Redaktion verändert
hat.

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

     {{1}}
| Weg | Was passiert | Stärke | Schwäche |
| --- | ------------ | ------ | -------- |
| **1 · [SCORM](https://de.wikipedia.org/wiki/SCORM)** | Import als Standard-Lernobjekt — in OPAL und jedem anderen LMS | Ergebnisse fließen ans LMS zurück | Bei jeder Änderung neu exportieren und importieren |
| **2 · Natives Interface** | OPAL zeigt LiaScript direkt an — ohne Export, ohne iFrame | Pflege in OPAL, keine URL-Konfiguration | Keine Rückmeldung von Nutzendendaten |
| **3 · Git / Codeberg** | Der Kurs bleibt offen im Netz, OPAL verweist darauf | Echte OER: Versionierung, Kollaboration | Erfordert ein Repository |

--{{1}}--
Drei Wege stehen Ihnen offen. Erstens SCORM — die allgemeine Lösung für
Lernmanagementsysteme, mit dem Vorteil, dass Ergebnisse ans LMS zurückfließen.
Zweitens das native Interface: OPAL kann LiaScript inzwischen direkt anzeigen,
ohne Export, ohne Bastelei — das ist das Alleinstellungsmerkmal von OPAL. Und
drittens Git: Der Kurs liegt offen in einem Repository, OPAL verweist nur
darauf. Das ist der Weg für echte offene Bildungsressourcen.

     {{2}}
> [!TIP]
> **Alle drei Wege im Detail — direkt in OPAL:**
>
> [LiaScript meets OPAL — der Kurs](https://bildungsportal.sachsen.de/opal/auth/RepositoryEntry/28960423936?4)
> · [Anleitung zur Einbettung](https://bildungsportal.sachsen.de/opal/auth/RepositoryEntry/28960423936/CourseNode/1751769302969809009?1)

--{{2}}--
In OPAL selbst liegt ein Kurs, der alle drei Wege Schritt für Schritt
beschreibt — mit einer bebilderten Anleitung für die Einbettung. Dort finden
Sie auch Beispielmaterialien zum Ausprobieren.

# Einordnung

> [!IMPORTANT]
> **Was heißt das nun für Ihre Lehre?**

--{{0}}--
Bevor wir zu den Fragen kommen, drei Punkte zur ehrlichen Einordnung.

## Macht jetzt die KI alles?

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
> Der Startpunkt und damit Ihre Rolle verändern sich.

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

## Macht KI OER nicht überflüssig?

> [!IMPORTANT]
> **Nachnutzung ist keine Absichtserklärung — sie ist in LiaScript messbar.**

Jeder **Kreis** ist eine Autorin oder ein Autor, jede **Raute** ein
LiaScript-Repository. Eine Linie bedeutet: Diese Person hat zu diesem Material
beigetragen. **Orange** markiert alle, die an mehr als drei Repositories
mitgewirkt haben.

??[Repository-Autoren-Netzwerk der LiaScript-Community](https://liaplayground.github.io/WEL_2026_LiaScriptMeetsOPAL/assets/repo_author_graph.html "Bipartiter Graph aus der Analyse öffentlicher LiaScript-Repositories")

> [!TIP]
> Der Graph lässt sich bedienen: Blenden Sie mit **„Hide authors (André &
> Sebastian)"** die beiden Hauptentwickler aus — das Netz bleibt trotzdem
> zusammenhängend.

--{{0}}--
Aber bleibt das eine Absichtserklärung? Schauen wir auf die Daten. Wir haben
die öffentlichen LiaScript-Repositories ausgewertet: Jeder Kreis ist eine
Autorin oder ein Autor, jede Raute ein Repository, jede Linie ein Beitrag.
Orange markiert Personen, die an mehr als drei Materialien mitgearbeitet
haben. Sie sehen: Das ist keine Sammlung von Einzelkämpfern, sondern ein
verbundenes Netz. Und wenn ich André und mich ausblende, bleibt es bestehen —
die Community trägt sich selbst.


# Vielen Dank!

<h2>„Ein LiaScript-Kurs ist ein Text.“</h2>

<div class="cols">
<div>

**Die drei Ideen**

1. Inhalt und Darstellung sind getrennt
2. Interaktion gehört zum Inhalt
3. Der Browser ist die Laufzeitumgebung

... die in OPAL ihre Wirkung entfalten.

</div>
<div>

<center>

**Alles zum Mitnehmen**

[qr-code](https://liascript.github.io/course/?https://raw.githubusercontent.com/LiaPlayground/WEL_2026_LiaScriptMeetsOPAL/main/Vortrag.md "Vortrag, Demo-Dateien und Anleitungen")

### <https://bit.ly/4cxGLcg>

</center>

</div>
</div>


> **Fragen?**
>
> **Prof. Dr. Sebastian Zug** · [sebastian.zug@informatik.tu-freiberg.de](mailto:sebastian.zug@informatik.tu-freiberg.de)
>
> **Dr. André Dietrich**
>
> TU Bergakademie Freiberg · Institut für Informatik
