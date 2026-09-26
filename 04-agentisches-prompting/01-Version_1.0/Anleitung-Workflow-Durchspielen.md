---
titel: "Anleitung: v3-Workflow mit dem Projektmaterial durchspielen"
status: anleitung
erstellt: 2026-05-15
basis: "v3-Architektur als verteilte Interpretation"
material: "projektspezifisch · T-/P-Dateien im Modul-Ordner"
tags: [karl-ai, workflow, anleitung, durchspielen, v3]
---

# Anleitung: v3-Workflow mit dem Projektmaterial durchspielen

Diese Anleitung führt dich praktisch durch den v3-Workflow mit deinem Material (Gesamttranskripte und ggf. vorbereitete Passagen als T-/P-Dateien). Sie ist als Begleiter für die Forschungssitzungen gedacht, nicht als methodologisches Handbuch. Die methodologische Substanz steht in den Modul-Dateien selbst, die konzeptuelle Einordnung in [[workflow]] und [[Schritt-fuer-Schritt-Erlaeuterung]].

## Verfahrens-Rahmen für das Sprachmodell (karl ai)

> **Diese Anleitung beschreibt einen verteilten Interpretationsprozess, kein Selbstspiel.**
>
> Das Sprachmodell simuliert die forschende Person an *keiner* Stelle — auch nicht in „Im Dialog zu klären"-Listen, auch nicht in „Was zu beobachten"-Hinweisen, auch nicht in Vorgaben wie „die Passage ist gewählt". Die Anleitung ist *an die forschende Person* gerichtet; das Modell liest sie als Verfahrens-Kontext, *nicht als Ausführungs-Skript*.
>
> Konkret: Wenn unter einem Schritt „Im Dialog zu klären: X, Y, Z" steht, ist das eine Agenda für das Gespräch zwischen Modell und forschender Person — keine Liste von Punkten, die das Modell selbst in einer Antwort abarbeitet. Das Modell macht *einen* Schritt: einen Vorschlag, eine Rückfrage, eine Variante. Dann wartet es auf die reale Antwort der forschenden Person. Die Antwort wird *nicht* antizipiert oder fingiert.
>
> Auch die „Was zu beobachten"-Hinweise sind nicht Aufgabe des Modells, sondern eine Lesehilfe für die forschende Person, die das Modell-Output beurteilt.
>
> Dieser Verfahrens-Rahmen ist in **`M-INT-Verteilte-Interpretation-und-Chat-Output.md`** ausgearbeitet und wird in jeder karl-ai-Sitzung zusammen mit M-STIL als verbindlicher Erstkontext mitgegeben. Dort stehen kanonisch die fünf Verfahrens-Maximen (kein Selbstspiel; Dokumentenspeicher-Sicherung mit Versionierung; Eingabeschichten prüfen, Sprünge sichtbar machen; Modul-Datei vollständig lesen; Mandat-Grenzen), die Sitzungszäsur und das Delta-Prinzip der Protokolle. Jedes operative Modul beginnt mit einer **Modul-Identitätskarte** (Block-Quote nach der H1), die diese Maximen am konkreten Modul konkretisiert.
>
> Die zweite Maxime aus M-INT gilt auch für jeden in dieser Anleitung erwähnten „Output speichern unter"-Pfad: das ist die Anweisung an das Modell, den freigegebenen Output per Create Document an genau dieser Stelle der Durchlauf-Ordnerstruktur anzulegen. Fehlende Ordner legt das Modell per Create Folder an, sobald sie gebraucht werden.

## Was du vor dem Start brauchst

**Im Vault liegen:**

- Gegebenenfalls vorbereitete Passagen als `P-<Fall>-Passage.md` (optional; sonst wählt M-02 aus dem Gesamttranskript)
- Die Gesamttranskripte als `T-<Fall>-Gesamttranskript.md` (für M-01 nötig); die Quelldateien (.rtf/.docx) bleiben außerhalb des Modul-Ordners erhalten
- Die v3-Modul-Dateien in `karl-ai-prompts/_workflow/` mit den vier Vierklang-Verortungs-Schichten: **M-GEG** (projektspezifische Gegenstandstheorie, z. B. `M-GEG-<Projekt>.md`), **M-GT-1/2/3** (Grundlagentheorie), **M-MET-1/2/3** (Methodologie), **M-MTH-1/…** (Methode, z. B. `M-MTH-1-Gruppendiskussionsverfahren.md`)

**Zugang zu einem Sprachmodell:**

Eine karl-ai-Sitzung mit Zugriff auf den Dokumentenspeicher, in dem Modul-Ordner, Materialien und Durchlauf-Outputs liegen. Das Modell liest Module, Material und Eingabeschichten eigenständig über seine Dokumenten-Tools (List Document Nodes, Search Documents, Read Document) und speichert Outputs per Create Document — händisches Kopieren von Modul-Prompts in den Chat ist nicht mehr nötig. Wichtig ist nur, dass der Speicher aktuell ist (Store-Sync: geänderte Modul-Dateien aus dem Vault dort ersetzen). Das Modell sollte ein ausreichend großes Kontextfenster haben, damit die Eingabeschichten (vorherige Modul-Outputs, Vergleichsmaterial, Passage) zusammen reinpassen.

## Vault-Struktur für die Outputs

Für jeden neuen Durchlauf wird ein eigener, datierter Output-Ordner angelegt — etwa `durchlauf-<datum>/` oder `durchlauf-vN/`. Das übernimmt das Modell zu Durchlauf-Beginn selbst per Create Folder (mit deiner Bestätigung); Unterordner folgen, sobald sie gebraucht werden. Im Folgenden steht `<durchlauf>/` als Platzhalter dafür. Frühere Durchläufe liegen archiviert in `_workflow/_archiv-durchlaeufe/`; sie werden nicht überschrieben.

Pro Fall entsteht *eine* reflektierende Interpretation (`04-Reflektierende-Interpretation.md`); Linsen und OR-Synthese sind darin enthalten, es entstehen keine separaten Linsen-/Synthese-Dateien.

```
karl-ai-prompts/
├── _workflow/                            (die Module)
└── <durchlauf>/                          (NEU für diesen Durchlauf)
    ├── 00-Gegenstandstheorie.md          (einmalig, aus M-GEG, projektspezifisch)
    ├── 00-Grundlagentheorie-Wahl.md      (einmalig, aus M-GT)
    ├── 00-Methodologie-Wahl.md           (einmalig, aus M-MET)
    ├── 00-Methodenwahl.md                (einmalig, aus M-MTH)
    ├── 00-Sitzungsprotokolle/            (pro Sitzung eines)
    ├── 00-Dirigent-Protokolle/           (pro Sitzung eines)
    ├── <Fall-1>/
    │   ├── 01-Thematischer-Verlauf.md
    │   ├── 02-Passagenauswahl.md
    │   ├── 03-FI.md
    │   ├── 04-0-Auffaelligkeiten.md
    │   ├── 04-2a-Diskursorganisation.md
    │   ├── 04-Reflektierende-Interpretation.md   (Hauptmodul, integriert; Linsen+Synthese inbegriffen)
    │   ├── M-VD-1-Zfri.md
    │   └── M-VD-3-Fallzusammenfassung.md
    ├── <Fall-2>/                          (analog)
    ├── <weitere Fälle>/                  (analog)
    ├── falluebergreifend/
    │   ├── M-TB-1-Sinngenetische-Typiken.md
    │   ├── M-TB-2-Typologien.md
    │   ├── M-TB-3-Soziogenetische-Rekonstruktion.md
    │   └── M-TB-H-Vergleichshorizonte-und-Sampleentwicklung.md   (nur falls die Schleife ausgelöst wird)
    ├── TL-1-Sampling-Timeline.md         (laufend, eine Datei)
    ├── TL-2-Typen-und-Theorie-Timeline.md (laufend, eine Datei)
    ├── Q-Module-Einsaetze/               (für Q-Module-Outputs)
    └── _Test-Tagebuch.md                 (laufende Beobachtungen zum Durchlauf)
```

