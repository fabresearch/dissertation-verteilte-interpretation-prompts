---
titel: "v3 Modularer Workflow für die Dokumentarische Methode als verteilte Interpretation"
status: aktiv
erstellt: 2026-05-15
geaendert: 2026-06-17
aenderung: "Vierklang-Verortung nachgezogen: Architektur-Sektion und zweite Maxime nennen jetzt alle vier Verortungs-Sc… — Volltext im _CHANGELOG"
basis: "Konversationsstützen statt prozedurale Pipeline"
tags: [karl-ai, workflow, verteilte-interpretation, dokumentarische-methode, v3]
---

# v3 Modularer Workflow für die Dokumentarische Methode als verteilte Interpretation

Dieser Workflow versteht sich nicht als prozedurale Pipeline, sondern als Repertoire von Konversationsstützen, die in einer geteilten Interpretation zwischen Mensch und Modell aktiviert werden. Die Module sind aktivierbare Bausteine, die der forschenden Person helfen, mit dem Modell zusammen an konkreten Stellen des Materials zu arbeiten. Sie folgen nicht einer festen Reihenfolge, sondern werden vom Dirigenten und von der forschenden Person je nach Stand der Interpretation aufgerufen.

## Konzeptuelle Grundlage

Der Workflow steht in der konzeptuellen Logik der verteilten Interpretation. Interpretation entsteht im Zusammenspiel zwischen Mensch und Modell, nicht als prozedurale Abarbeitung. Die Module sind Konversationsstützen, weil sie das Modell befähigen, an spezifischen Stellen mit der forschenden Person ins Gespräch zu gehen, Vorschläge zu machen, Rückfragen zu stellen, Alternativen anzubieten und auf Widerspruch zu reagieren. Forschende, die ihre Prompts nicht selbst schreiben können, gewinnen damit Zugang zu methodologisch durchgearbeiteten Interpretationsoperationen, ohne dass sie sich die Operation als Verfahren aneignen müssen.

Die Module verstehen sich also nicht als rezeptartige Anweisungen, die mechanisch abgearbeitet werden, sondern als methodisch vorstrukturierte Dialog-Räume, in denen sich Interpretation entfalten kann.

## Kürzel-System (Legende)

Fünf Kürzel-Familien trennen Instruktion von Material: **M-** (Module und Referenzen), **Q-** (Qualitätssicherung), **TL-** (Timelines), **T-** (Gesamttranskripte), **P-** (Passagen). Kanonische Quelle jedes Kürzels ist das Frontmatter der Datei, nie der Dateiname (M-INT, Maxime 4).

Die Dateinamen folgen zwei Logiken: Eingangskette und RI-Phase tragen Workflow-Nummern (`00-…` bis `04-…`), die den Ordner in Arbeitsfolge sortieren — dabei entsprechen die 04er-Ziffern den M-RI-Kürzeln (`04-0` ↔ M-RI-0, `04-1` ↔ M-RI-1, `04-2a/b` ↔ M-RI-2a/b; das nummernlose `04-Reflektierende-Interpretation` ist das Hauptmodul M-RI). Ab der Verdichtung ist der Dateiname das Kürzel selbst (`M-VD-…`, `M-TB-…`, `M-DIR-…`).

Das Ziffern-Suffix bedeutet je Familie Verschiedenes: bei M-GT/M-MET **Wahlvarianten**, bei M-RI **Sequenzschritte**, bei M-VD **Operationen**, bei M-TB **Abstraktionsgrade**, bei Q **Prüfachsen**. Buchstaben-Suffixe markieren Sonderrollen (M-TB-R relational, M-TB-H Schleifenmodul, M-TI-S Referenz). Verwechslungspaar: **M-INT** (Interaktions-Referenz) ist nicht **M-TI** (typenbildende Interpretation).

## Architektur

### Projekt-vorgelagerte Module · Vierklang-Verortung

