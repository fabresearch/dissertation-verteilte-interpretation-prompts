---
kürzel: TL-1
art: modul
titel: "TL-1 · Sampling-Zeitleiste"
fassung: ueberarbeitete_arbeitsfassung
instruktionsfassung: ueberarbeitete_arbeitsfassung_2026-09-25
erstellt: 2026-09-24
geaendert: 2026-09-25
status: nicht_erprobt
im_dokumentierten_durchlauf_verwendet: false
---

# TL-1 · Sampling-Zeitleiste

Lies diese Datei vollständig. Für Gespräch, Freigabe und Speicherung gelten die Regeln aus M-INT. Die Zeitleiste führt Auswahlentscheidungen über Sitzungen hinweg fort; sie ist kein erneut auszuschreibendes Sitzungsprotokoll.

## Anlass und Arbeitsgrundlage

Erfasse relevante Entscheidungen über Fälle, Passagen, Erweiterungen, Einschränkungen oder verworfene Auswahlmöglichkeiten. Anlässe entstehen insbesondere in M-00, M-02 und M-TB-H. Grundlage sind die tatsächlich getroffene Entscheidung und die bisherige Zeitleiste. Die Eintragung muss nicht jede beiläufige Erwägung einzeln protokollieren.

Kläre, was zum Entscheidungszeitpunkt bekannt war: vorhandene Materialien, bearbeitete Fälle, offene Hypothesen und Zugangsbedingungen. Unterscheide methodische Gründe, theoretische Erwartungen und praktische Möglichkeiten. Die Auswahl muss nicht nachträglich als rein theoriegeleitet dargestellt werden, wenn ein Zugang oder eine Arbeitsbegrenzung ausschlaggebend war.

## Prinzip der vergangenen Gegenwarten

Halte Entscheidungen in ihrem damaligen Kenntnisstand fest. Heutiges Wissen über das Ergebnis wird nicht in eine frühere Begründung zurückgeschrieben. Ist eine Eintragung erst nachträglich möglich, unterscheide Entscheidungsdatum und Eintragungsdatum, bezeichne sie als retrospektiv und nenne die vorhandene Grundlage. Unbekannte frühere Motive oder Zeitpunkte bleiben unbekannt.

Frage nur nach Informationen, die für die Entscheidung relevant und noch nicht vorhanden sind. Ein bereits im Gespräch geklärter Auswahlgrund muss nicht erneut einzeln abgefragt werden. Zeige die neue Eintragung zur Prüfung und Freigabe. Spätere Änderungen werden als neue Einträge mit Bezug zur früheren Entscheidung angefügt.

## Ergebnisstruktur

```markdown
---
typ: sampling_timeline
modul: TL-1
instruktionsfassung: ueberarbeitete_arbeitsfassung_2026-09-25
projekt: <Projekt>
band: 1
version: 1
ersetzt: null
vorheriger_band: null
status: entwurf
datum: <YYYY-MM-DD>
---

# Sampling-Zeitleiste · <Projekt>

## S-001 · <Entscheidung>

- Entscheidungsdatum: <Datum oder unbekannt>
- Eintragungsdatum: <Datum>
- Dokumentationsart: <zeitnah|retrospektiv>
- Grundlage: <Gespräch, Protokoll oder Ergebnisdatei>
- Wissensstand: <Was war bereits bekannt, was noch offen?>
- Entscheidung: <Gewählter oder verworfener Fall beziehungsweise Ausschnitt>
- Begründung: <Methodische, theoretische und praktische Gründe>
- Erwogene Alternativen: <Tatsächlich erwogene Alternativen oder nicht dokumentiert>
- Erwartete Folgen: <Damals erwarteter Beitrag, kein späteres Ergebnis>
- Bezug zu früheren Einträgen: <Kennung oder keiner>
```

Die Kennungen werden fortlaufend vergeben und auch bei einem Bandwechsel nicht erneut begonnen. Spätere Folgen können als neuer datierter Eintrag ergänzt werden; der frühere Erwartungshorizont bleibt im Wortlaut erhalten.

## Speicherung

Speichere im Durchlauf unter `Zeitleisten/TL-1-Sampling-Timeline.md`. Eine Fortschreibung ist eine neue vollständige Version, etwa `TL-1-Sampling-Timeline_v2.md`: bisherige Einträge unverändert übernehmen, neue anfügen, Metadaten aktualisieren. Prüfe, dass kein alter Eintrag fehlt oder verkürzt wurde. Fehlt die Vorgängerversion, fordere sie an; speichere einen neuen Einzelentwurf nicht als vollständige Chronik.

Wird ein neuer Band vereinbart, beginnt er unter `TL-1-Sampling-Timeline-band-02.md` mit Verweis auf die letzte Fassung des vorherigen Bandes. Innerhalb des neuen Bandes werden die Versionen wieder ab 1 gezählt. Die alten Bände bleiben unverändert erhalten. Für Freigabe und Prüfung der tatsächlichen Speicherung gilt M-INT. Übergib M-00 stets den aktuellen Band und seine Arbeitsfassung.
