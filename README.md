# StreetHunter – Gebietsdaten

Dieses Repository stellt aus OpenStreetMap abgeleitete Spieldaten bereit.
Der [Gebietskatalog](data/v2/README.md) verweist auf versionierte Grenzdateien
(`.mbtiles`) und Gebietsdateien (`.sqlite`) in
[GitHub Releases](https://github.com/NullPointerExceptionError/streethunter_data/releases).
Die frühere Stadt-Registry `data/registry.json` und ältere `.db`-Pakete unter
`data/packages/` stehen weiterhin für ältere App-Versionen bereit.

## Herkunft und Lizenz

© OpenStreetMap contributors. Die Grenz- und Gebietsdateien und die älteren
Stadtpakete stehen unter der **Open Database License 1.0 (ODbL 1.0)**.
Siehe [Lizenz der StreetHunter-Daten](LICENSE-DATA.md),
[OpenStreetMap-Herkunft und Attribution](https://www.openstreetmap.org/copyright)
und den [vollständigen Lizenztext](https://opendatacommons.org/licenses/odbl/1-0/).

StreetHunter leitet aus den OSM-Daten Verwaltungshierarchien und
H3-Referenzzellen ab, klassifiziert Straßen und berücksichtigt geprüfte
Korrekturen. Veröffentlichungsmanifeste dokumentieren, soweit vorhanden,
den Erzeugungsstand, die Eingaben und die Prüfsummen. Weitere technische Details stehen im [Generator-Repository](https://github.com/NullPointerExceptionError/streethunter_data-db-generator).

## Nutzung

Die Lizenz erlaubt auch kommerzielle Nutzung. Ihre Bedingungen zur Attribution
und zur Weitergabe abgeleiteter Datenbanken gelten weiterhin. Die Daten können
Fehler enthalten und ersetzen keine verlässliche Auskunft über Zugänglichkeit,
Verkehrsregeln oder Betretungsrechte.

Die Dateien enthalten keine Spielstände, besuchten Orte oder GPS-Verläufe.
Sie sind Spieldaten und keine Offline-Hintergrundkarten.