Vor jeder inhaltlichen Arbeit wird das Projekt in vier Schichten verortet, die einander begrenzen: Gegenstand, Grundlage, Methodologie, Methode. Jede der vier Verortungs-Dateien wird in jede nachfolgende Modul-Sitzung als Erstkontext mitgegeben.

- **M-GEG · Gegenstandsrahmung.** Erste Schicht. Anders als die folgenden drei ist M-GEG kein Wahl-Modul mit festen Varianten, sondern projektspezifisch — und in **zwei Fassungen** geführt (Schleusenregel im `M-GEG-Template`): Die **Minimalfassung** (`M-GEG-<Projekt>.md`: Forschungsfrage, Design-Fakten, Reichweiten-Setzungen, Standort-Hinweis) ist der einzige Erstkontext der interpretierenden Sitzungen. Die **Voll-Rahmung** (`_M-GEG-<Projekt>-Rahmung.md`: Schlüsselbegriffe, Theorieanschlüsse, Ergebnis-Stände) wird nur in Verwertungs- und Rahmungs-Sitzungen geladen (M-TB-H, Q-2-Vertiefung, Kapitel-Arbeit) — ein Sprachmodell kann Vorwissen nicht einklammern, deshalb wird es dosiert statt gewarnt.
- **M-GT · Grundlagentheorie-Wahl.** Zweite Schicht. Klärt einmal pro Projekt die grundlagentheoretische Linie und routet zu einer der Grundlagentheorie-Modul-Dateien (M-GT-1 Praxeologische Wissenssoziologie, M-GT-2 Hermeneutische Soziologie, M-GT-3 Symbolischer Interaktionismus) oder zu einer projektspezifischen M-GT-X für nicht im Repertoire ausgebaute Theorien. Die gewählte M-GT-Datei wird in jede nachfolgende Modul-Sitzung als Erstkontext mitgegeben.
- **M-MET · Methodologie-Wahl.** Dritte Schicht. Klärt einmal pro Projekt, welche Methodologie aus dem Gegenstand und der gewählten Grundlagentheorie folgt und routet zu einer der Methodologie-Modul-Dateien (M-MET-1 Dokumentarische Methode, M-MET-2 Objektive Hermeneutik, M-MET-3 Grounded Theory) oder zu einer projektspezifischen M-MET-X. Die gewählte M-MET-Datei trägt die operativen Maximen und die Pipeline-Festlegungen und wird zusammen mit dem M-GT-Protokoll und der M-GT-Datei in jede nachfolgende Modul-Sitzung als Erstkontext mitgegeben. Prüft die organische Passung zwischen Grundlagentheorie und Methodologie; bei nicht-organischen Konstellationen wird die Spannung explizit verhandelt und ihre Folgen für die nachfolgenden Module sichtbar gemacht.
- **M-MTH · Methodenwahl.** Vierte Schicht. Klärt einmal pro Projekt, welche konkrete Methode aus Methodologie und Gegenstand folgt, und routet zu einer der Methoden-Modul-Dateien (M-MTH-1 Gruppendiskussionsverfahren, voll ausgebaut; weitere Verfahren wie das narrativ-biografische Interview, die Photogruppendiskussion oder die Videografie als Skelett oder als projektspezifische M-MTH-X). Legt das materialtyp-spezifische RI-Strukturanalyse-Routing fest (Gruppendiskussion über M-RI-2a, Interview über M-RI-2b) und macht damit explizit, was zuvor implizit in M-MET-1 mitlief.

### Cross-Cutting laufend

