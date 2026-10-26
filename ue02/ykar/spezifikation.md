# Spezifikation des Terminplaners — Gliederung und Beispiele

Mitgearbeitet haben (GitHub-Benutzernamen, auch bei Einzelarbeit): @YunusKaradag76

## 1 Einleitung

### 1.1 Zweck des Dokuments

Dieses Dokument beschreibt alle Anforderungen an den Terminplaner der THM. Es richtet sich an das Entwicklerteam und ist die einzige verbindliche Grundlage für Konstruktion und Implementierung.

### 1.2 Ausgangssituation und Ziele

Bisher vereinbaren Studierende Sprechstunden per E-Mail. Das führt zu vielen Rückfragen und Doppelbuchungen. Ziel: Studierende buchen freie Termine selbst online, ohne E-Mail-Verkehr.

### 1.3 Abgrenzung

Nicht Teil des Systems sind die Buchung von Räumen und die Planung von Prüfungsterminen.

### 1.4 Begriffe (Glossar)

| Begriff | Bedeutung |
| --- | --- |
| Sprechstunde | Zeitblock, den eine Lehrender anbietet (z. B. Di 10–12 Uhr) |
| Termin | Einzelner buchbarer Slot innerhalb einer Sprechstunde (z. B. 15 Min.) |

## 2 Nutzerrollen und Stakeholder

| Rolle | Darf … |
| --- | --- |
| Studierende | freie Termine sehen, buchen, absagen |
| Lehrende | Sprechstunden anlegen, Buchungen sehen, Termine absagen |
| Admin | Nutzer und Rollen verwalten |

## 3 Funktionale Anforderungen

### 3.1 Termine anlegen und verwalten (Lehrende)

F-01: Lehrende können eine Sprechstunde mit Datum, Uhrzeit, Raum und Slot-Länge (10/15/30 Min.) anlegen. Das System teilt die Sprechstunde automatisch in einzelne Termine auf.

### 3.2 Termine suchen und buchen (Studierende)

F-05: Studierende sehen alle freien Termine eines*einer Lehrenden und können genau einen Termin pro Sprechstunde buchen. Optional geben sie ein Thema an (max. 200 Zeichen).

### 3.3 Absagen, Verschieben, Benachrichtigungen

F-09: Sagt eine Lehrender eine Sprechstunde ab, erhalten alle gebuchten Studierenden automatisch eine E-Mail. Studierende können bis 2 Stunden vor Beginn selbst absagen.

### 3.4 Verwaltung (Admin)

F-12: Der Admin kann einer Person die Rolle „Lehrende“ zuweisen oder entziehen.

## 4 Datenmodell (fachliche Objekte)

Objekt Termin: ID, Beginn, Ende, Status (frei / gebucht / abgesagt), zugehörige Sprechstunde, gebucht von (Studierende\*r), Thema.

Eine Sprechstunde hat 1 bis n Termine, ein Termin gehört zu genau einer Sprechstunde.

## 5 Benutzeroberfläche

Beschriebene Skizze: Startseite Studierende: oben Suchfeld „Lehrende suchen“, darunter eine Wochenansicht. Freie Termine erscheinen grün, belegte grau. Ein Klick auf einen grünen Termin öffnet ein Fenster mit dem Button „Buchen“.

## 6 Schnittstellen und Rahmenbedingungen

Die Anmeldung erfolgt über den bestehenden THM-Account (Single Sign-On). Gebuchte Termine können als `.ics`-Datei exportiert und so in Outlook übernommen werden.

## 7 Nicht-funktionale Anforderungen

- NF-02: Die Seite muss auf Smartphones vollständig bedienbar sein.
- NF-05: Personenbezogene Daten werden 6 Monate nach dem Termin gelöscht (DSGVO).

## 8 Abnahmekriterien

Testfall zu F-05: Ein Studierender bucht einen freien Termin. Danach ist der Termin für alle anderen als „belegt“ angezeigt, und der Lehrende sieht die Buchung in seiner Übersicht.

## 9 Offene Punkte

Noch zu klären mit der THM: Sollen auch Gruppentermine möglich sein, also mehrere Studierende in einem Slot?
