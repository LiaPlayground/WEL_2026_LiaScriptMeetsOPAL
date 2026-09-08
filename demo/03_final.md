<!--
author:   Sebastian Zug
email:    sebastian.zug@informatik.tu-freiberg.de
version:  1.0.0
language: de
narrator: Deutsch Female

comment:  Wie Bubble Sort funktioniert — und warum das Verfahren so heißt.
          Einstiegskurs für das erste Semester, entstanden als Live-Demo
          auf der WeL'26.

tags:     Informatik, Algorithmen, Sortierverfahren, OER

logo:     https://github.com/LiaPlayground/Saechsischer_Schulinformatik_Tag_2026/blob/main/pic/LiaScript_Meets_OER.png?raw=true

license:  https://creativecommons.org/licenses/by/4.0/

persistent: true

import: https://raw.githubusercontent.com/LiaTemplates/Pyodide/master/README.md
-->

[![LiaScript](https://raw.githubusercontent.com/LiaScript/LiaScript/master/badges/course.svg)](https://liascript.github.io/course/?https://raw.githubusercontent.com/LiaPlayground/WEL_2026_LiaScriptMeetsOPAL/main/demo/03_final.md)

# Bubble Sort

## Ein Problem, das Sie kennen

Sie haben eine Teilnehmendenliste mit 200 Namen — in der Reihenfolge, in der
sich die Leute angemeldet haben. Jetzt sucht jemand den Eintrag „Neumann".

     {{1}}
<section>

**Unsortiert** müssen Sie im Zweifel alle 200 Zeilen durchsehen.

**Sortiert** schlagen Sie ungefähr in der Mitte auf, sehen „M…", blättern nach
hinten — und sind nach etwa acht Schritten da.

</section>

     {{2}}
<section>

> [!IMPORTANT]
> **Sortieren ist die Vorarbeit, die das Suchen billig macht.**
>
> Deshalb ist es eine der meistuntersuchten Operationen der Informatik — und
> deshalb schauen wir uns an, wie ein Computer das eigentlich anstellt.

</section>

--{{0}}--
Bevor wir über Algorithmen sprechen, ein Problem, das Sie kennen: Eine Liste
mit zweihundert Namen, unsortiert, und Sie suchen einen bestimmten Eintrag.

--{{1}}--
Unsortiert müssen Sie alles durchsehen. Sortiert schlagen Sie in der Mitte auf
und halbieren mit jedem Schritt — nach acht Schritten sind Sie am Ziel.

--{{2}}--
Sortieren ist also die Vorarbeit, die das Suchen billig macht. Schauen wir uns
das einfachste Verfahren an.

## Wie das Verfahren arbeitet

Bubble Sort vergleicht immer nur **zwei benachbarte Elemente** — mehr nicht.

     {{1}}
<section>

**Die Regel:** Stehen zwei Nachbarn in der falschen Reihenfolge, tausche sie.
Dann rücke ein Feld weiter.

</section>

     {{2}}
<section>

Ein Durchlauf durch die Liste `[5, 1, 4, 2]`:

| Vergleich | Liste vorher   | Aktion       | Liste nachher  |
|:---------:|:--------------:|:------------:|:--------------:|
| 5 ↔ 1     | `[5, 1, 4, 2]` | tauschen     | `[1, 5, 4, 2]` |
| 5 ↔ 4     | `[1, 5, 4, 2]` | tauschen     | `[1, 4, 5, 2]` |
| 5 ↔ 2     | `[1, 4, 5, 2]` | tauschen     | `[1, 4, 2, 5]` |

</section>

     {{3}}
<section>

> [!NOTE]
> **Beobachtung:** Die `5` ist nach einem Durchlauf ganz hinten — sie ist wie
> eine Blase nach oben gestiegen. Daher der Name.
>
> Und: Die letzte Position ist damit **endgültig fertig**. Der nächste
> Durchlauf kann sie überspringen.

</section>

     {{4}}
<section>

**Wann ist Schluss?** Wenn ein kompletter Durchlauf ohne einen einzigen Tausch
vergeht, ist die Liste sortiert — dann kann das Verfahren aufhören.

</section>

--{{0}}--
Das Verfahren ist verblüffend einfach: Es schaut immer nur auf zwei
benachbarte Elemente.

--{{1}}--
Die Regel lautet: Stehen die beiden in der falschen Reihenfolge, tausche sie,
und rücke dann ein Feld weiter.

--{{2}}--
Verfolgen wir einen Durchlauf. Die Fünf wird mit jedem Vergleich weiter nach
rechts geschoben.

--{{3}}--
Und hier sehen Sie, woher der Name kommt: Die größte Zahl steigt auf wie eine
Blase. Wichtig ist die zweite Beobachtung — die hinterste Position ist jetzt
endgültig fertig.

--{{4}}--
Und das Verfahren weiß selbst, wann es fertig ist: Sobald ein ganzer Durchlauf
ohne Tausch vergeht, ist die Liste sortiert.

## Im Code nachvollzogen

Der folgende Code gibt nach **jedem Durchlauf** den Zwischenstand aus — so
sehen Sie das Verfahren arbeiten, statt nur das Endergebnis zu betrachten.

```python
zahlen = [5, 1, 4, 2, 8]
print(f"Start:       {zahlen}")

for i in range(len(zahlen)):
    getauscht = False

    for j in range(len(zahlen) - i - 1):
        if zahlen[j] > zahlen[j + 1]:
            zahlen[j], zahlen[j + 1] = zahlen[j + 1], zahlen[j]
            getauscht = True

    print(f"Durchlauf {i + 1}: {zahlen}")

    if not getauscht:
        print("→ keine Vertauschung mehr, fertig!")
        break
```
@Pyodide.eval

> [!TIP]
> **Probieren Sie es aus:** Ändern Sie die Startliste auf `[1, 2, 4, 5, 8]` —
> also bereits sortiert. Wie viele Durchläufe braucht das Verfahren dann?

--{{0}}--
Jetzt der Code. Achten Sie auf die Ausgabe nach jedem Durchlauf — und auf die
Variable "getauscht", die dafür sorgt, dass wir früh aufhören können. Ändern
Sie ruhig die Startwerte und lassen Sie es noch einmal laufen.

## Selbst ausprobieren

??[Sortier-Visualisierung](https://www.sortvisualizer.com/bubblesort/ "Bubble Sort Schritt für Schritt")

> Starten Sie die Visualisierung und beobachten Sie, wie sich der rechte Rand
> der Liste mit jedem Durchlauf um ein Feld nach links schiebt.

## Haben Sie es verstanden?

Die Liste `[3, 7, 1, 9]` wird mit Bubble Sort sortiert. Wie sieht sie **nach
dem ersten vollständigen Durchlauf** aus?

[( )] `[1, 3, 7, 9]`
[(X)] `[3, 1, 7, 9]`
[( )] `[7, 3, 9, 1]`
[( )] `[1, 3, 9, 7]`

[[?]] Gehen Sie die drei Vergleiche einzeln durch: 3↔7, dann 7↔1, dann 7↔9.

***
Der Durchlauf im Einzelnen:

- `3 ↔ 7` — richtige Reihenfolge, kein Tausch → `[3, 7, 1, 9]`
- `7 ↔ 1` — falsch herum, tauschen → `[3, 1, 7, 9]`
- `7 ↔ 9` — richtige Reihenfolge, kein Tausch → `[3, 1, 7, 9]`

Die `9` steht nun endgültig hinten. Beachten Sie: Die Liste ist noch **nicht**
fertig sortiert — ein Durchlauf genügt nicht.
***

---

Warum darf Bubble Sort aufhören, sobald ein Durchlauf ohne Vertauschung
vergangen ist?

[( )] Weil dann alle Elemente mindestens einmal verglichen wurden.
[(X)] Weil kein Paar mehr falsch herum steht — und damit die ganze Liste sortiert ist.
[( )] Weil das größte Element seine Position erreicht hat.

[[?]] Was genau bedeutet es, wenn *kein einziger* Nachbar getauscht werden musste?

***
Wenn in einem kompletten Durchlauf kein einziges benachbartes Paar vertauscht
werden musste, dann steht jedes Element in der richtigen Beziehung zu seinem
Nachbarn. Genau das ist die Definition einer sortierten Liste.

Die anderen beiden Aussagen sind zwar richtige Beobachtungen, begründen den
Abbruch aber nicht.
***

## Was Sie mitnehmen

- Bubble Sort vergleicht **benachbarte Paare** und tauscht bei Bedarf.
- Nach jedem Durchlauf steht mindestens ein Element endgültig richtig.
- Ohne Vertauschung im Durchlauf ist die Liste fertig.
- Das Verfahren ist **einfach zu verstehen, aber langsam** — für große
  Datenmengen nimmt man andere Algorithmen.

> [!NOTE]
> Bubble Sort ist deshalb vor allem ein *Lehrbeispiel*: Es zeigt in wenigen
> Zeilen, was ein Sortierverfahren im Kern tut.

--{{0}}--
Zusammengefasst: Bubble Sort vergleicht Nachbarn, tauscht bei Bedarf, und nach
jedem Durchlauf steht ein weiteres Element endgültig richtig. Das Verfahren ist
leicht zu verstehen, aber langsam — deshalb ist es vor allem ein Lehrbeispiel.

## Lizenz und Nachnutzung

[![CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

Dieser Kurs ist eine Offene Bildungsressource (OER) unter
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — frei nutzbar,
anpassbar und teilbar, auch kommerziell, bei Namensnennung.

> **„Bubble Sort"** von Sebastian Zug (TU Bergakademie Freiberg), lizenziert
> unter [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

> [!NOTE]
> **Entstehungsgeschichte:** Die erste Fassung dieses Kurses wurde am
> 20. August 2026 auf der WeL'26 an der Hochschule Zittau/Görlitz live mit
> KI-Unterstützung erzeugt und anschließend fachlich überarbeitet.
>
> Der Quelltext ist eine einzige Markdown-Datei — Sie können sie kopieren,
> ändern und für Ihre eigene Lehrveranstaltung anpassen.
