# Sportgeräteverleih – Beschreibung der Funktionen

## Ziel
Mit diesem Programm kann man Sportgeräte wie Ski, Velos oder Bälle ausleihen. Man sieht, welche Geräte frei sind, leiht sie aus und gibt sie wieder zurück.

## Szenen
**Login:** Man gibt Benutzername und Passwort ein. Das Passwort wird nicht angezeigt. Wenn etwas falsch ist, erscheint eine Fehlermeldung. Sonst kommt man ins Hauptfenster. Neue Benutzer klicken auf den Button «Noch kein Konto? Konto erstellen».

**Registrieren (Zusatzaufgabe):** Vorname, Nachname, Benutzername, E-Mail und zweimal das Passwort eingeben. Die Angaben werden in einer Datei gespeichert. Danach geht es zurück zum Login mit der Meldung «Konto erstellt».

**Hauptfenster:** Links wählt man eine Kategorie, z. B. Ski oder Velo. In der Mitte steht die Geräteliste (Buttons in einem ScrollPane). Klickt man auf ein Gerät, erscheinen rechts ein Platzhalter für das Bild, eine Beschreibung, der Preis und der Button «Ausleihen».

**Dialog Ausleihen:** Man gibt die Anzahl Tage in ein TextField ein. Der Gesamtpreis wird ausgerechnet. «Bestätigen» speichert die Ausleihe, «Abbrechen» schliesst das Fenster.

**Meine Ausleihen:** Zeigt die eigenen Ausleihen mit Datum und Preis. Mit «Zurückgeben» wird ein Gerät wieder frei, «Zurück zur Übersicht» führt zum Hauptfenster.

## Ablauf
Login und Registrieren hängen zusammen. Nach dem Anmelden kommt man ins Hauptfenster, mit «Abmelden» wieder zurück. Vom Hauptfenster kommt man zu Meine Ausleihen und wieder zurück. Der Dialog führt zurück zum Hauptfenster.

## Fehler und Hinweise
- Leere Felder oder falsches Login: Fehlermeldung
- Passwörter verschieden oder Benutzername schon vergeben: Fehlermeldung
- Kein Gerät ausgewählt: Hinweis «Bitte zuerst ein Gerät auswählen»
- Anzahl Tage: mindestens 1
- Keine Ausleihen: kurzer Hinweis

## Umsetzung
Ich baue das Projekt mit JavaFX und Maven. Die Oberflächen erstelle ich im SceneBuilder (FXML). Die Abläufe programmiere ich in Meilenstein 3.