- **M-DIR · Dirigent.** Begleitet die forschende Person durch die Sitzung, macht Vorschläge für nächste Modul-Aktivierungen, dokumentiert Konversationsführungs-Entscheidungen. Läuft im Hintergrund mit, wird zwischen Modulen explizit angesprochen.
- **M-STIL · Interpretationsstil.** Stil-Referenz für alle interpretativen Module (M-FI, M-RI-0, das integrierte M-RI, Verdichtungs- und Typenbildungs-Module). Legt fest, dass Modul-Outputs als kursorischer Fließtext mit langen Material-Zitaten, im Konjunktiv und mit ausgehaltener Mehrdeutigkeit geschrieben werden; Aspekt- und Inventar-Tabellen stehen am Ende als Nachschlagwerk, nicht als Strukturträger. Wird mit M-GT und M-MET als Erstkontext in jede Modul-Sitzung mitgegeben.
- **M-INT · Verteilte Interpretation und Output-Handhabung** (`M-INT-Verteilte-Interpretation-und-Chat-Output.md`). Interaktions-Referenz für chat-basierte Sprachmodell-Umgebungen (karl ai oder vergleichbar). Trägt kanonisch die **fünf Verfahrens-Maximen** (kein Selbstspiel; Dokumentenspeicher-Sicherung mit Versionierung; Eingabeschichten prüfen, Sprünge sichtbar machen; Modul-Datei vollständig lesen; Mandat-Grenzen), die Sitzungszäsur und das Delta-Prinzip der Protokolle — Wortlaut und Details dort, nicht hier. Wird gemeinsam mit M-STIL als verbindlicher Erstkontext mitgegeben. Jedes operative Modul beginnt zusätzlich mit einer **Modul-Identitätskarte** (Block-Quote nach der H1), die Kürzel, Workflow-Stelle, positives und negatives Mandat kompakt benennt.
- **`Initialprompt-karl-ai.md` · Sitzungs-Bootstrap.** Bootstrap-Datei (`art: bootstrap`, ohne Kürzel-Familie, parallel zu workflow.md und Anleitung-Workflow-Durchspielen.md) mit dem kopierbaren Initialprompt, mit dem jede neue karl-ai-Sitzung eröffnet wird. Setzt den verteilten Modus und beauftragt das Modell, M-STIL und M-INT eigenständig zu lesen. Kein operatives Modul (keine Modul-Identitätskarte, kein Output-Schema) — die Schnittstelle vor der ersten Modul-Aktivierung. In Cowork-Umgebungen oder bei direktem Zugriff auf den Modul-Ordner nicht zwingend nötig; in karl ai der Standard-Sitzungsstart.

### Material-Anker

Das **Gesamttranskript** ist die materielle Eingabeschicht des Workflows. Pro Fall gibt es ein Gesamttranskript (Gruppendiskussion, Interview oder anderer Materialtyp). Es ist die Eingabe für M-01 und bleibt im weiteren Verlauf als Kontext verfügbar. M-02 wählt aus dem Gesamttranskript eine Passage aus, auf der die nachfolgenden RI-Module arbeiten. Material-Ebene und Modul-Eingabe folgen also der Sequenz: Gesamttranskript → M-01 → M-02 (Passagenauswahl) → Passage → M-FI → RI-Kette.

Die Gesamttranskripte liegen als Markdown-Dateien in der Modulliste (Kürzel-Familie **T-**, `art: gesamttranskript`, Namensmuster `T-<Fall>-Gesamttranskript.md`); die ursprünglichen Quelldateien bleiben als Quelle erhalten. Aus jedem Gesamttranskript kann eine **Passage für Prompting** vorbereitet sein — die analytisch dichte Stelle, an der M-02/M-FI/M-RI ansetzen können (Kürzel-Familie **P-**, `art: passage`, Namensmuster `P-<Fall>-Passage.md`); jede P-Passage führt im Frontmatter `basis: T-<Fall>` als Verweis auf ihr Gesamttranskript. Die konkreten Fälle eines Projekts werden hier nicht aufgezählt; sie ergeben sich aus den T-/P-Dateien im Ordner.


### Sitzungs-vorgelagert

