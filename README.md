# Sportgeräteverleih – Meilenstein 2 (M322)

JavaFX-Projekt für den Sportgeräteverleih. In Meilenstein 2 ist nur das **Layout** umgesetzt
(FXML-Dateien aus SceneBuilder + CSS). Die Funktionalität (Login prüfen, Szenen wechseln,
Ausleihen usw.) folgt in Meilenstein 3.

## Starten

Voraussetzungen: JDK 17, Maven, VS Code mit dem Java Extension Pack.

```
mvn clean javafx:run
```

Die Anwendung startet mit der Login-Szene. Die anderen Szenen kann man in SceneBuilder
öffnen und mit *Preview > Show Preview in Window* anschauen. Zum Testen kann man auch in
`App.java` bei `loadFXML("login")` einen anderen Namen eintragen, z. B. `"hauptfenster"`.

## Aufbau

```
src/main/java/
  module-info.java
  ims/sargans/
    App.java                        Startklasse, startet mit login.fxml
    LoginController.java            Szene 1: Login
    RegistrierenController.java     Zusatzaufgabe: Registrierung
    HauptfensterController.java     Szene 2: Hauptfenster
    AusleihenDialogController.java  Dialog Gerät ausleihen
    MeineAusleihenController.java   Szene 3: Meine Ausleihen
src/main/resources/ims/sargans/
  login.fxml                        Szene 1: Login (HBox mit zwei Hälften)
  registrieren.fxml                 Zusatzaufgabe: Registrierung (gleicher Aufbau wie Login)
  hauptfenster.fxml                 Szene 2: Hauptfenster (BorderPane)
  ausleihen_dialog.fxml             Dialog Gerät ausleihen (VBox)
  meine_ausleihen.fxml              Szene 3: Meine Ausleihen (BorderPane)
  style.css                         Design (Farben, Buttons, Liste)
```

Die Controller enthalten nur die `@FXML`-Felder (fx:id) und leere Event-Handler
wie `handleAnmelden(ActionEvent e)`, die in der FXML-Datei mit `onAction="#handleAnmelden"`
verbunden sind. Diese werden in Meilenstein 3 ausprogrammiert.

## Layout, Style und Code getrennt

- **Layout (FXML):** BorderPane, HBox, VBox, GridPane, ScrollPane, StackPane und Pane (als Abstandhalter, der mitwächst)
- **Style (CSS):** `style.css` mit Typen-Selektoren (`TextField`), Klassen-Selektoren
  (`.button-primaer`) und Pseudoklassen (`:hover`, `:pressed`, `:focused`). Das Stylesheet wird
  in `App.java` mit `scene.getStylesheets().add(...)` eingebunden. In den FXML-Dateien ist es
  zusätzlich eingetragen, damit SceneBuilder die Vorschau mit dem richtigen Design zeigt.
- **Code (Java):** Startklasse `App` und je ein Controller pro FXML-Datei

## Verwendete Elemente

Label, Button, TextField, PasswordField, ScrollPane und StackPane.
Die Geräte im Hauptfenster sind normale Buttons in einer VBox, die in einem ScrollPane steht.
Der Platzhalter für ein späteres Bild ist ein graues Feld (StackPane) mit einem X.
Die Anzahl Tage im Dialog gibt man in ein TextField ein.
Der Link zwischen Login und Registrierung ist ein Button, der mit CSS wie ein Link aussieht.

## Zusatzaufgabe Registrierung

Auf der Login-Seite führt der Button «Noch kein Konto? Konto erstellen» zur Registrierung.
Dort gibt man Vorname, Nachname, Benutzername, E-Mail und zweimal das Passwort ein.
Die Felder stehen in einem GridPane mit zwei Spalten, damit alles auch im kleinsten
Fenster Platz hat. Der Button «Bereits ein Konto? Zur Anmeldung» führt zurück zum Login.
Das Speichern der Benutzerdaten in einer Datei folgt in Meilenstein 3.

## Fenstergrösse

Startgrösse 900 × 600, kleinste Grösse 800 × 550. Das Layout wurde in 800 × 550, 900 × 600
und 1280 × 800 getestet: Listen und Bereiche wachsen mit, nichts wird abgeschnitten.
