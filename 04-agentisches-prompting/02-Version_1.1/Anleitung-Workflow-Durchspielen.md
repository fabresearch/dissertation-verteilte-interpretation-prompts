---
art: steuerung
titel: "Ablage, Dateinamen und praktische Durchführung"
fassung: ueberarbeitete_arbeitsfassung
instruktionsfassung: ueberarbeitete_arbeitsfassung_2026-09-25
erstellt: 2026-09-24
geaendert: 2026-09-25
status: nicht_erprobt
im_dokumentierten_durchlauf_verwendet: false
---

# Ablage, Dateinamen und praktische Durchführung

Diese Datei wird vom Modell bei der Einrichtung und Fortsetzung eines Durchlaufs verwendet. Sie bestimmt die Ablage der Arbeitsergebnisse und konkretisiert M-INT. Sie enthält keine Forschungsdaten. Die Anweisungen beziehen sich auf die überarbeitete Arbeitsfassung, nicht auf eine rückwirkende Änderung früherer Durchläufe.

## Vorbereitung und Fassungswahl

Stelle alle 43 Dateien dieses Ordners als verfügbares Repertoire bereit. Lade in einer Sitzung nur die gemeinsamen Regeln, die gewählten Referenzen und die tatsächlich benötigten Module und Ergebnisdateien. Der vollständige Bestand ist keine Aufforderung, sämtliche Dateien gleichzeitig in den Gesprächskontext zu übernehmen.

Verwende entweder das ursprüngliche oder das überarbeitete System. Die Kennungen sind absichtlich gleich geblieben, damit die Arbeitsaufträge wiedererkennbar sind. Beide Fassungen gleichzeitig bereitzustellen kann deshalb zu unklarer Auswahl führen. Bei einer neuen Erprobung wird ein eigener Ausgabeordner verwendet; die Ergebnisse früherer Durchläufe werden nicht überschrieben.

Forschungsmaterialien werden gesondert bereitgestellt. Nötig sind je nach Auftrag die Originaltranskripte, Angaben zur Erhebung und bereits vorhandene Ergebnisse. Die Moduldateien ersetzen dieses Material nicht. Die projektspezifische Minimalrahmung wird vor Beginn geprüft; für andere Projekte dient M-GEG-Template als Vorlage. Die enthaltene ausführliche Projektrahmung `_M-GEG-Lieder-Rahmung.md` wird nur für ausdrücklich vereinbarte Einordnungsaufträge geladen, nicht als allgemeiner Erstkontext.

## Durchlaufordner

Vereinbare einen noch nicht belegten relativen Ausgabeordner, normalerweise `durchlauf-<YYYY-MM-DD>`. Bei mehreren neuen Durchläufen am selben Tag ergänze einen eindeutigen Kurznamen. Ein fortgesetzter Durchlauf behält seinen Ordner auch an späteren Tagen. Ein neuer Fall wird darin als weiterer Fallordner geführt.

```text
durchlauf-<datum>/
├── 00-Projektfestlegungen/
├── 00-Sitzungsprotokolle/
├── 00-Dirigent-Protokolle/
├── <Fallname>/
├── falluebergreifend/
└── Zeitleisten/
```

Erzeuge nur tatsächlich benötigte Unterordner und keine leeren Ergebnisdateien. Für die Dokumenterstellung werden die vorhandenen Karl-AI-Werkzeuge verwendet. Ist kein Schreibwerkzeug verfügbar, bleibt die Ausgabe ein Textentwurf; teile dies mit, statt eine Datei zu behaupten. Originalmaterialien bleiben in ihren vorhandenen Quelldateien. M-02 erstellt einen unveränderten Auszug, keine bereinigte Neufassung des Transkripts.

## Dateinamen

Vergib Passagenkennungen pro Fall fortlaufend als `passage-01-<kurzname>`, `passage-02-<kurzname>` usw. Verwende sie bereits bei der ersten Passage, damit später hinzukommende Ausschnitte keine Umbenennung erfordern. Die Kennung bleibt über alle Ergebnisdateien dieser Passage gleich. Umlaute können im Kurzname zur leichteren Übertragung als ae, oe und ue geschrieben werden; der lesbare Passagenname im Dokument bleibt unverändert.

Bei den meisten passagenbezogenen Ergebnissen folgt die Kennung auf den Dateistamm: `03-FI-passage-01-arbeitsweisen.md`. M-02 verwendet die kürzeren Formen `02-passage-01-arbeitsweisen.md` und `02-kontextprotokoll-01-arbeitsweisen.md`; ihre Metadaten tragen dennoch dieselbe Passagenkennung. Nutze keine Namen wie `02-passage-passage-01-...`.

