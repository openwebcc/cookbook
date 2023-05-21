# Layer Control für alle Hintergrundlayer der basemap.at

## Zutaten

- WMTS Hintergrundlayer der <https://basemap.at> über das Leaflet Provider Plugin
- Template: [control_layers_baselayers.html](https://github.com/openwebcc/cookbook/blob/main/templates/control_layers_baselayers.html) mit der Grundkarte aus dem Rezept *[Leaflet Provider Plugin für Hintergrundlayer](https://openwebcc.github.io/cookbook/plugin_leaflet_provider)*

## Ablauf

1. das Template [control_layers_baselayers.html](https://github.com/openwebcc/cookbook/blob/main/templates/control_layers_baselayers.html) kopieren und dort weiterarbeiten 🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/2fe0115b241ec1e8643bbc8d849e59499acdb560)

2. Einbau der Hintergrundlayer

    - den bestehenden `L.tileLayer.provider` Aufruf durch einen Aufruf von `L.control.layers` mit sieben `L.tileLayer.provider` Aufrufen für die <https://basemap.at> ersetzen. Die Layer control wird in einer Variablen `layerControl` gespeichert.

        ```javascript
        let layerControl = L.control.layers({
            "BasemapAT Grau": L.tileLayer.provider("BasemapAT.grau").addTo(map),
            "BasemapAT Standard": L.tileLayer.provider("BasemapAT.basemap"),
            "BasemapAT High-DPI": L.tileLayer.provider("BasemapAT.highdpi"),
            "BasemapAT Gelände": L.tileLayer.provider("BasemapAT.terrain"),
            "BasemapAT Oberfläche": L.tileLayer.provider("BasemapAT.surface"),
            "BasemapAT Orthofoto": L.tileLayer.provider("BasemapAT.orthofoto"),
            "BasemapAT Beschriftung": L.tileLayer.provider("BasemapAT.overlay")
        }).addTo(map);
        ```

        🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/f6613e7936374fde509be3dd8198ddf060d990df)

        > siehe Dokumentation [L.control.layers()](https://leafletjs.com/reference.html#control-layers)

3. Kombination des Orthofotos mit der Beschriftung

    - die beiden Tilelayer für das Orthofoto und die Beschriftung können mit einer `L.layerGroup` übereinandergelegt werden

        ```javascript
            "BasemapAT Orthofoto mit Beschriftung": L.layerGroup([
                L.tileLayer.provider("BasemapAT.orthofoto"),
                L.tileLayer.provider("BasemapAT.overlay")
            ])
        ```

        🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/0d41baa35c8772480758d169acbe8d5eb080cbe8)

        > siehe Dokumentation [L.layerGroup()](https://leafletjs.com/reference.html#layergroup)

4. Die Layercontrol beim Laden ausklappen

    ```javascript
    layerControl.expand();
    ```

    🔗[COMMIT](https://github.com/openwebcc/cookbook/commit/08a25d832ebd5ca1254b694bc59238171551870a)

    > siehe Dokumentation [.expand()](https://leafletjs.com/reference.html#control-layers-expand)

## Ergebnis

[Layer Control für Hintergrundlayer der basemap.at Beispiel](https://openwebcc.github.io/cookbook/examples/control_layers_baselayers.html) ([Source](https://github.com/openwebcc/cookbook/blob/main/examples/control_layers_baselayers.html))

___
[Inhaltsverzeichnis](https://openwebcc.github.io/cookbook/index)