## Dateinamen-Schema (verbindlich)

Die Outputs werden nach einem festen Muster benannt. Das ist keine Kosmetik: Der Sitzungs-Tick und die Eingabeschicht-Beschaffung stützen sich auf exakte Dateinamen, und uneinheitliche Namen (etwa ein doppelter Bindestrich oder ein mal vorhandenes, mal fehlendes Versionssuffix) führen dazu, dass eine Folgesitzung die falsche oder gar keine Datei findet. Das Modell benennt jeden Output nach diesem Schema und weicht nicht ab.

**Grundmuster:** `<Stamm>[-passage-NN-<slug>][_vN]`. Der Stamm steht fest pro Modul (siehe Tabelle), das Casing des Stamms wird unverändert übernommen. Der Passage-Teil entfällt, wenn pro Fall nur eine Passage bearbeitet wird; bei mehreren Passagen pro Fall trägt jeder passagenbezogene Output `-passage-NN-<slug>` mit zweistelliger Nummer und kurzem, kleingeschriebenem Themen-Slug (`-passage-01-teil-a-medien-ordnung-haptik`). Das Versionssuffix `_v2`, `_v3` steht immer ganz am Ende, hinter dem Passage-Teil.

| Modul | Stamm |
|-------|-------|
| M-01 Thematischer Verlauf | `01-Thematischer-Verlauf` |
| M-02 Passagenauswahl (extrahierte Passage) | `02-passage` |
| M-02 Kontextprotokoll | `02-kontextprotokoll` |
| M-FI Formulierende Interpretation | `03-FI` |
| M-RI-0 Auffälligkeiten | `04-0-Auffaelligkeiten` |
| M-RI-1 Textsortenbestimmung | `04-1-Textsortenbestimmung` |
| M-RI-2a Diskursorganisation | `04-2a-Diskursorganisation` |
| M-RI-2b Narrative Strukturanalyse | `04-2b-Narrative-Strukturanalyse` |
| M-RI Reflektierende Interpretation (integriert) | `04-Reflektierende-Interpretation` |
| M-VD-1 Zusammenfassung der RI | `M-VD-1-Zfri` |
| M-VD-2 Innerfall-Komparation | `M-VD-2-Innerfall-Komparation` |
| M-VD-3 Fallzusammenfassung | `M-VD-3-Fallzusammenfassung` |
| M-TB-1 Sinngenetische Typiken | `M-TB-1-Sinngenetische-Typiken` (in `falluebergreifend/`) |
| M-TB-2 Typologien | `M-TB-2-Typologien` (in `falluebergreifend/`) |
| M-TB-3 Soziogenetische Rekonstruktion | `M-TB-3-Soziogenetische-Rekonstruktion` (in `falluebergreifend/`) |
| M-TB-R Relationale Typenbildung (optional) | `M-TB-R-Relationale-Typenbildung` (in `falluebergreifend/`) |
| M-TB-H Vergleichshorizonte und Sample-Entwicklung | `M-TB-H-Vergleichshorizonte-und-Sampleentwicklung` (in `falluebergreifend/`) |
| Sitzungsprotokoll (M-00) | `<datum>-s<NN>-<kurzname>` in `00-Sitzungsprotokolle/` (NN = durchlaufweit fortlaufende Sitzungsnummer; pro Sitzung ein eigenes Dokument, kein Fortschreiben) |
| Dirigent-Protokoll (M-DIR) | `<datum>-s<NN>-dirigent` in `00-Dirigent-Protokolle/` (pro Sitzung ein eigenes Dokument, kein Fortschreiben) |
| Timelines | `TL-1-Sampling-Timeline`, `TL-2-Typen-und-Theorie-Timeline` |

Bei den passagenbezogenen Modulen (M-02 bis M-RI sowie M-VD-1) hängt der Passage-Teil an den Stamm: `03-FI-passage-01-teil-a-medien-ordnung-haptik`, `04-0-Auffaelligkeiten-passage-02-teil-b-ki-erste-reaktionen`. Innerfall-Komparation und Fallzusammenfassung sind fallbezogen und tragen keinen Passage-Teil. Wichtig: für die Auffälligkeiten gilt durchgängig `04-0-Auffaelligkeiten`, nicht eine improvisierte RI-0-Schreibung, und für die integrierte RI durchgängig `04-Reflektierende-Interpretation`, nicht `04-RI`.

## Wie eine Modul-Aktivierung praktisch abläuft

Pro Modul folgst du diesem Schema (die Schritte 4–6 sind das Herz der verteilten Interpretation):

1. **Sitzung eröffnen**: Frische karl-ai-Sitzung mit dem Initialprompt starten. Das Modell liest daraufhin `M-STIL` und `M-INT` eigenständig aus dem Dokumentenspeicher und prüft den Durchlauf-Ordner.
2. **Erstkontext klären**: Das Modell liest die vier Vierklang-Verortungs-Dateien (M-GEG, M-GT, M-MET, M-MTH) bzw. ihre Wahl-Protokolle aus dem Durchlauf-Ordner, dazu das letzte Sitzungs- und Dirigent-Protokoll. Du musst nichts einfügen, nur benennen, woran gearbeitet wird.
3. **Modul benennen**: Du nennst das Modul (oder bestätigst den Dirigent-Vorschlag). Das Modell liest die Modul-Datei selbst vollständig aus dem Speicher (Maxime 4) und steigt nach deren Auftakt-Schema ein.
4. **Eingabeschichten beschaffen lassen**: Das Modell holt sich Passage, vorherige Modul-Outputs und Vergleichsmaterial per Read Document selbst. Prüfe nur, ob es die richtigen Dokumente (und die höchsten Versionen) erwischt hat.
5. **Turn-by-turn arbeiten**: Das Modell macht *einen* Schritt — einen Vorschlag, eine Variante, eine Rückfrage. Es antizipiert deine Antwort nicht, es fingiert sie nicht. Du antwortest, das Modell macht den nächsten Schritt. So wird die „Im Dialog zu klären"-Agenda eines Moduls über *mehrere* Modell-Turns abgearbeitet, nicht in einer einzigen Antwort.
6. **Output prüfen und speichern lassen**: Wenn ein Modul seine Gesprächsspur ausgibt, zeigt das Modell den verdichteten Output im Chat lesbar gerendert, nicht als rohen Markdown-Codeblock; die exakte Markdown-Fassung mit Frontmatter steht in der Speicherfassung und wird im Chat nur auf ausdrücklichen Wunsch gezeigt. Du prüfst ihn, dann legt das Modell ihn per Create Document am vorgesehenen Ort im Durchlauf-Ordner an (du bestätigst die Anlage im Tool-Dialog). Revisionen entstehen als neue Version (`…_v2`), nicht durch Überschreiben.
7. **Timelines fortschreiben lassen**: Falls das Modul eine Eintragung verlangt, erzeugt das Modell eine neue Version der Timeline (`TL-1-Sampling-Timeline_v2` etc.), die den gesamten bisherigen Inhalt wörtlich übernimmt und den Neueintrag ergänzt. Alteinträge werden nicht nachträglich geglättet (Prinzip der vergangenen Gegenwarten). Wird der Bestand für die wörtliche Übernahme in einer Aktion zu groß, eröffnet das Modell einen neuen Band (`TL-1-Sampling-Timeline-Band-2`) statt zu kürzen; der alte Band bleibt unangetastet (Band-Rotation, M-INT Maxime 2). Sitzungs- und Dirigent-Protokolle werden dagegen **nie** fortgeschrieben — pro Sitzung entsteht je ein eigenes, sitzungsfinales Dokument (Delta-Prinzip).