- **M-00 · Sitzungs-Setup.** Klärt einmal pro Sitzung, welches **Gesamttranskript** (= welcher Fall) bearbeitet wird, welche **Material-Ebene** die Sitzung adressiert (Gesamttranskript für die Eingangskette M-01/M-02; Passage für die nachfolgenden RI-Module), Forschungszweck, Stand der Analyse, Standortgebundenheit. Achtet auf die Mindestpassagen-Anforderung.

### Eingangskette

- **M-01 · Thematischer Verlauf.** Erschließt das Gesamttranskript thematisch, schlägt analytisch dichte Passagen vor.
- **M-02 · Passagenauswahl mit Kontextprotokoll.** Wählt aus dem Gesamttranskript (informiert durch M-01) eine Passage aus, extrahiert sie, produziert das Kontextprotokoll. Erst ab M-02 wird auf Passagen-Ebene gearbeitet.
- **M-FI · Formulierende Interpretation.** Rekonstruiert den immanenten Sinngehalt der ausgewählten Passage.

### Reflektierende Interpretation, Eintritt (Material-Fokussierung und Form-Strukturen)

- **M-RI-0 · Auffälligkeiten.** Identifiziert formal auffällige Stellen in elf Kategorien.
- **M-RI-1 · Textsortenbestimmung** (optional, vor allem bei Gruppendiskussionen).
- **M-RI-2a · Diskursorganisation** (Gruppendiskussionen).
- **M-RI-2b · Narrative Strukturanalyse** (Interviews).

### Reflektierende Interpretation, Hauptmodul (integriert)

- **M-RI · Reflektierende Interpretation.** Default-Modul der RI-Phase. Produziert einen zusammenhängenden, kursorischen Interpretationstext, der die analytischen Schichten — Metaphern, Gegenhorizonte, Praktiken, konjunktive Erfahrung — integriert nutzt, wo immer das Material sie nahelegt. Keine vier separaten Sub-Sektionen; ungleiche Gewichtung als Standard. **Vergleichsmaterial aus mindestens einer weiteren Passage gehört als Pflicht-Eingabeschicht dazu**, weil Gegenhorizonte, Praktiken und konjunktive Erfahrungsräume Konturen erst durch Kontrast gewinnen.

### Reflektierende Interpretation, Vertiefungslinsen und Synthese

Die analytischen Schichten (Metaphern, Gegenhorizonte, Praktiken, konjunktiver Erfahrungsraum) und die OR-Synthese sind Bestandteile des integrierten M-RI — als material-getriebene, ungleich gewichtete Linsen, nicht als separate Module. Wo eine Schicht besondere Tiefe verlangt, geschieht das innerhalb des M-RI. (Ältere separate Linsen-Module liegen im Archiv; Historie im _CHANGELOG.)

### Verdichtungsphase (M-VD · Auftakt der typenbildenden Interpretation)

Die Verdichtung ist das Zusammenfassen, mit dem die typenbildende Interpretation (M-TI) leise anhebt — die Brücke zwischen reflektierender Interpretation und Typenbildung.

- **M-VD-1 · Zusammenfassung der Reflektierenden Interpretation** pro Passage (`M-VD-1-Zusammenfassung-RI.md`).
- **M-VD-2 · Innerfall-Komparation** zwischen Passagen eines Falls, mindestens zwei Passagen erforderlich (`M-VD-2-Innerfall-Komparation.md`).
- **M-VD-3 · Fallzusammenfassung** integriert mehrere Passagen-Zusammenfassungen, identifiziert Einzeltypen am Fall (`M-VD-3-Fallzusammenfassung.md`).

### Typenbildende Interpretation (M-TI · Modus) und Typenbildung (M-TB · Operation)

