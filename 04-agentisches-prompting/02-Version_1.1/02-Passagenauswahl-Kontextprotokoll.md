---
kürzel: M-02
art: modul
titel: "M-02 · Passagenauswahl und Kontextprotokoll"
fassung: ueberarbeitete_arbeitsfassung
instruktionsfassung: ueberarbeitete_arbeitsfassung_2026-09-25
erstellt: 2026-09-24
geaendert: 2026-09-25
status: nicht_erprobt
im_dokumentierten_durchlauf_verwendet: false
---

# M-02 · Passagenauswahl und Kontextprotokoll

Lies diese Datei vollständig. Für Zusammenarbeit, Freigabe und Speicherung gelten M-INT, für die Darstellung M-STIL. Die Auswahl ist ein eigener Arbeitsschritt; die Interpretation beginnt erst anschließend.

## Arbeitsgrundlagen und Auswahl

Benötigt werden das Originaltranskript und der thematische Verlauf aus M-01. Greife dessen Vorschläge auf und kläre mit der forschenden Person, welche Passage dem Forschungszweck dient. Fehlt der Verlauf, benenne die begrenzte Auswahlgrundlage. Ist nur ein bereits ausgewählter Ausschnitt vorhanden, kann dessen lokale Eignung geprüft, aber keine begründete Auswahl aus dem unbekannten Gesamttranskript behauptet werden.

Begründe die Auswahl an thematischer Relevanz und erkennbarer analytischer Ergiebigkeit: etwa interaktiver Verdichtung, ausführlicher Darstellung einer Praxis, wiederkehrenden Formulierungen, bildhaften Wendungen oder auffälligen Abschlüssen. Solche Hinweise rechtfertigen die nähere Untersuchung, legen ihren dokumentarischen Befund aber nicht fest. Eine bestimmte Zahl von Absätzen ist kein Maß für die Güte der Passage.

Prüfe die Grenzen des Ausschnitts. Worauf antwortet sein erster Beitrag? Wird ein Gesprächszusammenhang am Ende abgeschnitten? Schlage gegebenenfalls eine Erweiterung vor. Der Status des Einstiegs wird zunächst als eigenständige Eröffnung, Anschluss oder unklar beschrieben. Ob eine methodisch bestimmte Proposition vorliegt, ist in M-RI-2a am Verlauf zu prüfen; nicht jede eröffnende Moderationsfrage ist bereits eine Proposition im dokumentarischen Sinn.

Mehrere Passagen ermöglichen die fallinterne Prüfung. Vereinbare, ob weitere Ausschnitte folgen oder zunächst eine passagengebundene Analyse beabsichtigt ist. Bei mehrteiligem Design richtet sich die Auswahl danach, welche Gegenstände oder Erhebungssituationen tatsächlich verglichen werden sollen. Eine Prüfung zwischen Teil A und Teil B verlangt Material aus beiden Teilen; sie wird nicht aus einer einzelnen Passage abgeleitet.

## Wortgetreue Extraktion

Übernimm den vereinbarten Bereich vollständig aus dem Original. Erhalte Sprecherkennungen, Transkriptionszeichen, Pausen, Lachen, Überlappungen und markierte Unverständlichkeiten. Korrigiere keine vermeintlichen Sprachfehler. Ergänze eine lokale Nummerierung nur bei Bedarf und weise ihre Zuordnung zu den Originalstellen aus. Gliedere oder nummeriere so, dass der Wortlaut unverändert bleibt; füge keine erfundenen Redebeiträge hinzu.

Prüfe Anfang, Ende und Vollständigkeit gegen das Original. Bei sehr langen Passagen zeige Teilstücke in ihrer Reihenfolge und führe sie anschließend vollständig zusammen. Wenn die Extraktion technisch nicht vollständig gelingt, benenne die fehlenden Stellen. Eine gekürzte Abschrift ist nicht als vollständige Passage zu speichern.

## Kontextprotokoll

Das gesonderte Protokoll enthält:

1. **Status des Einstiegs:** Eigenständige Eröffnung oder Anschluss; bei Anschluss genaue vorangehende Stelle und, soweit nötig, deren Wortlaut.
2. **Außenreferenzen:** Bezüge auf andere Passagen, Personen oder Ereignisse. Trenne erkennbare Referenz, tatsächlich vorliegende Bezugsstelle und noch ungeklärten Bezug. Spekuliere nicht über fehlende Inhalte.
3. **Auswahlbegründung:** Forschungszweck, beobachtbare Auswahlhinweise und gegebenenfalls geprüfte Alternativen. Die Entscheidung der forschenden Person und eine abweichende Empfehlung werden unterscheidbar festgehalten.
4. **Verortung im Gesamtverlauf:** Themenzusammenhang, Erhebungsphase, vorausgehende und folgende Abschnitte sowie relevante Moderationsimpulse.

Hinweise für M-FI betreffen offene Bezüge oder unklare thematische Grenzen, nicht vorweggenommene Orientierungsrahmen. Die spätere Interpretation kann eine erneute Auswahl oder Erweiterung nahelegen.

## Zwei Ergebnisdateien

Zeige und speichere zuerst die Extraktion, danach das Kontextprotokoll, jeweils mit eigener Freigabe. Beide Dateien verwenden dieselbe Fall- und Passagenkennung und verweisen aufeinander. Die Dokumenttypen bleiben unterscheidbar.

```yaml
fall: <Fall>
passage: <Passagenname>
passagenkennung: passage-<NN>-<kurzname>
modul: M-02
instruktionsfassung: ueberarbeitete_arbeitsfassung_2026-09-25
datum: <YYYY-MM-DD>
status: entwurf
version: 1
ersetzt: null
quelle: <Originaltranskript>
originalbereich: <Stellenangabe>
input_M01: <Datei oder nicht vorhanden>
vergleichsstand: <weitere Passagen vorhanden|geplant|vorerst einzelne Passage>
zugehoerige_datei: <Extraktion bzw. Kontextprotokoll>
```

Die **Extraktionsdatei** ergänzt `typ: transkriptpassage`. Unter „Quelle und Nummerierung“ steht die Zuordnung zum Original; unter „Passage“ folgt der vollständige unveränderte Wortlaut mit Stellenangaben. Keine analytischen Kommentare werden zwischen die Beiträge eingeschoben.

Die **Kontextdatei** ergänzt `typ: passagenauswahl_mit_kontextprotokoll`. Sie enthält „Gesprächsspur (verdichtet)“, „Kontextprotokoll“ mit den vier Unterabschnitten, „Empfehlungen für M-FI“, „Auswahl-Memo“ und gegebenenfalls „Rückmeldungen an vorgelagerte Module“.

## Speicherung und Anschluss

Speichere im Fallordner unter `02-passage-<NN>-<kurzname>.md` und `02-kontextprotokoll-<NN>-<kurzname>.md`. Die Stellenzuordnung bleibt bei jeder Weiterverwendung erhalten. Für Revisionen gelten die Versionsregeln aus M-INT und die Dateinamen aus `Anleitung-Workflow-Durchspielen.md`.

Nach beiden Speicherungen folgt normalerweise M-FI. Schlage hier auch eine Sitzungszäsur vor, wenn der Umfang einen neuen Chat nahelegt. M-00 übergibt dann beide Dateien und den thematischen Verlauf. Die Auswahlentscheidung wird für TL-1 festgehalten; dies ersetzt nicht das Kontextprotokoll.
