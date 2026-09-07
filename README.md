# LiaScript meets OPAL

> **Workshop — WeL'26, Hochschule Zittau/Görlitz, 20. August 2026**
> *Wie aus einer Textdatei ein interaktiver Kurs wird — mit KI-Unterstützung*

Vortrag von **Prof. Dr. Sebastian Zug** (TU Bergakademie Freiberg) über
[LiaScript](https://liascript.github.io/) und seine Einbettung in OPAL — von
den Grundkonzepten über die KI-gestützte Kurserstellung bis zur
Veröffentlichung im LMS. Die Präsentation ist selbst ein LiaScript-Kurs.

## Ansehen

- [Vortrag in LiaScript öffnen](https://liascript.github.io/course/?https://raw.githubusercontent.com/LiaPlayground/WEL_2026_LiaScriptMeetsOPAL/main/Vortrag.md)
- Quelltext: [Vortrag.md](Vortrag.md)

## Aufbau

Der Vortrag gliedert sich in sechs Blöcke à 60 Minuten Gesamtdauer:

| Block | Inhalt |
| --- | --- |
| Was Sie hier gerade sehen | Der Vortrag als Textdatei, QR-Codes zum Mitlesen |
| Drei Ideen | Trennung von Inhalt und Darstellung · Interaktion als Sprachmerkmal · Browser als Laufzeitumgebung |
| Die Werkstatt | Live-Erzeugung eines Bubble-Sort-Kurses mit KI, anschließende Redaktion |
| Der Weg nach OPAL | SCORM · natives Interface · Git |
| Einordnung | Grenzen der KI, Redaktionspflicht, OER-Lizenzierung |
| Vielen Dank | Zusammenfassung und Fragen |

## Die Demo-Materialien

Der in Block 3 live erzeugte Kurs liegt in [demo/](demo/) in allen
Bearbeitungsstufen — als Sicherheitsnetz, falls Netz oder KI-Dienst ausfallen:

| Datei | Inhalt |
| --- | --- |
| [00_prompt.md](demo/00_prompt.md) | Der Auftrag an die KI im Wortlaut |
| [01_rohentwurf.md](demo/01_rohentwurf.md) | KI-Rohentwurf mit typischen Schwächen |
| [02_ueberarbeitet.md](demo/02_ueberarbeitet.md) | Nach der fachlichen Redaktion |
| [03_final.md](demo/03_final.md) | Endfassung mit OER-Metadaten |
| [REDAKTION.md](demo/REDAKTION.md) | Regieanweisung: die vier Schwächen und ihre Korrektur |

Der Bubble-Sort-Kurs lässt sich auch einzeln öffnen:
[Endfassung ansehen](https://liascript.github.io/course/?https://raw.githubusercontent.com/LiaPlayground/WEL_2026_LiaScriptMeetsOPAL/main/demo/03_final.md)

## Konzept

Das Design-Dokument liegt unter
[docs/superpowers/specs/](docs/superpowers/specs/2026-09-07-wel2026-liascript-meets-opal-design.md).

## Lizenz

[![CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

Dieses Werk ist als Offene Bildungsressource (OER) unter
[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
lizenziert — frei nutzbar, anpassbar und teilbar, auch kommerziell, bei
**Namensnennung**.

> **„LiaScript meets OPAL"** von Sebastian Zug (TU Bergakademie Freiberg),
> lizenziert unter [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

Der vollständige Lizenztext liegt in [LICENSE](LICENSE).
