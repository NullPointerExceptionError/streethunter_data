# StreetHunter – Stadtdaten

Dieses Repository stellt die öffentlichen Stadt-Referenzdaten für StreetHunter bereit. `data/registry.json` enthält den Katalog und verweist auf versionierte SQLite-Dateien in GitHub Releases. Ältere Datenbanken liegen außerdem unter `data/packages/`.

## Herkunft und Lizenz

© OpenStreetMap contributors. Die Stadt-Referenzdatenbanken sind aus OpenStreetMap-Daten abgeleitete Datenbanken und werden unter der Open Database License 1.0 (ODbL-1.0) bereitgestellt. Die Erzeugung ergänzt unter anderem H3-Zellen, Straßenklassifikation und manuell überprüfte Korrekturen. Siehe [LICENSE-DATA.md](LICENSE-DATA.md).

- OpenStreetMap und Quellenhinweise: https://www.openstreetmap.org/copyright
- Vollständige Datenbanklizenz: https://opendatacommons.org/licenses/odbl/1-0/
- Generator: https://github.com/NullPointerExceptionError/streethunter_data-db-generator

Diese Hinweise gelten für die OSM-basierten `.db`-Dateien in diesem Repository und den zugehörigen StreetHunter-Datenbank-Releases. Die Dateien werden in einer offenen, mit SQLite lesbaren Form bereitgestellt. Veröffentlichungsmanifeste (`publication.json`), soweit vorhanden, beschreiben zusätzlich Erzeugungsstand, Eingaben und Prüfsummen. Fehlende historische Angaben dürfen nicht nachträglich erfunden werden.

## Nutzung

Die Lizenz erlaubt auch kommerzielle Nutzung, verlangt aber insbesondere Attribution und bei Weitergabe abgeleiteter Datenbanken die Einhaltung ihrer Share-Alike-Bedingungen. Lizenz und Hinweise müssen mit der Weitergabe zugänglich bleiben. Die Daten können Fehler enthalten und ersetzen keine verlässliche Auskunft über Zugänglichkeit, Verkehrsregeln oder Betretungsrechte.

Die Stadtdaten sind keine Aufzeichnungen von Spielern. Private Besuchszellen, Besuchszeiten und GPS-Verläufe gehören nicht in dieses öffentliche Repository. Die Datenlizenz verlangt nicht die Veröffentlichung privater Spielerdaten oder des gesamten Appcodes.

Es werden hier keine vollständigen Offline-Hintergrundkarten angeboten. Eine Stadt-Referenzdatenbank ist kein Offline-Tile-Archiv.
