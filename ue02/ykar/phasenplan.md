# Phasenplan — Terminplaner für die THM

Kürzel: ykar

## Studie

**Ergebnis der Phase:** Studie mit Machbarkeit, Aufwandsschätzung und Meilensteinplan als Entscheidungsgrundlage für den Auftrag

- Eigenentwicklung, Anpassung einer Open-Source-Lösung und Kauf nebeneinanderstellen und nach Kosten und Nutzen bewerten
- Die heutige Lage aufnehmen: wie Sprechstunden und Prüfungstermine bisher vereinbart werden und wo es hakt
- Aufwand schätzen und einen Meilensteinplan vorschlagen
- Mit einem technischen Prototyp prüfen, ob die Anmeldung über das Hochschulkonto funktioniert

## Systemspezifikation

**Ergebnis der Phase:** Systemspezifikation: Beschreibung der Anforderungen (Abläufe, Daten, Schnittstellen) samt Systemtestfällen

- Mit Lehrenden und Sekretariaten Schritt für Schritt beschreiben, wie ein Sprechstundentermin gebucht wird
- Festlegen, welche Vorgänge ein KI-Agent über die API auslösen darf — z.B. freie Termine abfragen und buchen, aber keine Prüfungstermine absagen
- Bildschirmskizzen der Buchungsseite mit Studierenden durchgehen
- Festlegen, welche Angaben zu einem Termin gehören und wie Termine, Personen und Räume zusammenhängen
- Beschreiben, welche Termindaten mit dem Kalendersystem der Hochschule ausgetauscht werden
- Testfälle formulieren, an denen sich später zeigt, ob das System leistet, was vereinbart wurde

## Systemkonstruktion

**Ergebnis der Phase:** Systemkonstruktion: Architektur mit Komponenten, Schnittstellen und Technologieauswahl

- Das System in Komponenten zerlegen — z.B. Terminverwaltung, Benachrichtigung, Anmeldung — und deren Schnittstellen festlegen
- Datenbank, Programmiersprache und Web-Framework auswählen
- Die API entwerfen: Endpunkte, Datenformat und die Anmeldung der KI-Agenten festlegen
- Festlegen, in welcher Reihenfolge die Komponenten gebaut werden und welche Zwischenziele gelten

## Implementierung

**Ergebnis der Phase:** Implementierte und einzeln getestete Komponenten

- Die Komponente „Benachrichtigung“ programmieren
- Die fertige Komponente „Terminverwaltung“ für sich testen, ehe sie mit anderen zusammenkommt

## Integration & Einführung

**Ergebnis der Phase:** Integriertes, gegen die Testfälle geprüftes und vom Auftraggeber abgenommenes System im Betrieb

- Terminverwaltung und Benachrichtigung zusammenführen und ihr Zusammenspiel gegen Testfälle prüfen
- Das System als Ganzes unter Federführung des Qualitätsbeauftragten gegen die Testfälle prüfen
- Mit einem KI-Agenten prüfen, ob sich ein Sprechstundentermin vollständig über die API buchen lässt
- Die THM installiert das System in ihrer eigenen Umgebung und prüft es in eigener Verantwortung
- Probebetrieb mit einem Fachbereich, ehe die ganze Hochschule umsteigt

## Wartung

**Ergebnis der Phase:** Laufend gepflegtes System: behobene Fehler und nachgerüstete Funktionen

- Einen Fehler bei der Zeitumstellung beheben, den ein Sekretariat gemeldet hat
- Eine Warteliste für ausgebuchte Termine nachrüsten, die sich die Lehrenden nach einem Semester wünschen
- Eine Hotline für Fragen der Anwenderinnen und Anwender besetzen

## Bei welchen Karten waren Sie unsicher — und was haben Sie abgewogen?

- **Die heutige Lage aufnehmen: wie Sprechstunden und Prüfungstermine bisher vereinbart werden und wo es hakt** (Studie): Das Erfassen der Ist-Situation könnte schon zur Spezifikation gehören, dient hier aber vor allem dazu zu entscheiden, ob und wie das Projekt sinnvoll ist – daher Studie.
- **Eine Hotline für Fragen der Anwenderinnen und Anwender besetzen** (Wartung): Die Hotline wird erst mit der Einführung nötig, ihr Schwerpunkt ist aber der laufende Betrieb und die Betreuung der Nutzenden – daher Wartung statt Einführung.
- **Die API entwerfen: Endpunkte, Datenformat und die Anmeldung der KI-Agenten festlegen** (Systemkonstruktion): Welche Vorgänge die API anbietet, wäre Spezifikation; Endpunkte, Datenformat und Anmeldung sind jedoch technischer Entwurf – daher Systemkonstruktion.
- **Mit einem technischen Prototyp prüfen, ob die Anmeldung über das Hochschulkonto funktioniert** (Studie): Ein Prototyp ähnelt der Implementierung, soll hier aber nur die Machbarkeit klären und wird nicht Teil des Systems – daher Studie.
- **Eine Warteliste für ausgebuchte Termine nachrüsten, die sich die Lehrenden nach einem Semester wünschen** (Wartung): Eine neue Funktion könnte wie in der Spezifikation beschrieben werden, entsteht aber als Änderungswunsch nach dem Betrieb – daher Wartung.
- **Festlegen, in welcher Reihenfolge die Komponenten gebaut werden und welche Zwischenziele gelten** (Systemkonstruktion): Die Planung gehört auch zur Studie (Meilensteine), die Reihenfolge der Komponenten folgt jedoch aus der Zerlegung des Systems – daher Systemkonstruktion.
- **Mit einem KI-Agenten prüfen, ob sich ein Sprechstundentermin vollständig über die API buchen lässt** (Integration & Einführung): Es ist ein Test über die gesamte Kette, der erst möglich ist, wenn die Komponenten zusammengeführt sind – daher Integration statt Implementierung.

<!-- zuordnung ue02-phasenplan: k01=implementierung k02=studie k03=integration k04=spezifikation k05=wartung k22=spezifikation k06=konstruktion k07=studie k08=integration k09=konstruktion k10=spezifikation k11=wartung k12=implementierung k23=konstruktion k13=studie k14=spezifikation k15=studie k16=integration k17=wartung k18=konstruktion k19=spezifikation k24=integration k20=integration k21=spezifikation | unsicher: k07 k11 k23 k15 k17 k18 k24 -->