| Auftrag | Dateistamm | Ort und Zusatz |
|---|---|---|
| Projekt-Minimalrahmung | `M-GEG-<Projekt>` | `00-Projektfestlegungen/`; bei unveränderter vorhandener Referenz genügt der Verweis |
| M-GT | `M-GT-Grundlagentheorie-Wahl` | `00-Projektfestlegungen/` |
| M-MET | `M-MET-Methodologie-Wahl` | `00-Projektfestlegungen/` |
| M-MTH | `M-MTH-Methodenwahl` | `00-Projektfestlegungen/` |
| M-00 | `<datum>-s<NN>-<kurzname>` | `00-Sitzungsprotokolle/` |
| M-DIR | `<datum>-s<NN>-dirigent` | `00-Dirigent-Protokolle/` |
| M-01 | `01-Thematischer-Verlauf` | Fallordner, bezogen auf das Gesamttranskript |
| M-02, Passage | `02-passage-<NN>-<kurzname>` | Fallordner |
| M-02, Kontext | `02-kontextprotokoll-<NN>-<kurzname>` | Fallordner |
| M-FI | `03-FI` | Fallordner, Passagenkennung anhängen |
| M-RI-0 | `04-0-Auffaelligkeiten` | Fallordner, Passagenkennung anhängen |
| M-RI-1 | `04-1-Textsortenbestimmung` | Fallordner, Passagenkennung anhängen |
| M-RI-2a | `04-2a-Diskursorganisation` | Fallordner, Passagenkennung anhängen |
| M-RI-2b | `04-2b-Narrative-Strukturanalyse` | Fallordner, Passagenkennung anhängen |
| M-RI | `04-Reflektierende-Interpretation` | Fallordner, Passagenkennung anhängen |
| M-VD-1 | `M-VD-1-Zfri` | Fallordner, Passagenkennung anhängen |
| M-VD-2 | `M-VD-2-Innerfall-Komparation` | Fallordner, bei mehreren Aufträgen Vergleichskennung ergänzen |
| M-VD-3 | `M-VD-3-Fallzusammenfassung` | Fallordner |
| M-TB-1 | `M-TB-1-Sinngenetische-Typiken` | `falluebergreifend/`, Kurzname anhängen |
| M-TB-2 | `M-TB-2-Typologien` | `falluebergreifend/`, Kurzname anhängen |
| M-TB-3 | `M-TB-3-Soziogenetische-Rekonstruktion` | `falluebergreifend/`, Kurzname anhängen |
| M-TB-H | `M-TB-H-Vergleichshorizonte-und-Sampleentwicklung` | `falluebergreifend/`, Kurzname anhängen |
| M-TB-R | `M-TB-R-Relationale-Typenbildung` | `falluebergreifend/`, Kurzname anhängen |
| Q-1 | `Q-1-Begriffsdisziplin` | Beim geprüften Ergebnis, eindeutige Bezugskennung anhängen |
| Q-2 | `Q-2-Standortgebundenheit` | Beim geprüften Ergebnis, eindeutige Bezugskennung anhängen |
| Q-3 | `Q-3-Reichweite` | Beim geprüften Ergebnis, eindeutige Bezugskennung anhängen |
| TL-1 | `TL-1-Sampling-Timeline` | `Zeitleisten/` |
| TL-2 | `TL-2-Typen-und-Theorie-Timeline` | `Zeitleisten/` |

Alle Dateien erhalten die Endung `.md`. Die erste Ergebnisfassung trägt im Frontmatter `version: 1` und `ersetzt: null`; sie benötigt noch kein `_v1` im Namen. Jede Revision erhält `_v2`, `_v3` usw. **am Ende** des Namens vor `.md`. Beispiel: `04-Reflektierende-Interpretation-passage-01-arbeitsweisen_v2.md`. `ersetzt` nennt die vollständige Vorgängerdatei. Die Vorgängerdatei bleibt erhalten.

Sitzungsnummern laufen durchlaufweit über Fälle und Tage weiter. Sitzungsprotokolle erhalten pro Sitzung neue Namen; Versionen ändern nur den Stand derselben Sitzung. Spätere Berichtigungen werden als datierte Ergänzungen einer neuen Sitzung dokumentiert. Die in M-INT geregelte Ausnahme für Zeitleisten bleibt bestehen: Sie übernehmen in jeder Version sämtliche bisherigen Einträge ihres Bandes unverändert. Ein neuer Band hat einen neuen Stamm, etwa `TL-1-Sampling-Timeline-band-02`, und einen Verweis auf den Vorgängerband.

