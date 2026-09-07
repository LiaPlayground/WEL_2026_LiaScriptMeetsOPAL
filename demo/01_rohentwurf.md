<!--
author:   KI-generiert
version:  0.1.0
language: de
narrator: Deutsch Female

comment:  Ein Kurs über den Bubble-Sort-Algorithmus.

import: https://raw.githubusercontent.com/LiaTemplates/Pyodide/master/README.md
-->

# Bubble Sort

Herzlich willkommen zu diesem Kurs über Bubble Sort!

In diesem Kurs lernen Sie den Bubble-Sort-Algorithmus kennen. Bubble Sort ist
ein einfacher Sortieralgorithmus, der wiederholt durch die zu sortierende Liste
läuft, benachbarte Elemente vergleicht und sie vertauscht, falls sie in der
falschen Reihenfolge sind.

## Warum sortieren wir?

Sortieren ist eine der grundlegendsten Operationen in der Informatik. Sortierte
Daten können effizienter durchsucht werden. Es gibt viele verschiedene
Sortieralgorithmen, darunter Bubble Sort, Insertion Sort, Selection Sort, Merge
Sort, Quick Sort und Heap Sort.

Die Sortierung von Daten ist in vielen Anwendungsbereichen von zentraler
Bedeutung und bildet die Grundlage für zahlreiche weiterführende Algorithmen.

## Der Algorithmus

Bubble Sort funktioniert folgendermaßen:

    {{1}}
**Schritt 1:** Vergleiche das erste und das zweite Element.

    {{2}}
**Schritt 2:** Wenn das erste Element größer ist als das zweite, vertausche sie.

    {{3}}
**Schritt 3:** Gehe zum nächsten Paar und wiederhole den Vorgang.

    {{4}}
**Schritt 4:** Wiederhole den gesamten Durchlauf, bis keine Vertauschungen mehr
nötig sind.

Der Algorithmus hat eine Zeitkomplexität von $\mathcal{O}(n^2)$ im
schlechtesten und im durchschnittlichen Fall sowie $\mathcal{O}(n)$ im besten
Fall. Die Speicherkomplexität beträgt $\mathcal{O}(1)$, da die Sortierung
in-place erfolgt.

## Implementierung

Hier ist eine Implementierung in Python:

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
    return arr

daten = [64, 34, 25, 12, 22, 11, 90]
print(bubble_sort(daten))
```
@Pyodide.eval

## Visualisierung

??[Bubble Sort Visualisierung](https://www.sortvisualizer.com/bubblesort/)

## Quiz

Wie heißt der Algorithmus, den wir in diesem Kurs behandelt haben?

[[Bubble Sort]]
[[?]] Der Name kommt vom englischen Wort für Blase.

***
Bubble Sort heißt so, weil die größten Elemente wie Blasen nach oben steigen.
***

Welche Zeitkomplexität hat Bubble Sort im schlechtesten Fall?

[( )] $\mathcal{O}(n)$
[( )] $\mathcal{O}(n \log n)$
[(X)] $\mathcal{O}(n^2)$
[( )] $\mathcal{O}(2^n)$

***
Bubble Sort benötigt im schlechtesten Fall $\mathcal{O}(n^2)$ Vergleiche, da
für jedes der $n$ Elemente die Liste einmal durchlaufen wird.
***

## Zusammenfassung

In diesem Kurs haben Sie den Bubble-Sort-Algorithmus kennengelernt. Sie wissen
nun, wie er funktioniert, wie er implementiert wird und welche Komplexität er
hat.

Vielen Dank für Ihre Teilnahme!