Die typenbildende Interpretation (**M-TI**) ist der dritte Interpretationsmodus nach der formulierenden und der reflektierenden Interpretation. Sie ist *nicht* dasselbe wie „Typenbildung": M-TI ist der weitere *Modus* — ein Strom, der schon in der reflektierenden Interpretation anhebt (Aspekt-Strom, abduktiver Blitz), über die Verdichtung (M-VD) läuft und in der Typologie mündet; die **Typenbildung** (**M-TB**) ist die *Operation* in seinem Hauptlauf (Typiken, Typologien, soziogenetische Verortung). M-TI wiederholt den Vergleich und die Schlüsse der RI nicht, sondern verdichtet und prüft, was dort schon entstand: Reduktion, wo die RI Expansion war. Geordnet ist M-TB nicht nach Schlussformen, sondern nach Abstraktionsgraden — entlang der Aspekt-Leiter von den sinngenetischen und soziogenetischen Aspekten über die Einzeltypen am Fall zu den Typiken, Typologien und ihrer soziogenetischen Verortung. Die Schlussformen (abduktive Einsicht, als-ob-deduktive Verallgemeinerung, pragmatisch-induktive Prüfung) sind wiederkehrende Modi, keine Phasen.

- **M-TI · Typenbildende Interpretation — Überblick** (`M-TI-Typenbildende-Interpretation-Ueberblick.md`). Benennt den Modus, klärt sein Verhältnis zur reflektierenden Interpretation und die Abgrenzung zur Typenbildung, legt die Reihenfolge der Module fest.
- **M-TI-S · Schlussformen** (`M-TI-S-Schlussformen.md`). Querlaufende Referenz für die wiederkehrenden Modi der abduktiven Einsicht, der als-ob-deduktiven Verallgemeinerung und der pragmatisch-induktiven Prüfung (dilemmatisches Oszillieren statt planbarer Kreislauf).
- **M-TB-1 · Sinngenetische Typiken** (`M-TB-1-Sinngenetische-Typiken.md`). Hebt die Einzeltypen am Fall über die vergleichende Analyse und die schrittweise Abstraktion einer Vergleichsdimension auf Typiken; prüft sie an Material außerhalb der Hypothesenbildung. Enthält die Warnung vor dem vorschnellen Raster.
- **M-TB-2 · Typologien** (`M-TB-2-Typologien.md`). Setzt mehrere Typiken zu einer Typologie zusammen und klärt ihr Verhältnis zueinander.
- **M-TB-3 · Soziogenetische Rekonstruktion** (`M-TB-3-Soziogenetische-Rekonstruktion.md`). Verortet Einzeltypen, Typiken und Typologien in kollektiven Dimensionen (Korrespondenzen, keine Kausalitäten).
- **M-TB-R · Relationale Typenbildung** (`M-TB-R-Relationale-Typenbildung.md`; optional, bei mehreren Typologien).

### Schleifenmodul

- **M-TB-H · Vergleichshorizonte und Sample-Entwicklung** (`M-TB-H-Vergleichshorizonte-und-Sampleentwicklung.md`). Wird ausgelöst, wenn das Material für die Bildung oder Bewährung einer Typik nicht reicht. Steuert die methodisch kontrollierte Auswahl weiterer Vergleichsfälle und empfiehlt Erweiterung, Verzicht oder Aufschub.

### Cross-Cutting Q-Module (an Anlassstellen)

- **Q-1 · Begriffsdisziplin- und Stil-Check.** Prüft die methodologische Begriffs-Verwendung und die Stil-Treue gegen M-STIL.
- **Q-2 · Standortgebundenheits-Reflexion.** Reflektiert die Verortung an konkreten Stellen.
- **Q-3 · Reichweiten-Check.** Prüft die Reichweite der Aussagen.

### Parallele Timelines

- **TL-1 · Sampling-Timeline.** Dokumentiert chronologisch die Sample-Entwicklung im Prinzip der vergangenen Gegenwarten.
- **TL-2 · Typen-und-Theorie-Timeline.** Dokumentiert chronologisch die Genese der Typenhypothesen und Theoriebezüge.

## Maximen

### Erstens, Konversationsstützen statt prozedurale Abarbeitung