## Metadaten und Status

Ergebnisse tragen die tatsächliche Modulkennung unter `modul`, die Quellen beziehungsweise Eingabeschichten, Datum und die Instruktionsfassung `ueberarbeitete_arbeitsfassung_2026-09-25`. Das Datum des Ergebnisses ist der tatsächliche Arbeitszeitpunkt, nicht automatisch das Erstellungsdatum der Instruktionen. Verwende die zusätzlichen Felder des jeweiligen Moduls. Gleiche Fall- und Passagenkennungen müssen über die Dateien hinweg übereinstimmen.

Die Schemata beginnen mit `status: entwurf`. Nach ausdrücklicher Prüfung kann `status: gepruefte_arbeitsfassung` vereinbart werden. Eine bloße Speicherfreigabe erteilt kein methodisches Gütesiegel. Der Geltungsstatus einzelner Hypothesen steht im Text; er wird nicht aus dem Dateistatus abgeleitet. Die Instruktionsdateien selbst bleiben als noch nicht erprobte Neufassung gekennzeichnet.

## Praktischer Arbeitsgang

1. Kläre Gegenstandsrahmung, Grundlagentheorie, Methodologie und Methode. Bereits getroffene Festlegungen werden weiterverwendet.
2. M-00 eröffnet die konkrete Sitzung; M-DIR begleitet ihre Übergänge.
3. M-01 erschließt das Gesamttranskript. M-02 vereinbart den Ausschnitt und speichert Passage und Kontext gesondert. M-FI reformuliert dessen Themen.
4. M-RI-0 hält Auffälligkeiten fest, M-RI-1 untersucht Textsorten. Für Gruppendiskussionen folgt die Diskursorganisation in M-RI-2a; für geeignete Interviews M-RI-2b. Bereits sinnvoll integrierte Textsortenarbeit muss nicht doppelt ausgeführt werden.
5. Vor M-RI werden Einstiegssequenz, Arbeitsfrage und konkretes Vergleichsmaterial vereinbart. Bei fehlendem Vergleich kann eine ausdrücklich begrenzte Lesart beginnen. Die Ausarbeitung erfolgt bei Bedarf in zwei bis vier Teilen, anschließend als vollständige Ergebnisdatei.
6. Q-1 und Q-2 können begriffliche beziehungsweise standortbezogene Fragen prüfen. Vereinbarte Änderungen müssen in der Ergebnisdatei umgesetzt werden; das Prüfprotokoll allein genügt nicht.
7. M-VD-1 verdichtet die Passage, M-VD-2 vergleicht mehrere Passagen desselben Falls, M-VD-3 fasst den gedeckten Fallzusammenhang zusammen. Bei nur einer Passage können die ersten beiden Schritte entfallen; das Ergebnis bleibt eine passagengebundene Fallskizze.
8. Q-3 prüft den Anspruch der Aussagen. M-TB-1 kann fallübergreifend Dimensionen und Typisierungshypothesen ausarbeiten. Weitere typenbildende Module werden nur bei entsprechender Frage und Materialgrundlage verwendet. Ein Ende auf der Ebene der Dimensionierung ist zulässig.
9. Auswahlentscheidungen und wesentliche Hypothesenänderungen werden in TL-1 beziehungsweise TL-2 festgehalten. M-TB-H unterstützt gezielte weitere Vergleiche oder einen begründeten Verzicht.

Die Reihenfolge ist ein begründeter Normalweg. Rückgänge und bewusst begrenzte Aufgaben sind nach M-INT möglich; fehlende Daten und nicht implementierte Module werden dadurch nicht ersetzt.

## Abschluss und Wiederaufnahme

Nach jedem Modul: Ergebnis zeigen, Speicherort vorschlagen, Freigabe abwarten, vollständig speichern, Werkzeugrückmeldung prüfen und nächsten Schritt anbieten. Vor einem Sitzungswechsel werden sämtliche freigegebenen Ergebnisse und beide Sitzungsprotokolle gesichert. Nicht gespeicherte Arbeit bleibt ausdrücklich offen.

M-00 führt unter „Anschluss für die nächste Sitzung“ das nächste Modul, genaue Eingabedateien mit Fassungen und offene Punkte. Das M-DIR-Protokoll dokumentiert den Entscheidungsverlauf. Die Folgesitzung beginnt mit diesen beiden Dateien und den für den nächsten Schritt erforderlichen Quellen, nicht mit der gesamten wiederholten Chatgeschichte. Prüfe den Anschluss nach Lektüre des nächsten Moduls erneut.