**Wenn das Modell im Selbstspiel rutscht** — also deine Antwort vorwegnimmt oder zwei Schritte auf einmal macht — ist die richtige Antwort: ein kurzer Hinweis „warte auf meine Antwort", und in schweren Fällen ein Verweis auf M-INT.

## Wichtiger methodologischer Hinweis zur Materiallage

Du hast pro Fall nur eine ausgewählte Passage. Das hat zwei Konsequenzen für den v3-Workflow.

**Erstens, die Innerfall-Komparation entfällt.** Sie verlangt mindestens zwei Passagen eines Falls. Sie wird übersprungen, mit Eintrag im Sitzungsprotokoll.

**Zweitens, das Vergleichsmaterial für die reflektierende Interpretation kommt aus anderen Fällen.** Das Hauptmodul M-RI (und ebenso eine etwaige Vertiefungslinse) verlangt Vergleichsmaterial als Pflicht-Eingabeschicht. In deiner Konstellation kommt dieses Vergleichsmaterial nicht aus einer zweiten Passage desselben Falls, sondern aus den Passagen der anderen drei Fälle. Das ist methodologisch zulässig und sogar produktiv, weil der fallübergreifende Vergleich von Anfang an mitläuft. Voraussetzung ist, dass mindestens ein anderer Fall schon mindestens den RI-Eintritt (M-RI-0, M-FI) durchlaufen hat, idealerweise auch schon ein M-RI, damit du auf dessen Befunde Bezug nehmen kannst.

Daraus folgt eine bestimmte Reihenfolge der Bearbeitung: zuerst läuft pro Fall die Eingangskette und der RI-Eintritt (M-RI-0, M-RI-2a/2b) durch. Dann beginnt das M-RI-Hauptmodul mit Fall 2 oder 3, sodass Vergleichsmaterial aus Fall 1 bereits verfügbar ist. Fall 1 bekommt sein M-RI später, mit dem dann verfügbaren Vergleichsmaterial aus den anderen Fällen.

**Drittens, die Fallzusammenfassung wird angepasst.** Wenn pro Fall nur eine Passage bearbeitet wurde, übernimmt die Fallzusammenfassung die Passagen-Zusammenfassung, mit explizitem Hinweis, dass weitere Passagen pro Fall offen sind. Die Reichweite des Falls wird entsprechend eingeschränkt.

**Viertens, die fallübergreifende Komparation ist mit vier Fällen möglich**, aber methodologisch grenzwertig für eine voll bewährte Typologie. Q-3 (Reichweiten-Check) wird hier besonders wichtig.

## Methodische Leitplanken (Stand 2026-05-21)

Diese Leitplanken sind aus dem Durchlauf 2026-05-21 in die Module eingearbeitet (Details in den jeweiligen Modulen, in `M-STIL` und im Änderungsprotokoll `_Moduluberarbeitung-2026-05-21.md`). Beim Durchspielen sind sie besonders zu beachten, weil hier die häufigsten und schwersten Fehler liegen:

- **OR ist modus operandi, keine Einstellung.** Nicht die Meinung/Selbstdeutung/den Affekt der Sprechenden rekonstruieren, sondern das Wie der Praxis. Faustprobe: Würde die Sprecherin dem OR-Satz einfach zustimmen, ist es noch ihre Haltung.
- **Form zuerst.** Den OR aus der formalen Ebene (Diskursorganisation, Sequenz, Metaphernwahl) erzeugen, nicht den Inhalt nachträglich mit der Form bestätigen. Bei reportiven Passagen liegt der Zugriff im Wie des Erzählens, nicht im Inhalt des Berichteten (zitierte ≠ vollzogene Antithese).
- **Vergleichsdimension gewinnen, nicht mitbringen.** Fälle möglichst *nicht* entlang der vermuteten Zieldimension wählen; jeden Fall zuerst für sich rekonstruieren, die Dimension danach aus den Fällen gewinnen (Kontrolle des Interpreten-Vergleichshorizonts). Wer entlang der Achse sampelt, plausibilisiert nur.
- **Abduktion ≠ Konfirmation; Kontrast ≠ Bewährung.** Eine vorab feststehende, nur erfüllte Hypothese ist Konfirmation. Ein Kontrastfall korroboriert die Dimension, nicht den Typ.
- **KER ≠ Schema ≠ Ausdruck.** Norm/Vokabular = kommunikatives Schema; geteilter Affekt = Ausdruck eines KER; der KER selbst ist die geteilte Lage/Praxis.
- **Q-Korrekturen verbindlich einarbeiten.** Q-1/Q-3-Befunde werden im geprüften Output *vollzogen*, nicht nur notiert (sonst „performative Korrektur").
- **Gegen Glättung.** Mehrdeutigkeit auch mal offen lassen; Vorbehalte senken die Aussage, statt sie zu lizenzieren; bei restloser Passung die Zu-glatt-Gegenprobe (was im Material widersteht?).
- **Beispiele/Realitäts-Grenze.** Modul-Beispiele dürfen nie aus dem eigenen Korpus stammen. Und: Selbstspiel (eine Instanz spielt forschende Person und Modell) ersetzt die Forschungswerkstatt nicht — Dirigent und Verhandlungs-Module sind so nicht validierbar; die Geltung der Rekonstruktion verlangt reale Mehrstimmigkeit.

## Reihenfolge der Bearbeitung im Überblick

Die Anleitung folgt dreizehn Phasen. Sie sind nicht alle in einer Sitzung zu machen, sondern verteilen sich über mehrere Forschungssitzungen. Die RI-Phase läuft als **integriertes M-RI-Hauptmodul**; die Vertiefung einzelner Schichten geschieht innerhalb des M-RI.

```
Phase 1  · Vierklang-Verortung (einmalig pro Projekt):
            1.1 M-GEG Gegenstandstheorie (projektspezifisch)
            1.2 M-GT  Grundlagentheorie-Wahl
            1.3 M-MET Methodologie-Wahl
            1.4 M-MTH Methodenwahl
Phase 2  · M-00 Sitzungs-Setup + M-DIR Dirigent aktivieren (pro Sitzung)
Phase 3  · Pro Fall: Eingangskette M-01, M-02, M-FI (vier Sitzungen)
Phase 4  · Pro Fall: RI-Eintritt M-RI-0 (+ M-RI-2a/2b) (vier Sitzungen)
Phase 5  · Pro Fall: M-RI (integriert) mit Vergleichsmaterial (vier Sitzungen)
            Vertiefung der Schichten innerhalb des integrierten M-RI
Phase 6  · Q-1 und Q-2 nach jedem M-RI (optional, empfohlen)
Phase 7  · Pro Fall: Zusammenfassung der RI und Fallzusammenfassung
Phase 8  · Q-3 nach jeder Fallzusammenfassung (empfohlen)
Phase 9  · Fallübergreifend: Sinngenetische Typiken
            (vergleichende Analyse und Vergleichsdimension, Typik-Bildung in
             normischer Form, Prüfung an unabhängigem Material)
Phase 10 · Fallübergreifend: Typologien (mit vorgeschaltetem Reichweiten-Check)
Phase 11 · Fallübergreifend: Soziogenetische Rekonstruktion
Phase 12 · Fallübergreifend: Relationale Typenbildung (optional, nur bei mehreren Typologien)
Phase 13 · Vergleichshorizonte und Sample-Entwicklung (Schleife, auf Anlass aus Phase 9–11)
```

**Wichtiger Hinweis zur Typenbildung.** Auch die fallübergreifenden Phasen (Komparative Analyse, Abduktion, Als-ob-Deduktion) sind keine Stellen, an denen Komparation, Abduktion und Bewährung *zum ersten Mal* geschehen. Diese Operationen laufen bereits in jeder reflektierenden Interpretation: Die OR-Rekonstruktion ist eine Abduktion, der Pflicht-Vergleich ist die Komparation, und die Prüfung der OR-Hypothese am Vergleichsmaterial ist eine Als-ob-Deduktion. Die fallübergreifenden Module **konsolidieren** das korpusweit und leisten die **nicht-zirkuläre Bewährung** an Fällen außerhalb der Hypothesenbildung. Praktisch heißt das beim Durchspielen: Erwarte nicht, dass M-TB-1/M-TB-2/M-TB-3 neue Befunde produzieren — sie verdichten und prüfen, was die RIs schon hervorgebracht haben. Wenn die Typenbildungs-Outputs (M-TB-1 bis M-TB-3) sich weitgehend als Wiederholung der RIs lesen, ist das kein Fehler, sondern die korrekte Arbeitsteilung; der einzige genuin neue Schritt ist die Bewährung an unabhängigem Material. Bei sehr kleinem Sample (etwa zwei Fälle) hat die Typenbildungs-Phase deshalb wenig Eigenarbeit und produziert vor allem eine Reichweiten-Ehrlichkeit: eine Typik-Hypothese, deren Bewährung aussteht (→ Theoretical Sampling über M-TB-H).

---

## Phase 1 · Vierklang-Verortung (einmalig pro Projekt)

Diese Phase besteht aus vier aufeinanderfolgenden Modulen entlang der Vierklang-Differenzierung. Jede Schicht begrenzt die nächste: die Gegenstandstheorie ruft eine passende Grundlagentheorie ab, die Grundlagentheorie eine passende Methodologie, die Methodologie eine passende Methode. Die organische Passung wird in jedem Schritt explizit geprüft.

### Schritt 1.1 · M-GEG Gegenstandstheorie (projektspezifisch)

**Modul**: projektspezifische M-GEG-Datei, z. B. `M-GEG-<Projekt>.md`. Anders als M-GT, M-MET und M-MTH ist M-GEG *kein* Wahl-Modul mit fixen Varianten — die Gegenstandstheorie ist projektgebunden und wird in einer eigenen Datei niedergelegt, die Schlüsselbegriffe, Forschungsfragen und Standbein-Architektur des Projekts verdichtet.

**Eingabe**: keine; du bringst dein eigenes Projekt mit.

**Im Dialog zu klären**:

- Für die **Minimalfassung** (Erstkontext): Forschungsfrage, Design-Fakten, Reichweiten-Setzungen, Standort-Hinweis
- Für die **Voll-Rahmung** (kein Erstkontext): Schlüsselbegriffe, Standbein-Architektur, theoretische Anschlüsse, ggf. Ergebnis-Stände
- Schleusenregel: interpretierende Sitzungen laden nur die Minimalfassung (Begründung im `M-GEG-Template`)

**Output speichern unter**: zwei Dokumente — `M-GEG-<Projekt>.md` (Minimalfassung, Erstkontext) im Modul-Ordner und `_M-GEG-<Projekt>-Rahmung.md` (Voll-Rahmung, kein Erstkontext).

**Was zu beobachten**: Begrenzt die Datei sich selbst klar gegen das Theoriekapitel und gegen die Lese-Folie für die einzelnen Fall-RI? Sind die Schlüsselbegriffe so präzise, dass Q-1 sie später prüfen kann?

### Schritt 1.2 · M-GT Grundlagentheorie-Wahl

**Modul**: `M-GT-Grundlagentheorie-Wahl.md`

**Eingabe**: die M-GEG-Datei aus Schritt 1.1.

**Im Dialog zu klären**:

- Grundlagentheorie (etwa: praxeologische Wissenssoziologie)
- Verweis auf die GT-Modul-Datei: `M-GT-1-Praxeologische-Wissenssoziologie.md`
- Organische Passung zum Gegenstand prüfen (Verteilte Interpretation verlangt einen Begriff von konjunktivem Erfahrungsraum, der nur praxeologisch zu haben ist)
- Standard-Anschluss-Methodologie: Dokumentarische Methode (DM)

**Output speichern unter**: `<durchlauf>/00-Grundlagentheorie-Wahl.md`

**Was zu beobachten**: Bietet das Modul Optionen sinnvoll an, ohne ins Lehrbuch zu rutschen? Wird die Passung zum Gegenstand sichtbar geprüft, statt sie zu unterstellen?

### Schritt 1.3 · M-MET Methodologie-Wahl

**Modul**: `M-MET-Methodologie-Wahl.md`

**Eingabe**: M-GEG-Datei und M-GT-Protokoll aus den Schritten 1.1 und 1.2 plus die referenzierte GT-Modul-Datei (`M-GT-1-Praxeologische-Wissenssoziologie.md`).

**Im Dialog zu klären**:

- Methodologie: dokumentarische Methode (organische Passung zu M-GT-1)
- Verweis auf die MET-Modul-Datei: `M-MET-1-Dokumentarische-Methode.md`
- Aktivierte Pipeline: die im v3-Workflow ausgebaute DM-Pipeline
- Optionale Module: alle Q-Module aktiv, relationale Typenbildung optional
- Reichweiten-Anpassungen aus der Material-Lage (etwa: Innerfall-Komparation entfällt bei nur einer Passage pro Fall)

**Output speichern unter**: `<durchlauf>/00-Methodologie-Wahl.md`

**Was zu beobachten**: Prüft das Modul die organische Passung zwischen Grundlagentheorie und Methodologie sichtbar, oder rutscht es ins automatische Bestätigen? Wird die Festlegung der konkreten *Methode* an M-MTH delegiert, statt sie hier vorwegzunehmen?

### Schritt 1.4 · M-MTH Methodenwahl

**Modul**: `M-MTH-Methodenwahl.md`

**Eingabe**: M-GEG, M-GT-Protokoll, M-MET-Protokoll aus den Schritten 1.1 bis 1.3.

**Im Dialog zu klären**:

- Methode (etwa: Gruppendiskussionsverfahren; organische Passung zur Methodologie prüfen)
- Verweis auf die MTH-Modul-Datei: `M-MTH-1-Gruppendiskussionsverfahren.md`
- Materialtypen im Projekt: vier Gruppendiskussionen
- RI-Strukturanalyse-Routing: M-RI-2a (Diskursorganisation)
- Setting-spezifische Akzentuierungen (etwa Online-Erhebung, Vorwissen der Teilnehmenden)
- Reichweiten-Anpassungen aus dem Verfahren (Mindestpassagenzahl, Mindestfallzahl)

**Output speichern unter**: `<durchlauf>/00-Methodenwahl.md`

**Was zu beobachten**: Hebt das Modul die methodische Wahl als eigenständigen Entscheidungsschritt heraus, statt sie als bloße Folge der Materiallage zu behandeln? Werden die Setting-Akzentuierungen (Zoom, geschulte Gruppe) als operative Hinweise für M-RI-0 und M-RI-2a aufgenommen?

---

## Phase 2 · M-00 + M-DIR pro Sitzung

Diese Phase wiederholt sich vor jeder weiteren Phase. Sie öffnet eine konkrete Forschungssitzung.

**Modul M-00**: `00-Sitzungs-Setup.md`

**Eingabe**: die vier Vierklang-Dateien aus Phase 1 — M-GEG (z. B. `M-GEG-<Projekt>.md`), M-GT-Protokoll plus M-GT-Modul-Datei (`M-GT-1-Praxeologische-Wissenssoziologie.md`), M-MET-Protokoll plus M-MET-Modul-Datei (`M-MET-1-Dokumentarische-Methode.md`), M-MTH-Protokoll plus M-MTH-Modul-Datei (`M-MTH-1-Gruppendiskussionsverfahren.md`) — plus dein Sitzungsziel. Bei Eingangsketten-Sitzungen zusätzlich das **Gesamttranskript** des Falls.

**Im Dialog zu klären**:

- Material der Sitzung: welches **Gesamttranskript** (= welcher Fall) steht im Mittelpunkt. Die Passage wird in Eingangsketten-Sitzungen erst durch M-02 ausgewählt; sie ist *nicht* Eingabe in M-00.
- **Material-Ebene der Sitzung**: Gesamttranskript (Eingangskette M-01/M-02 stehen an) oder Passage (M-02 ist gelaufen, RI-Module folgen).
- Forschungszweck der Sitzung (etwa: vollständige Eingangskette für Fall 1; oder: die RI-Tiefenarbeit für Fall 2 mit Vergleichsmaterial).
- Stand der Analyse (was schon gelaufen ist).
- Mindestpassagen-Status: pro Fall nur eine Passage. Markiere als „begrenzte_reichweite mit fallübergreifendem Vergleich".
- Standortgebundenheit: projektspezifische Verortung (Doppelrollen, Nähe zum Feld), falls vorhanden.
- Reichweite der Sitzung: passage, fall, fallübergreifend, methodologisch.

**Output speichern unter**: `<durchlauf>/00-Sitzungsprotokolle/<datum>-s<NN>-<kurzname>.md` — pro Sitzung ein eigenes Protokoll (Delta-Prinzip), NN läuft durchlaufweit fort.

**Modul M-DIR**: `M-DIR-Dirigent.md`

**Eingabe**: das Sitzungsprotokoll aus M-00, plus, ab der zweiten Sitzung, das Dirigent-Protokoll der vorigen Sitzung als Verlaufsgedächtnis.

**Im Dialog zu klären**: Wo stehe ich gerade, welches Modul wäre als nächstes sinnvoll? Der Dirigent macht Vorschläge, du wählst.

**Output speichern unter**: `<durchlauf>/00-Dirigent-Protokolle/<datum>-s<NN>-dirigent.md`. Wird am Sitzungsende gespeichert; weitere Sicherungen innerhalb derselben Sitzung als neue Version. Pro Sitzung ein eigenes Protokoll, das nur diese Sitzung dokumentiert — frühere Dirigent-Protokolle werden nicht fortgeschrieben (Delta-Prinzip, M-INT Maxime 2).

---

## Phase 3 · Pro Fall: Eingangskette M-01, M-02, M-FI

Reihenfolge: frei wählbar; sinnvoll ist, mit dem Fall zu beginnen, zu dem schon Vorarbeit existiert.

### Schritt 3.1 · M-01 Thematischer Verlauf

**Modul**: `01-Thematischer-Verlauf.md`

**Eingabe**: das Gesamttranskript des Falls plus das Sitzungsprotokoll. Wenn das Transkript keine Absatznummerierung hat, weise das Modell darauf hin, es vergibt dann eine modul-interne Nummerierung.

**Vorschritt Datenaufbereitung.** Vor M-01 das Transkript nummerieren und — bei langen Transkripten (mehrere zehntausend Wörter) — in Blöcke zerlegen, die nacheinander erschlossen und zu *einer* durchgehenden Sequenzierungstabelle zusammengeführt werden. Ohne diese Aufbereitung sprengt M-01 oft das Kontextfenster (gerade beim Kopieren in eine Chat-Sitzung). Wird chunk-weise gearbeitet, im Output vermerken, damit Brüche an den Chunk-Grenzen geprüft werden können.

**Im Dialog zu klären**: Ist die Sequenzierungstabelle feinkörnig genug (eine Zeile pro Unterthema, keine Sammelzeilen mit mehreren Themen)? Passen die Schnitte zu deiner Lektüre? Schlägt das Modell die schon ausgewählte Passage als analytisch dicht vor?

**Output speichern unter**: `<durchlauf>/<Fall>/01-Thematischer-Verlauf.md`

### Schritt 3.2 · M-02 Passagenauswahl mit Kontextprotokoll

**Modul**: `02-Passagenauswahl-Kontextprotokoll.md`

**Eingabe**: das Gesamttranskript, der M-01-Output, plus der Hinweis, dass die in der Dissertationsvorbereitung ausgewählte Passage (`<Fall>_Passage für Prompting.docx`) zu wählen ist. Wenn du willst, kannst du das Modell auch *ohne* Vorgabe einen Vorschlag *anbieten* lassen — die Auswahl trifft im verteilten Modus du selbst, das Modell macht nur einen begründeten Vorschlag und fragt nach, ob du ihm folgst.

**Im Dialog zu klären**: Propositionaler Status des Einstiegs (eigenständig oder Anschluss), Außenreferenzen, Dichte-Marker, Verortung im thematischen Verlauf.

**Output speichern unter**: `<durchlauf>/<Fall>/02-Passagenauswahl.md`

**TL-1 aktualisieren**: Eintrag „Passage <Fall> ausgewählt" mit Wissensstand, Begründung, geprüften Alternativen.

### Schritt 3.3 · M-FI Formulierende Interpretation

**Modul**: `03-Formulierende-Interpretation.md`

**Eingabe**: die Passage mit Kontextprotokoll aus 3.2 plus der thematische Verlauf aus 3.1.

**Im Dialog zu klären**: Oberthema, Unterthemen pro Sprecherwechsel mit thematischer Substanz, Diskursnotizen für formale Stellen ohne Sachgehalt, Außenreferenzen, Validierung des Oberthemas.

**Output speichern unter**: `<durchlauf>/<Fall>/03-FI.md`

**Was zu beobachten**: Bleibt die FI strikt immanent, ohne ins Reflektierende abzurutschen? Werden die Originalbegriffe der Sprechenden beibehalten?

Wiederhole Schritt 3.1 bis 3.3 für alle vier Fälle, bevor du in Phase 4 gehst.

---

## Phase 4 · Pro Fall: RI-Eintritt (M-RI-0 und ggf. M-RI-2a/2b)

Reihenfolge: dieselbe wie in Phase 3.

### Schritt 4.1 · M-RI-0 Auffälligkeiten

**Modul**: `04-0-Auffaelligkeiten.md`

**Eingabe**: M-02 (Passage + Kontextprotokoll), M-FI, M-01.

**Im Dialog zu klären**: Welche Stellen sind formal auffällig? Welche sind mehrfach auffällig? Welche Stellen drängen sich für die reflektierende Interpretation auf?

**Output speichern unter**: `<durchlauf>/<Fall>/04-0-Auffaelligkeiten.md`

### Schritt 4.2 · M-RI-2a Diskursorganisation

**Modul**: `04-2a-Diskursorganisation.md`

**Eingabe**: M-02, M-FI, M-RI-0, M-01.

**Im Dialog zu klären**: Proposition(en), Zuordnung der Beiträge zu den Diskursbewegungen, übergreifende Diskursbewegungen, Bestimmung des Diskursmodus.

**Output speichern unter**: `<durchlauf>/<Fall>/04-2a-Diskursorganisation.md`

**Was zu beobachten**: Werden sanfte Antithesen als Antithesen erkannt, oder fälschlich als Validierungen gelesen? Wird die Mehrdeutigkeit einzelner Beiträge sauber ausgehalten?

Wiederhole Schritt 4.1 und 4.2 für alle vier Fälle, bevor du in Phase 5 gehst.

---

## Phase 5 · Pro Fall: M-RI (integriert) mit fallübergreifendem Vergleichsmaterial

**Methodologisch zentraler Schritt.** Hier läuft das Hauptmodul der RI-Phase als zusammenhängender Interpretationstext. Statt vier Tier-3-Module der Reihe nach abzuarbeiten, schreibt das Modell eine kursorische, dichte Interpretation, die die analytischen Schichten — Metaphern, Gegenhorizonte, Praktiken, konjunktive Erfahrung — integriert nutzt, dort, wo das Material sie aufruft. Ungleiche Gewichtung der Schichten ist Standard.

**Empfohlene Reihenfolge**: Beginne mit dem Fall, dessen RI-Eintritt am besten ausgearbeitet ist — mit den bereits bearbeiteten Fällen als Vergleichsmaterial; der erste Fall bekommt sein M-RI zuletzt, wenn Vergleichsmaterial aus den anderen vorliegt. Vergleichsmaterial ist Pflicht-Eingabeschicht.

### Schritt 5.1 · M-RI Reflektierende Interpretation (integriert)

**Modul**: `04-Reflektierende-Interpretation.md`

**Eingabe**:
- M-02 (Passage + Kontextprotokoll), M-FI, M-RI-0, M-RI-2a (bei GD) bzw. M-RI-2b (bei Interview)
- M-01 zur Verortung
- **Vergleichsmaterial (Pflicht)**: aus mindestens einer weiteren Passage; bei einer Passage pro Fall: aus mindestens einem anderen Fall (mindestens dessen FI und M-RI-0, idealerweise dessen M-RI)
- M-STIL als Stil-Referenz und M-INT als Interaktions-Referenz (beide verbindlicher Erstkontext in karl ai)

**Im Dialog zu klären**: An welcher Anker-Stelle setzt die Interpretation ein? Welche Schichten tragen in dieser Passage besonders, welche nur am Rand? Wie verhält sich das Material zum Vergleichsmaterial? Wo lohnt sich Vertiefung, wo nicht? Wo gilt es, Mehrdeutigkeit zu halten?

**Output speichern unter**: `<durchlauf>/<Fall>/04-Reflektierende-Interpretation.md`

**Was zu beobachten**: Schreibt das Modell als interpretierender Sozialforscher oder als Schema-Befüller? Ist der Output ein zusammenhängender Fließtext oder zerfällt er in vier symmetrische Sub-Sektionen? Wird die ungleiche Gewichtung dem Material gerecht? Wird mit langen Zitaten aus dem Material und dem Vergleichsmaterial gearbeitet?

### Schritt 5.2 · Vertiefung innerhalb des integrierten M-RI

Wenn eine Schicht (Metaphern, Gegenhorizonte, Praktiken, KER) besondere Tiefe verlangt, geschieht das *innerhalb* des M-RI-Durchgangs (ungleiche Gewichtung als Standard) oder an einer zweiten Passage — nicht durch ein separates Linsen-Modul. Die Orientierungsrahmen-Synthese ist im M-RI-Output bereits enthalten.

Wiederhole 5.1 für alle Fälle, bevor du in Phase 6 gehst.

---

---

## Phase 6 · Q-1 und Q-2 nach jedem M-RI (empfohlen)

Nach jedem M-RI-Output (und ggf. nach durchgelaufenen Vertiefungslinsen) läuft optional Q-1 und Q-2.

### Q-1 Begriffsdisziplin- und Stil-Check

**Modul**: `Q-1-Begriffsdisziplin.md`

**Eingabe**: der M-RI-Output des Falls.

**Im Dialog zu klären**: Werden die Kern-Begriffe der DM (Rahmen versus Schema, immanent versus dokumentarisch, konjunktiv versus kommunikativ, Komparation versus Vergleich) korrekt verwendet? Entspricht der Output dem in M-STIL festgelegten Interpretations-Stil — Fließtext, Konjunktiv, Mehrdeutigkeit, Konkretheit am Material — oder ist er in Karteikarten-Stil gerutscht?

**Output speichern unter**: `<durchlauf>/Q-Module-Einsaetze/Q-1-<Fall>-MRI.md`

### Q-2 Standortgebundenheit

**Modul**: `Q-2-Standortgebundenheit.md`

**Eingabe**: der M-RI-Output des Falls plus kontextuelle Angaben zu deiner Verortung (Doppelrollen, Methoden-Vertrautheit, Verhältnis zum Forschungsgegenstand).

**Im Dialog zu klären**: Welche Verortungs-Achsen wirken auf die Befund-Stelle? Vertrautheits- oder Fremdheits-Effekte? Doppelrollen-Effekte? Welche Folgerungen für die Formulierung?

**Output speichern unter**: `<durchlauf>/Q-Module-Einsaetze/Q-2-<Fall>-MRI.md`

---

## Phase 7 · Pro Fall: Zusammenfassung der RI und Fallzusammenfassung

### Schritt 7.1 · Zusammenfassung der Reflektierenden Interpretation

**Modul**: `M-VD-1-Zusammenfassung-RI.md`

**Eingabe**: der M-RI-Output, M-RI-2a, M-RI-0, M-FI.

**Bei einer Passage pro Fall überspringen.** Wenn pro Fall nur eine Passage vorliegt, fällt die Zusammenfassung der RI (Zfri) mit der Fallzusammenfassung (Schritt 7.2) zusammen — beide verdichten dieselbe eine RI. Die Zfri wird dann übersprungen (analog zur entfallenden Innerfall-Komparation) und ihre Verdichtung in die Fallzusammenfassung gezogen; das wird dort vermerkt. Erst ab zwei Passagen pro Fall ist die separate Zfri sinnvoll.

**Im Dialog zu klären**: Thematische, strukturelle und inhaltliche Verdichtung. Konsolidierte Aspekt-Listen mit Reichweiten. Reichweiten-Notiz. Übergabe an die Fallzusammenfassung.

**Output speichern unter**: `<durchlauf>/<Fall>/M-VD-1-Zfri.md`

**Was zu beobachten**: Wird wirklich verdichtet, oder werden die M-RI-Schicht- und Synthese-Outputs (im integrierten M-RI) reproduziert? Bleiben die Aspekt-Listen strukturiert?

### Schritt 7.2 · Fallzusammenfassung

**Modul**: `M-VD-3-Fallzusammenfassung.md`

**Eingabe**: die Zusammenfassung der RI aus 7.1, das Sitzungs-Setup.

**Hinweis**: Bei pro Fall einer Passage übernimmt die Fallzusammenfassung im Wesentlichen die Passagen-Zusammenfassung. Die Innerfall-Komparation entfällt, das wird im Output explizit als „nur eine Passage pro Fall, Innerfall-Komparation nicht anwendbar" markiert.

**Im Dialog zu klären**: Fallinterne OR-Rekonstruktion, sinngenetische Einzeltypen am Fall (auch wenn sie aus nur einer Passage abgeleitet sind), soziogenetische Hinweise, fallinterne Aspekt-Konsolidierung mit fallinternen Reichweiten.

**Output speichern unter**: `<durchlauf>/<Fall>/M-VD-3-Fallzusammenfassung.md`

Wiederhole für alle vier Fälle.

---

## Phase 8 · Q-3 nach jeder Fallzusammenfassung (empfohlen)

**Modul**: `Q-3-Reichweite.md`

**Eingabe**: die Fallzusammenfassung des Falls.

**Im Dialog zu klären**: Aussagen mit Reichweiten-Profilen, Über- oder Unter-Reichweiten, Standard-Befunde (Typik aus zu wenig Fällen, Passage versus Fall, Hypothese versus Rekonstruktion, kausal versus korrespondierend).

**Output speichern unter**: `<durchlauf>/Q-Module-Einsaetze/Q-3-<Fall>-Fallzusammenfassung.md`

---

## Phase 9 · Fallübergreifend: Sinngenetische Typiken

Vor dieser Phase einmal den Überblick zur typenbildenden Interpretation und die Schlussformen-Referenz lesen: Die Phase ist nach Abstraktionsgraden geordnet (von den Einzeltypen am Fall zu den Typiken), und die Schlussformen — abduktive Einsicht, als-ob-deduktive Verallgemeinerung, pragmatisch-induktive Prüfung — sind wiederkehrende Modi, keine aufeinanderfolgenden Schritte.

**Modul**: `M-TB-1-Sinngenetische-Typiken.md`

**Eingabe**: die Fallzusammenfassungen mit ihren sinngenetischen Einzeltypen und Aspekten, das Sitzungs-Setup, die Typen- und Theorie-Zeitleiste. Querlaufend: die Schlussformen-Referenz (`M-TI-S-Schlussformen.md`).

**Im Dialog zu klären**: Inventar der Einzeltypen und Aspekte über die Fälle; mögliche Vergleichsdimensionen und Auswahl einer Vergleichsdimension gegen mindestens eine Alternative; vergleichende Analyse entlang der Dimension mit der abduktiven Einsicht; minimaler und maximaler Kontrast; Formulierung der Typik in normischer Form mit fallbezogenen Randbedingungen; Konturierung gegen alternative Typiken; pragmatisch-induktive Prüfung an Material außerhalb der Hypothesenbildung (Unterscheidung von bloßer Konsistenz und Bewährung); Reichweiten-Markierung.

**Output speichern unter**: `<durchlauf>/falluebergreifend/M-TB-1-Sinngenetische-Typiken.md` (Stamm laut Dateinamen-Schema)

**Typen- und Theorie-Zeitleiste aktualisieren**: Einträge „Vergleichsdimension festgelegt", „erste abduktive Hypothese", „Typik formuliert" mit Reichweite.

**Bei Diskonfirmation an unabhängigem Material**: zurück zur abduktiven Einsicht, die Typik wird neu gefasst. Diese Schleife ist methodisch produktiv, kein Defizit.

**Was zu beobachten**: Wird die Vergleichsdimension als Dimension verstanden, nicht als inhaltliche Ähnlichkeit? Werden minimaler und maximaler Kontrast beide gesucht? Wird die Warnung vor dem vorschnellen Raster beachtet (gemeinsam variierende Teildimensionen ergeben eine Achse mit Polen, kein Raster)? Wird Konsistenz nicht mit Bewährung verwechselt?

---

## Phase 10 · Fallübergreifend: Typologien

### Schritt 10.1 · Reichweiten-Check vor der Typologie

**Modul**: der Reichweiten-Check (Datei `Q-3-Reichweite.md`)

**Eingabe**: der Output der sinngenetischen Typiken.

Empfohlen, weil hier die Reichweite besonders schnell überschätzt wird.

**Output speichern unter**: `<durchlauf>/Q-Module-Einsaetze/Q-3-Typiken.md`

### Schritt 10.2 · Typologien

**Modul**: `M-TB-2-Typologien.md`

**Eingabe**: alle gebildeten Typiken (mindestens zwei), das Sitzungs-Setup, die Typen- und Theorie-Zeitleiste.

**Hinweis**: Mit wenigen Fällen ist die Typologie eher vorläufig als bewährt. Liegt nur eine Typik vor, kann keine Typologie gebaut werden — dann nur die ausdrückliche Feststellung und ein begründeter Ausblick darauf, welche weiteren Typiken eine Typologie tragen würden.

**Im Dialog zu klären**: Inventar der Typiken; gegenstandstheoretische Frage; Verhältnis der Typiken zueinander (Gegenpole, Komplement, Reihung, Querschnitt); Warnung vor dem vorschnellen Raster (gemeinsam variierende Dimensionen ergeben eine Achse mit Polen); Formulierung der Typologie; Reichweite nicht über die schwächste Typik hinaus.

**Output speichern unter**: `<durchlauf>/falluebergreifend/M-TB-2-Typologien.md` (Stamm laut Dateinamen-Schema)

**Typen- und Theorie-Zeitleiste aktualisieren**: Eintrag „Typologie formuliert" mit Reichweite (oder „keine Typologie, nur eine Typik; Ausblick").