Die Module sind Dialog-Räume, keine Verfahren. Das Modell begegnet der forschenden Person im Gespräch, macht Vorschläge, stellt Rückfragen, dokumentiert Abweichungen, hält Mehrdeutigkeit aus. Die forschende Person bleibt souverän über die Modul-Wahl und über die methodologische Substanz.

Die Output-Form der interpretativen Module folgt M-STIL: kursorischer Fließtext mit langen Material-Zitaten, Konjunktiv für Hypothesen, ausgehaltene Mehrdeutigkeit, Sprache der Sprechenden im Wortlaut. Tabellen, Aspekt-Listen und Inventar-Übersichten stehen am Schluss der Modul-Outputs als Nachschlagwerk für die nachfolgenden Module, nicht als Sammelplatz der Interpretation.

### Zweitens, Vierklang-Verortung am Anfang

Vor jeder inhaltlichen Arbeit wird das Projekt in den vier Schichten der Architektur-Sektion oben verortet: Gegenstand → Grundlage → Methodologie → Methode. Alle vier Dateien laufen in jeder nachfolgenden Modul-Sitzung als Erstkontext mit. Die Schichtung ist konstitutiv: Jede Schicht begrenzt die nächste, auch wenn die Folge nicht deterministisch ist; nicht-organische Konstellationen werden in M-MET explizit gehalten. Die aktuelle Sammlung ist auf die dokumentarische Methode in praxeologischer Lesart ausgebaut (M-GT-1, M-MET-1, M-MTH-1 voll, M-GT-2/3 und M-MET-2/3 als Skelette).

### Dritte, Konversationsführung durch den Dirigenten

Der Dirigent ist die operative Konsequenz der verteilten Interpretation. Er kennt die Modul-Architektur und schlägt der forschenden Person aktiv vor, welches Modul an welcher Stelle sinnvoll wäre. Er entscheidet nicht, er empfiehlt. Er dokumentiert Abweichungen ohne Widerstand.

### Viertens, Mindestpassagen-Anforderung

Die dokumentarische Methode arbeitet konstitutiv mit Vergleich. Mindestens zwei Passagen pro Fall sind die Standardanforderung. Wenn nur eine Passage vorliegt, wird die Reichweite der Interpretation entsprechend eingeschränkt. M-00 macht das transparent; die RI-Tiefenarbeit im integrierten M-RI verlangt Vergleichsmaterial als Pflicht-Eingabeschicht.

### Fünftens, Komparation — und mit ihr Abduktion und Als-ob-Deduktion — in der Reflektierenden Interpretation

Die Komparation wird nicht in die Verdichtungsphase verschoben, sondern als Pflicht in die RI-Phase integriert. Das integrierte M-RI-Hauptmodul verlangt Vergleichsmaterial; ebenso die Vertiefungslinsen, falls sie aktiviert werden. Gegenhorizonte, Praktiken und konjunktive Erfahrungsräume gewinnen ihre analytische Kontur erst durch Kontrast mit anderen Passagen. Manche Gegenhorizonte werden sogar erst sichtbar, wenn ein Vergleichsfall vorliegt, der eine andere Bewegungsrichtung zeigt.

Mit der Komparation geschehen in der RI auch die beiden anderen typenbildenden Operationen: die **Abduktion** (die OR-Rekonstruktion *ist* der abduktive Schluss vom Wie aufs Orientierende) und die **Als-ob-Deduktion** (die OR-Hypothese wird am Vergleichsmaterial geprüft, bewährt oder spezifiziert). Die fallübergreifende Typenbildung (die Module der typenbildenden Interpretation) erzeugt diese Operationen daher nicht zum ersten Mal; sie konsolidiert die in den RIs schon paarweise vollzogene Komparation/Abduktion/Bewährung auf korpusweite Ebene und leistet das eine, was die einzelne RI nicht kann: die korpusweite Abstraktion des Tertiums und die nicht-zirkuläre Bewährung an Fällen außerhalb der Hypothesenbildung. Die Trennung in „RI-Phase" und „Typenbildungs-Phase" ist also eine Trennung von lokaler Erzeugung und korpusweiter Konsolidierung, nicht von „noch nicht" und „jetzt erst".

