# Erste Leaflet Karte mit Marker und Popup

## Zutaten

- Browser & Visual Studio Code
- Leafletbibliothek unter <https://leafletjs.com>
- Template: [first_leaflet_map.html](https://github.com/openwebcc/cookbook/blob/main/templates/first_leaflet_map.html) mit einem Visual Studio Code *"html 5"* Baustein als Grundgerüst

## Ablauf

1. das Template [first_leaflet_map.html](https://github.com/openwebcc/cookbook/blob/main/templates/first_leaflet_map.html) kopieren und dort weiterarbeiten 🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/21fd73f5abd44186937685c1404843dafadcadc5)

2. den Kartenbereich vorbereiten

    - ein DIV Element mit einem ID Attribut `map` hinzufügen

        ```html
        <div id="map"></div>
        ```

        🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/4bcb99608f340c390b2123af972935bd12616c9b)

    - die zukünftige Kartenfläche über eine STYLE Element im HEAD Bereich festlegen - die Karte wird 90% der Fensterbreite einnehmen, 600 Pixel hoch sein und einen hellgrauen Rahmen aufweisen

        ```html
        <style>
            #map {
                width: 90%;
                height: 600px;
                border: 1px solid silver
            }
        </style>
        ```

        🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/a6dce0c7290d2af75a3d07b9d4e2ffb1c2751f93)

3. die Leaflet Bibliothek einbinden

    - der Codeblock zum Einbinden der Leaflet Bibliothek im HEAD Bereich von `index.html` kommt von der Leaflet-Download Seite unter <https://leafletjs.com/download.html> und verlinkt die Leaflet CSS und Javascript Dateien

        ```html
        <head>
            <!-- Leaflet Bibliothek -->
            <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.3/dist/leaflet.css" integrity="sha256-kLaT2GOSpHechhsozzB+flnD+zUyjE2LlfWPgU04xyI=" crossorigin="" />
            <script src="https://unpkg.com/leaflet@1.9.3/dist/leaflet.js" integrity="sha256-WBkoXOwTeyKclOHuWtc+i2uENFpDZ9YPdf5Hf+D7ewM=" crossorigin=""></script>
        </head>
        ```

        🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/f72cb3b6be012aeb1b19aa3f0642f5565375d7d6)

4. den Javascript Code für die Karte erstellen

    - unmittelbar nach dem DIV Element der Karte ein SCRIPT Element für die Javascript Befehle einfügen

        ```html
            <script>

            </script>
        ```

        🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/363a3866659626bd02a48ffba2cb396f8d2c1912)

    - die Karte im DIV mit der ID `map` initialiseren und im Zoomlevel 13 auf die Koordinaten von Innsbruck (siehe [Wikipedia-Eintrag für Innsbruck](https://de.wikipedia.org/wiki/Innsbruck)) blicken.

        ```javascript
        let map = L.map("map");
        map.setView([47.267222, 11.392778], 13);
        ```

        🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/1945f7f03e061acd78ac5df3d7909a2470b8250a)

        > siehe Dokumentation [L.map()](https://leafletjs.com/reference.html#map) und [.setView()](https://leafletjs.com/reference.html#map-setview)

    - einen WMTS Hintergrundlayer für die OpenStreetMap zur Karte hinzufügen

        ```javascript
        L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
            attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
        }).addTo(map);
        ```

        🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/d5bed14eeb91db843e0c816f385bc7400248f2ff)

        > siehe Dokumentation [L.tileLayer()](https://leafletjs.com/reference.html#tilelayer) und [.addTo()](https://leafletjs.com/reference.html#tilelayer-addto)
        >

    - einen Marker mit Popup im Kartenmittelpunkt erstellen und das Popup öffnen

        ```javascript
        let marker = L.marker([47.267222, 11.392778]).addTo(map);
        marker.bindPopup("Innsbruck");
        marker.openPopup();
        ```

        🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/631f341b50a123219b065ecf1802e2c67cac5dfa)

        > siehe Dokumentation [L.marker()](https://leafletjs.com/reference.html#marker), [.addTo()](https://leafletjs.com/reference.html#marker-addto), [.bindPopup()](https://leafletjs.com/reference.html#marker-bindpopup) und  [.openPopup()](https://leafletjs.com/reference.html#marker-openpopup)
        >
        > Hinweis: im Popup sind auch HTML Formatierungen zulässig
        >
        > Hinweis: über Template-Syntax (z.B. \`Popup mit ${someVar}\`) sind im Popup auch Variablen verwendbar

## Ergebnis

[Erste Leaflet Karte mit Marker und Popup Beispiel](https://openwebcc.github.io/cookbook/examples/first_leaflet_map.html) ([Source](https://github.com/openwebcc/cookbook/blob/main/examples/first_leaflet_map.html))

___
[Inhaltsverzeichnis](https://openwebcc.github.io/cookbook/index)