---

## Phase 11 · Fallübergreifend: Soziogenetische Rekonstruktion

**Modul**: `M-TB-3-Soziogenetische-Rekonstruktion.md`

**Eingabe**: die Typologie (oder, falls keine entstand, die Typiken), die vier Fallzusammenfassungen mit ihren soziogenetischen Aspekten, die Typen- und Theorie-Zeitleiste.

**Im Dialog zu klären**: Inventar der soziogenetischen Aspekte pro Fall und Dimension, soziogenetische Korrespondenzen pro Typik, dominante und untergeordnete Dimensionen, Konturierung der Hypothesen, Reichweiten-Markierung; kollektive Lage und geteilte Selbstverständlichkeit auseinanderhalten.

**Bei wenigen Fällen ist die soziogenetische Rekonstruktion methodologisch eher Hypothese als belegte Rekonstruktion.** Die Reichweite bleibt entsprechend vorsichtig; es geht um Korrespondenzen, nicht um Kausalitäten.

**Output speichern unter**: `<durchlauf>/falluebergreifend/M-TB-3-Soziogenetische-Rekonstruktion.md` (Stamm laut Dateinamen-Schema)

**TL-2 aktualisieren**: Eintrag „Soziogenetische Verortung formuliert".

### Q-2 nach der Soziogenese

