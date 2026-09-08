# Regieanweisung für die Redaktion (Block 3, Schritt 3)

Diese Datei ist **nur für den Vortragenden** — sie wird nicht projiziert.
Sie benennt die eingebauten Schwächen von `01_rohentwurf.md` und die Korrektur,
die in `02_ueberarbeitet.md` sichtbar wird.

Die vier Schwächen entsprechen genau der Tabelle in `Vortrag.md`, Abschnitt
„Schritt 2 — Der Rohentwurf". Zeitbudget: etwa 6 Minuten, also rund 90 Sekunden
pro Punkt. Wenn die Zeit knapp wird, sind Punkt 1 und 3 die wichtigsten.

---

## 1 · Formal korrekt, didaktisch flach

**Fundstelle:** Abschnitt „Warum sortieren wir?"

> „Sortieren ist eine der grundlegendsten Operationen in der Informatik.
> Sortierte Daten können effizienter durchsucht werden."

**Das Problem:** Eine Aufzählung von sechs Algorithmennamen, die niemand
braucht, und ein Allgemeinplatz statt eines Anlasses. Die Frage „Warum
sortieren wir?" wird gestellt, aber nicht beantwortet — es fehlt die Erfahrung,
an die sich anknüpfen ließe.

**Was Sie sagen können:**
> *„Das ist nicht falsch. Aber fragen Sie sich: Warum sollte mich das
> interessieren? Der Text nennt keinen einzigen Grund, der mit meinem Leben zu
> tun hat."*

**Die Korrektur:** Ein konkreter Anlass, den jede und jeder kennt — die
Teilnehmendenliste, die nach Nachname sortiert werden soll; die Suche im
Telefonbuch, die nur funktioniert, weil es sortiert ist.

---

## 2 · Quiz prüft Auswendiglernen

**Fundstelle:** Erste Quizfrage

> „Wie heißt der Algorithmus, den wir in diesem Kurs behandelt haben?"

**Das Problem:** Die Antwort steht in der Überschrift. Die Frage prüft, ob
jemand lesen kann — nicht, ob er das Verfahren verstanden hat.

**Was Sie sagen können:**
> *„Diese Frage kann man richtig beantworten, ohne den Kurs gelesen zu haben.
> Sie steht in der Überschrift. Das ist der häufigste Fehler in
> KI-generierten Quizfragen."*

**Die Korrektur:** Eine Frage, die Verständnis verlangt — etwa: Was passiert
nach dem ersten Durchlauf? Oder: Warum ist das Verfahren fertig, sobald ein
Durchlauf ohne Vertauschung bleibt?

---

## 3 · Beispiel ohne Bezug zur Zielgruppe

**Fundstelle:** Python-Block

```python
daten = [64, 34, 25, 12, 22, 11, 90]
```

**Das Problem:** Sieben zufällige Zahlen. Man kann dem Ablauf nicht folgen,
weil man nichts erwartet — und die Ausgabe zeigt nur das Endergebnis, nicht den
Weg dorthin.

**Was Sie sagen können:**
> *„Der Code läuft, er ist korrekt. Aber er zeigt nichts. Ich sehe eine
> sortierte Liste — und habe nicht verstanden, wie sie dahin kam."*

**Die Korrektur:** Weniger Zahlen, dafür Ausgabe nach jedem Durchlauf. Der
Zwischenschritt ist die Lehre, nicht das Endergebnis.

---

## 4 · Fachlich fast richtig

**Fundstelle:** Abschnitt „Der Algorithmus", letzter Absatz

> „Der Algorithmus hat eine Zeitkomplexität von $\mathcal{O}(n^2)$ im
> schlechtesten und im durchschnittlichen Fall sowie $\mathcal{O}(n)$ im besten
> Fall."

**Das Problem:** Das $\mathcal{O}(n)$ im besten Fall gilt **nur für die
optimierte Variante** mit Abbruchbedingung — also die, die stoppt, sobald ein
Durchlauf ohne Vertauschung bleibt. Der darunter abgedruckte Code hat diese
Abbruchbedingung *nicht* und braucht deshalb immer $\mathcal{O}(n^2)$.

Text und Code widersprechen sich also. Das ist die gefährlichste Sorte Fehler:
Beide Teile sind für sich genommen richtig, nur zusammen nicht.

**Was Sie sagen können:**
> *„Hier steht eine Aussage über den besten Fall, die zum abgedruckten Code
> nicht passt. Beides ist einzeln korrekt — nur eben nicht gemeinsam. So etwas
> finden Sie nur, wenn Sie das Thema beherrschen. Genau deshalb bleiben Sie
> unverzichtbar."*

**Die Korrektur:** Entweder die Abbruchbedingung in den Code aufnehmen (besser,
weil sie didaktisch ohnehin interessant ist), oder die Aussage über den besten
Fall streichen.

---

## Zum Schluss des Blocks

Nach der vierten Korrektur zum Block „Der Weg nach OPAL" wechseln.

Wenn Zeit bleibt, lohnt an dieser Stelle ein Satz, der den Kreis zum
Konzeptteil schließt: Die KI konnte den Kurs überhaupt schreiben, weil er Text
ist — das war Idee 1. Sie hat ein Quiz in drei Zeilen gesetzt, weil Interaktion
zur Sprache gehört — Idee 2. Der Code läuft im Browser — Idee 3. Und für die
Visualisierung hat sie genau die zwei Fragezeichen verwendet, die vorhin auf
der Medien-Folie standen.

---

## Nachtrag: der Community-Graph am Ende (Block 5)

Die Folie „Und passiert das auch wirklich?" bettet
`assets/repo_author_graph.html` über GitHub Pages ein:

```
https://liaplayground.github.io/WEL_2026_LiaScriptMeetsOPAL/assets/repo_author_graph.html
```

**Voraussetzung:** GitHub Pages muss für das Repository aktiviert sein —
Settings → Pages → Source: *Deploy from a branch*, Branch `main`, Ordner
`/ (root)`. Zum Stand 08.09.2026 war Pages **noch nicht aktiv**; die URL
liefert bis dahin 404.

Nach dem Aktivieren dauert die erste Veröffentlichung ein bis zwei Minuten.
Prüfen lässt sich das mit:

```bash
curl -sI -o /dev/null -w '%{http_code}\n' \
  https://liaplayground.github.io/WEL_2026_LiaScriptMeetsOPAL/assets/repo_author_graph.html
```

**Fallback ohne Pages:** Die Datei liegt lokal unter
`assets/repo_author_graph.html` und ist eigenständig lauffähig (alle Daten
eingebettet, nur vis-network kommt vom CDN). Im Notfall in einem zweiten
Browsertab öffnen und dorthin wechseln, statt die Folie einzubetten.

**Auf der Bühne:** Der Graph hat einen Schalter *„Hide authors (André &
Sebastian)"*. Ihn zu betätigen ist der stärkste Moment der Folie — das Netz
bleibt zusammenhängend, auch ohne die beiden Hauptentwickler.
