# Leaflet Provider Plugin für Hintergrundlayer

## Zutaten

- das Leaflet Provider Plugin unter <https://github.com/leaflet-extras/leaflet-providers>
- Template: [plugin_leaflet_provider.html](https://github.com/openwebcc/cookbook/blob/main/templates/plugin_leaflet_provider.html) mit der Grundkarte aus dem Rezept *[Erste Leaflet Karte mit Marker und Popup](https://openwebcc.github.io/cookbook/first_leaflet_map)*

## Ablauf

1. das Template [plugin_leaflet_provider.html](https://github.com/openwebcc/cookbook/blob/main/templates/plugin_leaflet_provider.html) kopieren und dort weiterarbeiten 🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/07301f67d5bbc65ee6b01ce5527327422d697e69)

2. das Leaflet Provider Plugin einbinden

    - Suche bei <https://cdnjs.com> nach *"leaflet-provider"* liefert <https://cdnjs.com/libraries/leaflet-providers>

    - Einbau in `index.html` über "*Copy Script Tag"* (\</>) Icon beim Suchergebnis

        ```html
        <!-- Leaflet Provider -->
        <script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet-providers/1.13.0/leaflet-providers.js" integrity="sha512-pb9UiEEi2JIxkMloqYnqgONe9CTcp2BWWq1Hbz60l7f3R3VhZ57dEE58Ritf/HgBw3o/5Scf5gg0T9V+tf48fg==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
        ```

        🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/3d5f5e62d5e27badb206622f100ab4ad76fa82a4)

3. das Leaflet Provider Plugin im SCRIPT Element verwenden

    - den bestehenden `L.tileLayer` Aufruf durch einen Aufruf an das Plugin ersetzen. Als *Provider string* verwenden wir den Standardlayer der <https://basemap.at> für Österreich

        ```javascript
        L.tileLayer.provider('BasemapAT.basemap').addTo(map);
        ```

        🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/d05c7a6bf77fc39238b104c08897ae1e3885e69b)

        > siehe Dokumentation [Leaflet-providers Usage](https://github.com/leaflet-extras/leaflet-providers#usage)

    - über die Demoseite <http://leaflet-extras.github.io/leaflet-providers/preview/index.html> sind alle verfügbaren Tilelayer wählbar

        - Beispiele für weltweit verfügbare Tilelayer

            ```javascript
            L.tileLayer.provider('OpenStreetMap.Mapnik');
            L.tileLayer.provider('OpenTopoMap');
            L.tileLayer.provider('Stamen.TonerLite');
            L.tileLayer.provider('Stamen.Watercolor');
            L.tileLayer.provider('Esri.WorldStreetMap');
            L.tileLayer.provider('Esri.WorldTopoMap');
            L.tileLayer.provider('Esri.WorldImagery');
            L.tileLayer.provider('CartoDB.Positron');
            L.tileLayer.provider('CyclOSM');
            ```

        - basemap.at Tilelayer für Österreich

            ```javascript
            L.tileLayer.provider('BasemapAT.basemap');
            L.tileLayer.provider('BasemapAT.grau');
            L.tileLayer.provider('BasemapAT.highdpi');
            L.tileLayer.provider('BasemapAT.terrain');
            L.tileLayer.provider('BasemapAT.surface');
            L.tileLayer.provider('BasemapAT.orthofoto');
            L.tileLayer.provider('BasemapAT.overlay');
            ```

## Ergebnis

[Leaflet Provider Plugin für Hintergrundlayer Beispiel](https://openwebcc.github.io/cookbook/examples/plugin_leaflet_provider.html) ([Source](https://github.com/openwebcc/cookbook/blob/main/examples/plugin_leaflet_provider.html))

___
[Inhaltsverzeichnis](https://openwebcc.github.io/cookbook/index)