### Sechstens, Aspekt-Strom als durchgehende Operation, aber nachgelagert

Sinngenetische und soziogenetische Aspekte werden in M-RI vergeben, aber erst am Ende des Interpretationstexts als Nachschlagwerk-Inventar geführt, nicht parallel zum Schreiben in Tabellen-Spalten befüllt. In der Verdichtungsphase werden sie konsolidiert, in der Typenbildung als Material genutzt. Der Aspekt-Strom verbindet alle Phasen, ist aber Nachverdichtung der Interpretation, nicht ihre Strukturlogik.

### Siebtens, Schleifen statt linearer Kette

Vier methodologisch unterschiedliche Schleifen sind im Workflow angelegt. Die Diskonfirmations-Schleife innerhalb der Typenbildung, in der Bewährung in der Als-ob-Deduktion zu neuer Abduktion führt. Die Tertium-Spezifizierungs-Schleife vom Typologien-Aufbau zurück zur Komparativen Analyse. Die Theoretical-Sampling-Schleife von der Typenbildung zurück zu M-02 oder zur Erhebung. Die Q-Module-Rückkanäle, die Cross-Cutting-Befunde an die Hauptkette zurückspielen.

### Achtens, Prinzip der vergangenen Gegenwarten in den Timelines

Eintragungen in die Sampling- und in die Typen-und-Theorie-Timeline werden im damaligen Wissensstand gehalten, nicht nachträglich geglättet. Das macht die Forschungsgegenwart für spätere Rekonstruktionen sichtbar und schützt vor teleologischen Konstruktionen.

### Neuntens, rekonstruktive Disziplin (gegen die häufigsten Interpretationsfehler)

Diese Maxime bündelt die Korrekturen aus dem Durchlauf 2026-05-21. Der **Orientierungsrahmen ist ein modus operandi, keine Einstellung**: Er rekonstruiert das Wie der Praxis, nicht die Meinung, Selbstdeutung oder den Affekt der Sprechenden (Faustprobe: Würde die Sprecherin dem Satz einfach zustimmen, ist es noch ihre Haltung, nicht ihr Rahmen). Die **Form geht dem Inhalt voraus**: Der OR wird aus der formalen Ebene erzeugt, nicht durch sie nachträglich bestätigt; bei reportiven Passagen liegt der Zugriff im Wie des Erzählens, nicht im Inhalt des Berichteten. Die **Vergleichsdimension wird aus den Fällen gewonnen, nicht mitgebracht** (die Kontrolle des Interpreten-Vergleichshorizonts); wer entlang seiner Zieldimension sampelt, plausibilisiert nur, statt zu rekonstruieren. Die **Schlussformen sind keine Etiketten**: Abduktion setzt eine Überraschung voraus (eine vorab feststehende, nur erfüllte Hypothese ist Konfirmation), und ein Kontrastfall korroboriert die Dimension, nicht den Typ — eine „Bewährung in der Differenz" gibt es nicht. Schließlich werden **KER, Schema und Ausdruck getrennt**: eine geteilte Norm oder ein geteiltes Vokabular ist kommunikatives Schema, ein geteilter Affekt ist Ausdruck eines KER, nicht der KER selbst.

### Zehntens, Selbstkontrolle gegen Glättung und Schein