**Modul**: `Q-2-Standortgebundenheit.md`

**Eingabe**: die soziogenetische Rekonstruktion.

**Im Dialog zu klären**: Wie wirkt die eigene Verortung (Doppelrollen, Vertrautheit oder Fremdheit zum Feld) auf die soziogenetischen Korrespondenzen? Welche Dimensionen sind durch den eigenen Standort besonders nahegelegt oder verstellt? Welche Reichweiten-Folge ergibt sich für die Formulierung?

**Output speichern unter**: `<durchlauf>/Q-Module-Einsaetze/Q-2-Soziogenese.md`

---

## Phase 12 · Fallübergreifend: Relationale Typenbildung (optional)

Diese Phase läuft nur, wenn mehrere sinngenetische Typologien vorliegen. Bei vier Fällen mit je einer Passage entsteht meist höchstens eine Typologie, dann entfällt die Phase mit einem entsprechenden Vermerk im Output. Liegen zwei oder mehr Typologien vor, setzt sie diese zueinander in Beziehung.

**Modul**: `M-TB-R-Relationale-Typenbildung.md`

**Eingabe**: mindestens zwei sinngenetische Typologien aus Phase 10, die soziogenetische Rekonstruktion, die Fallzusammenfassungen, die Typen- und Theorie-Zeitleiste.

