# LiaScript meets OPAL — WEL 2026

**Design-Dokument, Stand 07.09.2026**

## 1 · Rahmen

| | |
|---|---|
| **Anlass** | WeL'26 — Workshop-Tagung, Hochschule Zittau/Görlitz, Gebäude GI |
| **Termin** | 20.08.2026, 14:45–15:45 Uhr |
| **Raum** | 1.19 |
| **Titel** | LiaScript meets OPAL |
| **Vortragender** | Prof. Dr. Sebastian Zug, TU Bergakademie Freiberg |
| **Dauer** | 60 Minuten inkl. Fragen |
| **Programm** | https://zfe.hszg.de/wel/tagungsprogramm-wel26 |

Der Slot ist im Programm als Workshop ausgewiesen, wird aber bewusst
**demo-getrieben** gestaltet: Der Vortragende führt live vor, das Publikum
schaut zu. Kein Hands-on am eigenen Gerät, damit die Zeit nicht in
Setup-Problemen versickert.

## 2 · Zielgruppe

Zwei Gruppen, beide **ohne Programmiererfahrung** vorausgesetzt:

1. **Lehrende an Hochschulen** — kennen OPAL als Nutzende, schreiben kein
   Markdown, haben in der Regel keinen GitHub-Account.
2. **E-Learning- und Didaktik-Support** — Multiplikatoren, betreuen
   OPAL-Kurse für andere; interessiert an Skalierung, Pflegeaufwand,
   Rechtefragen.

Konsequenz für die Gestaltung: Kein Kommandozeilen-Werkzeug im Hauptpfad,
keine Git-Kenntnisse als Voraussetzung, jede Syntax wird gezeigt statt
erklärt.

## 3 · Kernbotschaft

> **Ein LiaScript-Kurs ist Text. Deshalb kann eine KI ihn schreiben — und
> deshalb bleiben Sie die Fachperson, die ihn verantwortet.**

Der Vortrag führt in die Konzepte ein, erzeugt dann live mit
KI-Unterstützung einen Beispielkurs zu einem Informatikthema, überarbeitet
ihn sichtbar und veröffentlicht ihn in OPAL.

Bewusste didaktische Entscheidung: **Der KI-Rohentwurf wird nicht geschönt.**
Schwächen im generierten Material (wacklige Erklärung, unpassendes Quiz)
werden vorgeführt und korrigiert. Gegenüber Didaktik-Support ist das
glaubwürdiger als ein auf Anhieb perfektes Ergebnis, und es transportiert die
eigentliche Botschaft: KI liefert den Rohstoff, die Lehrperson redigiert.

## 4 · Dramaturgie

Der rote Faden ist eine **Kehrtwende in der Mitte**. Erste Hälfte: LiaScript
als Format. Ab Minute 18 kippt der Vortrag in die Werkstatt — es entsteht ein
Kurs, den niemand vorbereitet hat.

| Block | Min | Inhalt |
|---|---|---|
| 1 · Aufschlag | 0–5 | Dieser Vortrag ist selbst eine Textdatei · QR-Codes zu OPAL und GitHub |
| 2 · Konzepte | 5–18 | Drei Kernideen + Link-Eskalation |
| 3 · Werkstatt ⭐ | 18–35 | KI generiert Bubble-Sort-Kurs, Live-Redaktion |
| 4 · Nach OPAL | 35–48 | Git / SCORM / natives Interface am erzeugten Kurs |
| 5 · Einordnung | 48–55 | Grenzen, Redaktionspflicht, OER-Lizenz |
| 6 · Fragen | 55–60 | |

Die Werkstatt erhält mit 17 Minuten knapp ein Drittel der Zeit. Das ist
beabsichtigt: Kürzer wirkt die KI-Generierung wie ein Gimmick statt wie ein
Arbeitsweg.

## 5 · Inhaltliche Bausteine

### 5.1 Die drei Kernideen

Übernommen aus `Opal_Schule_meets_LiaScript/02_Verstehen.md`, gekürzt und mit
neuen Beispielen:

1. **Trennung von Inhalt und Darstellung** — Sie schreiben Text, der Player
   entscheidet über die Form.
2. **Interaktion gehört zum Inhalt** — Quizze und Animationen sind
   Sprachmerkmal, kein Plugin.
3. **Der Browser ist die Laufzeitumgebung** — was der Browser kann, kann
   LiaScript.

Zu Idee 3 existieren in den Bestandskursen zwei Formulierungen
(„Laufzeitumgebung" vs. „Erweiterbarkeit über ein Modulsystem" in
`nis2/about-liascript.md`). Für die WEL gilt die **Laufzeitumgebungs-Fassung**:
Vor Lehrenden ohne Programmiererfahrung ist „kein Setup, läuft überall im
Browser" das anschlussfähige Argument, während „Modulsystem" nach
Wartungsaufwand klingt.

**Die drei Ideen sind zugleich die Analyse-Brille für die Werkstatt.** Sie
werden nicht vorne abgehandelt und dann vergessen, sondern in Block 3 am
generierten Kurs wieder aufgerufen:

- Die KI schreibt Text → Idee 1, deshalb kann eine KI das überhaupt.
- Die KI setzt ein Quiz in drei Zeilen → Idee 2.
- Der Sortier-Code läuft im Browser → Idee 3.

Das begründet, warum sich ausgerechnet LiaScript für KI-Generierung eignet:
Weil ein Kurs Text ist, ist er das, was Sprachmodelle am besten können. Dieses
Argument verbindet beide Hälften des Vortrags.

### 5.2 Die Link-Eskalation

Eigene Station in Block 2, Vorlage: `LiaScript_WeAreDevelopers2022/README.md`,
Abschnitt „Extensions to Links".