Modelle, die diese Outputs schreiben, neigen zu Über-Systematisierung, zu Schein-Mehrdeutigkeit (eine zweite Lesart einführen und sofort kassieren), zu Caveat-Inflation (Vorbehalte, die eine Über-Reichweite lizenzieren statt sie zu senken) und zu verstecktem Eigen-Schema (formgleiche Outputs über mehrere Passagen). M-STIL hält die Gegenmaßnahmen als Negativ-Maximen fest. Drei strukturelle Sicherungen ergänzen sie: **Beispiele in Modul-Dateien dürfen nie aus dem zu interpretierenden Korpus stammen** (sonst gibt das Modul die erwartete Lesart vor); **Q-Korrekturen sind verbindlich einzuarbeiten**, nicht nur zu notieren (sonst bleibt es bei der performativen Korrektur); und eine **Zu-glatt-Gegenprobe** — was im Material widersteht der Ordnung? — gehört in jede Typik-Bildung.

## Aspekt-Strom durch den Workflow

Erstens, in der RI-Tiefenarbeit (im integrierten M-RI) werden sinngenetische und soziogenetische Aspekte vergeben, jeweils mit Stellenverweis und zweisätziger Charakterisierung.

Zweitens, in der OR-Synthese (im integrierten M-RI) werden die Aspekte konsolidiert. Doppelvergaben werden erkannt, Spannungen markiert, Reichweiten neu vergeben.

Drittens, in der Zusammenfassung der Reflektierenden Interpretation werden die Aspekte in Tabellenform aufgelistet.

Viertens, in der Fallzusammenfassung werden die Aspekte über mehrere Passagen integriert. Aus den konsolidierten Aspekten entstehen sinngenetische Einzeltypen am Fall.

Fünftens, in der Typenbildenden Interpretation werden die Aspekte und Einzeltypen fallübergreifend zu Typiken und Typologien verdichtet.

Sechstens, in der soziogenetischen Rekonstruktion werden die soziogenetischen Aspekte zur Verortung der Typologien genutzt.

## Schleifen im Überblick

- **Diskonfirmations-Schleife (innerhalb Typenbildung):** Wenn die pragmatisch-induktive Prüfung einer Typik an unabhängigem Material negativ ausfällt, geht es zurück zur abduktiven Einsicht, und die Typik wird neu gefasst — ein dilemmatisches Oszillieren zwischen Allgemeinem und Besonderem.
- **Vergleichsdimensions-Schleife (innerhalb Typenbildung):** Von der Typologie zurück zu den sinngenetischen Typiken, falls die Vergleichsdimension nachjustiert werden muss (sukzessives Abstrahieren der Vergleichsdimension).
- **Vergleichshorizont-Schleife:** Wenn die Hypothesen im bestehenden Sample nicht hinreichend bewährbar sind, geht es über das M-TB-H (Vergleichshorizonte und Sample-Entwicklung) zurück zur Passagenauswahl oder zur Erhebung.
- **Q-Module-Rückkanäle:** Cross-Cutting-Module produzieren Befunde, die Korrekturen an Modulen der Hauptkette auslösen können.

## Zur Anwendung in der Forschungspraxis

Der Workflow wird selten in der vollen Breite linear durchlaufen. Vielmehr werden die Module je nach Sitzungs-Ziel und Stand der Interpretation aktiviert. Der Dirigent hilft bei der Navigation.

Eine typische Sitzung im laufenden Projekt könnte etwa so aussehen: M-00 öffnet die Sitzung mit knapper Bestandsaufnahme, M-DIR schlägt die nächste Modul-Aktivierung vor, ein oder zwei inhaltliche Module laufen, M-DIR wird wieder angesprochen, die Sitzung wird geschlossen, die Timelines werden aktualisiert.

Im RI-Bereich schlägt der Dirigent das integrierte M-RI als Default vor und greift eine einzelne Schicht nur dann gesondert auf, wenn der M-RI-Output zeigt, dass eine Linse eine vertiefte separate Behandlung lohnt — und auch dann nur die, die wirklich trägt, nicht alle vier symmetrisch.

<!-- Passage am 24.08.2026 rekonstruiert, Original durch Dateischaden verloren. -->