**Im Dialog zu klären**: Inventar der zu relationierenden Typologien; Matrix der Kombinationen mit Eintragung pro Fall; realisierte relationale Typiken; Formulierung der relationalen Typologie; methodologisch produktive Befunde, besonders die Leerstellen der Matrix (zufällig oder strukturell). Bei kleinem Sample werden die relationalen Typiken ausdrücklich als hypothetisch markiert.

**Output speichern unter**: `<durchlauf>/falluebergreifend/M-TB-R-Relationale-Typenbildung.md`

**Typen- und Theorie-Zeitleiste aktualisieren**: Eintrag „relationale Typologie formuliert" oder „nur eine Typologie, relationale Typenbildung nicht anwendbar", mit Reichweite. Produktive Leerstellen werden als Empfehlung zur Auswahl weiterer Vergleichsfälle vermerkt, was nach Phase 13 überleiten kann.

**Was zu beobachten**: Wird mit Matrix-Logik gearbeitet, nicht mit linearer Reihung? Werden die Leerstellen als aussagekräftig behandelt, nicht als bloße Lücken?

---

## Phase 13 · Vergleichshorizonte und Sample-Entwicklung (Schleife, auf Anlass)

Diese Phase steht nicht in fester Position, sondern wird als Schleife aufgerufen, sobald sich in Phase 9, 10 oder 11 zeigt, dass das Sample für die Bildung oder die Bewährung einer Typik nicht reicht. Bei vier Fällen mit je einer Passage ist dieser Anlass eher die Regel als die Ausnahme, weil die Bewährung an unabhängigem Material oft aussteht.