Zuspitzung: **Eine Syntax, fünf Medientypen. Der Unterschied sind ein bis zwei
Zeichen am Zeilenanfang.**

```markdown
 [Titel](URL)   → Link
![Titel](URL)   → Bild
?[Titel](URL)   → Audio
!?[Titel](URL)  → Video
??[Titel](URL)  → eingebettete Anwendung (3D, Simulation, GeoGebra …)
```

Diese Station entkräftet in fünf Zeilen die verbreitete Sorge, Multimedia
einzubinden sei eine technische Hürde (Einbettungscode, iframes,
Plugin-Rechte). Sie ist zugleich Idee 1 und 2 in einem Bild: Der Autor
schreibt, *was* eingebunden wird, der Player entscheidet, *wie*.

Die Antiken-Beispiele der Vorlage werden durch Informatik-/Sortier-Bezug
ersetzt, damit die Station auf die Demo hinführt statt ein zweites Thema zu
eröffnen.

**Rückgriff in der Werkstatt:** Die KI wird gebeten, eine
Sortier-Visualisierung einzubetten, und schreibt `??[…]`. Das Publikum
erkennt die Syntax von zehn Minuten zuvor wieder — der Kreis zwischen
Konzeptteil und Werkstatt schließt sich.

### 5.3 Die Werkstatt (Block 3)

Thema des generierten Kurses: **Bubble Sort**. Begründung: visuell erklärbar,
erlaubt Animation, ausführbaren Code und Quiz, und ist auch für Fachfremde
intuitiv — Sortieren versteht jeder.

Ablauf in drei sichtbaren Stufen:

1. **Prompt** — der Vortragende formuliert die Anforderung vor Publikum.
2. **Rohentwurf** — die KI erzeugt einen LiaScript-Kurs; Schwächen bleiben
   sichtbar.
3. **Redaktion** — der Vortragende korrigiert fachlich und didaktisch, der
   Kurs läuft.

### 5.4 Nach OPAL (Block 4)

Übernommen aus `OPAL_Andwendertag_2026/Vortrag.md`, vorgeführt am soeben
erzeugten Kurs:

| Wenn … | … dann |
|---|---|
| maximale Offenheit, OER-Verbreitung | **Git / Codeberg** |
| Standard-LMS-Objekt, Ergebnis ans LMS | **SCORM** |
| Inhalt in OPAL, schnelle Pflege, native Anzeige | **Natives Interface** |

### 5.5 Einordnung (Block 5)

- Grenzen der KI-Generierung: Fachliche Korrektheit bleibt Aufgabe der
  Lehrperson.
- Redaktionspflicht als Berufsbild, nicht als Mehraufwand.
- OER-Lizenzierung (CC BY 4.0) und Nachnutzbarkeit.

## 6 · Technische Umsetzung

### 6.1 Aufbau

Der Vortrag ist selbst ein LiaScript-Kurs, Hauptdatei `Vortrag.md` im
Projektwurzelverzeichnis. Konventionen aus `OPAL_Andwendertag_2026`
übernommen:

- LiaScript-Header mit `language: de`, `narrator: Deutsch Female`,
  `persistent: true`, `edit: true`
- `import:`-Blöcke für benötigte Templates
- `@style`-Block mit `.cols`-Klasse für Zweispalter
- Grad-Bilder (`pics/grad/N.png` aus `MINT-the-GAP/Aufgabensammlung`) als
  Kapitelmarker
- Zweispalter mit Animationsstufen `{{0-2}}` / `{{1-2}}`
- `style.css` im Projektverzeichnis

### 6.2 Wiederverwendung

| Baustein | Quelle |
|---|---|
| Header, `@style`, Grad-Marker, Zweispalter-Muster | `OPAL_Andwendertag_2026/Vortrag.md` |
| Drei Kernideen | `Opal_Schule_meets_LiaScript/02_Verstehen.md` |
| Link-Eskalation | `LiaScript_WeAreDevelopers2022/README.md` |
| OPAL-Einbettung, „Welcher Weg wann?" | `OPAL_Andwendertag_2026/Vortrag.md` |
| CC-BY-README, LiaPlayground-Deploy | `OPAL_Andwendertag_2026/README.md` |

### 6.3 Fallback-Konzept für die Live-Demo

Die KI-Generierung läuft **wirklich live**, jede Stufe ist jedoch als Datei
vorbereitet. Bei Netz- oder API-Problemen schaltet der Vortragende per Klick
auf die vorbereitete Fassung um, ohne dass das Publikum einen Bruch bemerkt.

Ablage unter `demo/`:

| Datei | Inhalt |
|---|---|
| `demo/00_prompt.md` | Der Prompt im Wortlaut |
| `demo/01_rohentwurf.md` | KI-Rohentwurf inkl. Schwächen |
| `demo/02_ueberarbeitet.md` | Nach der Live-Redaktion |
| `demo/03_final.md` | Endfassung für den OPAL-Export |

Anforderung an die Fallback-Dateien: Sie müssen ohne Netz lauffähig sein und
optisch dem entsprechen, was die Live-Generierung erzeugt hätte.

### 6.4 Veröffentlichung

- GitHub-Repository unter der Organisation `LiaPlayground`
- Aufruf über `https://liascript.github.io/course/?…/Vortrag.md`
- QR-Codes für OPAL-Kurs und GitHub-Repository (Block 1)
- Lizenz CC BY 4.0, `LICENSE` im Repository

## 7 · Abgrenzung

Nicht Gegenstand dieses Vortrags:

- Hands-on-Übungen der Teilnehmenden am eigenen Gerät
- Vollständige LiaScript-Syntaxreferenz
- Vergleich mit H5P, ILIAS, Moodle über das Nötige hinaus
- Installation lokaler Werkzeuge (Editor-Plugins, Exporter-CLI)
