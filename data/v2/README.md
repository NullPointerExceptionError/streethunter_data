# Verwaltungsdaten für StreetHunter

`registry.json` ist der Einstieg für den neuen Datenvertrag. In `dev_AI`
bleibt die Länderliste bis zur Bereitstellung geprüfter Daten leer. Jede
Länderkennung verweist später über `manifest_url` auf ein Länder-Manifest
im selben `data/v2/`-Verzeichnis. `manifest_sha256` enthält den SHA-256
der veröffentlichten Manifest-Datei. Beide Felder stehen zusammen in
`countries.<Länderkennung>`.
Die bestehende Stadt-Registry bedient weiterhin bereits installierte Apps.

## Katalog und Download

Das Länder-Manifest des Generators enthält `country`, `schema_version`,
`catalog_version`, `boundaries` und `endpoints`. `boundaries` enthält die
eigenständige Grenzdateiversion. Jeder Endpunkt hat seine stabile `id`,
`reference_count`, `street_count` und einen eigenständig versionierten
`file`-Deskriptor. IDs bestehen aus Länderkennung, Bindestrich und 32
kleingeschriebenen Hexadezimalzeichen. `identities` und `lineage` enthalten
die Historie für den Wiederaufbau und für Gebietsänderungen.

Ein Dateideskriptor enthält die ganzzahlige `version`, `size_bytes`,
`sha256` und `assets`. Jedes Asset hat seine eigene Größe, SHA-256-Summe
und HTTPS-URL im GitHub-Release dieses Repositories. Mehrteilige Dateien
werden in Array-Reihenfolge zusammengesetzt. Die App prüft sowohl die Teile
als auch die zusammengesetzte Datei. Ein aktualisiertes Bundle ändert
weder die Version noch die URL eines unveränderten Endpunkts.

Das Manifest wird zusammen mit den release-spezifischen Assets freigegeben.
Die Registry soll erst auf eine neue Version zeigen, nachdem sämtliche
referenzierten Dateien erreichbar und geprüft sind. Ein lokaler
`release-plan.json` des Generators gruppiert maximal 1.000 Assets pro
Release und kann ohne Veröffentlichung geprüft werden.

## SQLite-Dateien

| Datei | Tabellen | Bedeutung |
| --- | --- | --- |
| `<Ländercode>_boundaries.mbtiles` | `metadata`, `tiles`, `area`, `endpoint_bbox`, `lineage` | MVT-Grenzen in MBTiles mit TMS-Zeilennummerierung, Eltern-IDs, Labelkoordinaten, H3-Zellzahlen, räumlicher Index für Endpunkt-Polygone und versionierte Identitätsübergänge |
| `<Ländercode>_<Name>_<ID>.sqlite` | `metadata`, `reference`, `street_segment`, `street_cell` | Ein Endpunkt mit sämtlichen R12-Referenzzellen, Straßensegmenten und ihrer Zuordnung |

Beide Dateien verwenden `PRAGMA user_version=1`. `area.reference_count`
und `street_count` sind nur für Endpunkte gesetzt. `reference.h3_index`
ist kleingeschriebener H3-Text. `is_street` ist 0 oder 1. Fortschritt nutzt
alle Referenzzellen als Nenner. Für Elterngebiete werden Zähler und Nenner
der darunterliegenden Endpunkte jeweils summiert.

Endpunktgrenzen und Straßengeometrien basieren auf OpenStreetMap.
© OpenStreetMap contributors. Die Daten unterliegen der ODbL 1.0.
Siehe [Datenlizenz](../../LICENSE-DATA.md).
