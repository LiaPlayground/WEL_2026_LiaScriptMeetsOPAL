# Der Prompt für die Live-Demo

Dieser Text wird in Block 3 („Die Werkstatt") vor Publikum in ein KI-Werkzeug
eingegeben. Er enthält bewusst **keine LiaScript-Syntax** — das ist Teil der
Botschaft: Die Lehrperson beschreibt das Lernziel, nicht die Technik.

## Wortlaut

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

## Hinweise für die Bühne

**Vor der Eingabe laut vorlesen.** Das Publikum soll hören, dass der Auftrag in
normaler Sprache formuliert ist — keine Fachbegriffe, keine Syntax.

**Den fehlenden Kontext benennen.** Der Prompt sagt nichts über die konkrete
Vorlesung, den Studiengang oder das Vorwissen der Gruppe. Genau daraus
entstehen die Schwächen, die in Schritt 3 korrigiert werden. Das lässt sich
vorab ankündigen: *„Achten Sie darauf, was ich hier alles nicht sage."*

**Wenn der Skill verfügbar ist**, kann die Generierung mit dem
`liascript-course`-Skill erfolgen (liegt in `.claude/skills/liascript-skill/`).
Dann ist die Syntax verlässlich korrekt, und die Schwächen liegen dort, wo sie
didaktisch hingehören: im Inhalt.

## Fallback-Kette

| Wenn … | … dann |
|---|---|
| Generierung läuft | live weitermachen |
| Netz oder API fällt aus | `01_rohentwurf.md` öffnen |
| Zeit wird knapp | direkt zu `03_final.md` springen |