**Modul**: `M-TB-H-Vergleichshorizonte-und-Sampleentwicklung.md`

**Eingabe**: der konkrete Anlass mit präziser Bestimmung der Lücke (welche Konvergenz fehlt, welche Bewährung nicht möglich ist, welche Dimension nicht variiert), die Sampling-Zeitleiste, die Typen- und Theorie-Zeitleiste, die Fallzusammenfassungen.

**Im Dialog zu klären**: spezifische Bestimmung der Lücke statt pauschalem „mehr Fälle wären gut"; hypothesengetriebene Auswahlkriterien; minimal- und maximal-kontrastive Kandidaten mit ehrlicher Einschätzung der Realisierbarkeit; Empfehlung (Erweiterung um konkrete Fälle, Verzicht mit ausdrücklicher Reichweiten-Einschränkung, oder Aufschub).

**Output speichern unter**: `<durchlauf>/falluebergreifend/M-TB-H-Vergleichshorizonte-und-Sampleentwicklung.md` (Stamm laut Dateinamen-Schema)

**Sampling-Zeitleiste (TL-1) aktualisieren**: die Sampling-Entscheidung im Prinzip der vergangenen Gegenwarten. Bei Erweiterung Rückgang zur Passagenauswahl (vorhandenes Material) oder in die Erhebung (neues Material), bei Verzicht Verbleib im laufenden Prozess mit eingeschränkter Reichweite.

---

## Zum Schluss: Was du nach dem Durchspielen hast

Nach dem Durchspielen liegen dir folgende Materialien vor:

- Eine projektspezifische M-GEG-Datei (Gegenstandstheorie)
- Ein M-GT-Grundlagentheorie-Wahl-Protokoll mit Verweis auf die GT-Modul-Datei (M-GT-1)
- Ein M-MET-Methodologie-Wahl-Protokoll mit Verweis auf die MET-Modul-Datei (M-MET-1)
- Ein M-MTH-Methodenwahl-Protokoll mit Verweis auf die MTH-Modul-Datei (M-MTH-1)
- Pro Sitzung ein M-00-Protokoll und ein M-DIR-Protokoll
- Pro Fall die Eingangskette (M-01, M-02, M-FI)
- Pro Fall die RI in voller Breite (RI-Eintritt, RI-Strukturanalyse, RI-Tiefenarbeit und OR-Synthese (alle im integrierten M-RI))
- Pro Fall die Verdichtung (Zusammenfassung, Fallzusammenfassung)
- Fallübergreifend gebildete sinngenetische Typiken — mit ausgewiesener Vergleichsdimension, normischer Formulierung und Prüfung an Material außerhalb der Hypothesenbildung (abduktive Einsicht, als-ob-deduktive Verallgemeinerung und pragmatisch-induktive Prüfung als wiederkehrende Modi)
- Eine sinngenetische Typologie (oder, bei nur einer Typik, ein begründeter Ausblick)
- Eine soziogenetische Rekonstruktion der Typen, Typiken und Typologien
- Q-Modul-Einsätze an den empfohlenen Stellen
- Zwei laufende Timelines (Sampling und Typen-und-Theorie)

Diese Materialien sind die Grundlage für die methodologische Darstellung in der Dissertation. Sie zeigen die Forschungsgegenwart, in der die Befunde entstanden sind, und machen die Genese der Typologie nachvollziehbar.

## Hinweise zur Sitzungsplanung

Das Durchspielen ist eine umfangreiche Operation. Es wird nicht in einer Sitzung gehen, sondern in vielen. Eine grobe Schätzung pro Phase:

- Phase 1 (M-GEG + M-GT + M-MET + M-MTH): eine bis zwei Stunden, je nachdem, wie ausgearbeitet die Gegenstandstheorie schon ist
- Phase 2 (M-00 + M-DIR): zehn bis fünfzehn Minuten pro Sitzung
- Phase 3 (Eingangskette pro Fall): ein bis zwei Stunden pro Fall, also vier bis acht Stunden für alle vier Fälle
- Phase 4 (RI-Eintritt pro Fall): ein bis zwei Stunden pro Fall
- Phase 5 (integriertes M-RI pro Fall): zwei bis vier Stunden pro Fall, der mit Abstand aufwändigste Schritt, weil hier die eigentliche Interpretationstiefe entsteht
- Phase 6 (Q-1 und Q-2 nach jedem M-RI): je fünfzehn bis dreißig Minuten, an den Anlassstellen
- Phase 7 (Zusammenfassung der RI und Fallzusammenfassung pro Fall): ein bis zwei Stunden pro Fall
- Phase 8 (Q-3 nach jeder Fallzusammenfassung): fünfzehn bis dreißig Minuten
- Phase 9 (Sinngenetische Typiken, fallübergreifend): zwei bis vier Stunden, je nachdem, wie gut das Material konvergiert
- Phase 10 (Typologien mit vorgeschaltetem Reichweiten-Check): ein bis zwei Stunden
- Phase 11 (Soziogenetische Rekonstruktion): ein bis zwei Stunden
- Phase 12 (Relationale Typenbildung, optional): ein bis zwei Stunden, nur wenn mehrere Typologien vorliegen
- Phase 13 (Vergleichshorizonte, Schleife): dreißig bis sechzig Minuten je Aufruf

Diese Zahlen sind grobe Anhaltspunkte, keine Vorgaben. Wegen der Sitzungszäsur (siehe M-INT) wird ohnehin nach jedem abgeschlossenen Modulblock geschnitten. Plane deshalb lieber mehr und kürzere Sitzungen als wenige lange, der Dokumentenspeicher trägt den Arbeitsstand von Sitzung zu Sitzung.
