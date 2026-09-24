# Modulares Prompting

Bezug zur Dissertation: Abschnitt 12.5.

## Ansatz

Das modulare Prompting verteilt die Instruktionen des monolithischen Prompts auf einen gemeinsamen Grundlagentext und fünf Arbeitsmodule. Für jeden Arbeitsschritt wird eine neue Konversation begonnen. Die forschende Person stellt die Eingaben zusammen, prüft die Modellvorschläge und entscheidet, welche Ergebnisse in den nächsten Arbeitsschritt eingehen.

Die Aufteilung folgt den Aufgaben des untersuchten Arrangements. Diskursorganisation, Textsortenbestimmung und Zusammenfassung sind dabei Teil der reflektierenden Interpretation, nicht zusätzliche Verfahren neben ihr.

## Dateien

| Datei | Funktion |
|---|---|
| [EXP-M0-Grundlagen.md](EXP-M0-Grundlagen.md) | Gemeinsamer Grundlagentext für alle Arbeitsschritte |
| [EXP-M1-Formulierende-Interpretation.md](EXP-M1-Formulierende-Interpretation.md) | Formulierende Interpretation mit Ober- und Unterthemen |
| [EXP-M2-Diskursorganisation.md](EXP-M2-Diskursorganisation.md) | Analyse der Diskursorganisation und des Diskursmodus |
| [EXP-M3-Textsorten.md](EXP-M3-Textsorten.md) | Textsortenmäßige Einordnung der Beiträge |
| [EXP-M4-Reflektierende-Interpretation.md](EXP-M4-Reflektierende-Interpretation.md) | Ausführliche Interpretation unter Einbezug der Vorarbeiten |
| [EXP-M5-Zusammenfassung.md](EXP-M5-Zusammenfassung.md) | Verdichtende Zusammenfassung und offene Fragen |

Die Dateien enthalten die kopierbaren Instruktionstexte einschließlich ihrer Überschriften und Eingabe-/Ausgabeangaben. Die YAML-Metadaten der lokalen Arbeitsdateien wurden entsprechend der Durchführungsanleitung weggelassen. Der übrige Wortlaut wurde nicht verändert.

## Verwendung

Jede neue Konversation erhält den vollständigen Grundlagentext M0, das jeweilige Arbeitsmodul und den Transkriptausschnitt. Je nach Arbeitsschritt werden außerdem die zuvor geprüften Ergebnisse beigefügt.

### Vorgesehene Abfolge

| Arbeitsschritt | Eingaben zusätzlich zu M0, Arbeitsmodul und Transkriptausschnitt |
|---|---|
| M1 – Formulierende Interpretation | Keine Vorarbeiten |
| M2 – Diskursorganisation | Konsolidierte formulierende Interpretation aus M1 |
| M3 – Textsorten | Konsolidierte formulierende Interpretation aus M1; das Ergebnis von M2 wird nicht beigefügt |
| M4 – Reflektierende Interpretation | Konsolidierte Ergebnisse aus M1, M2 und M3 |
| M5 – Zusammenfassung | Konsolidierte Ergebnisse aus M1, M2, M3 und M4 |

Die Modellvorschläge werden innerhalb der jeweiligen Konversation am Transkript und unter methodischen Gesichtspunkten geprüft. Rückfragen und Überarbeitungen bleiben in dieser Konversation. Als konsolidierte Fassung wird der von der forschenden Person geprüfte und für die Weiterarbeit ausgewählte Text gesichert. Diese Fassung wird anschließend den vorgesehenen Folgeschritten beigefügt, nicht der gesamte bisherige Gesprächsverlauf.

Die Tabelle beschreibt die vorgesehene Arbeitsordnung. Der tatsächliche Durchlauf, die Interventionen und die Abweichungen von dieser Ordnung werden in Abschnitt 12.5 ausgewertet.

## Dokumentation und Material

Die Module wurden aus dem monolithischen Prompt v2 entwickelt. Die vorliegende Sammlung dokumentiert die in Abschnitt 12.5 beschriebene Modulanordnung; sie enthält keine nachträglich methodisch verbesserte Fassung. Spätere Überarbeitungen werden gesondert gekennzeichnet.

Im untersuchten Durchlauf wurde eine Passage aus der Gruppendiskussion Achondrit verwendet. Transkripte, Gesprächsexporte und fallbezogene Ergebnisdateien sind nicht Bestandteil dieser Veröffentlichung. Für eine eigene Verwendung muss ein zur Verarbeitung freigegebener Transkriptausschnitt gesondert bereitgestellt werden.

Die erzeugten Interpretationsvorschläge sind am Material und mit den Verfahren der Dokumentarischen Methode zu prüfen.

[Zur Übersicht](../README.md)
