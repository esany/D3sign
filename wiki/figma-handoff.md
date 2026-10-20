# Qualität übergeben und abnehmen

## Welche Frage beantwortet diese Seite?

„Welche Information braucht Development, um die beabsichtigte Erfahrung
verlässlich umzusetzen und gemeinsam abnehmen zu können?“ Eine Übergabe ist
kein Datenexport, sondern eine prüfbare Vereinbarung über den relevanten
Kontext.

## Kleinste ausreichende Übergabe

Eine Übergabe enthält nur, was für die Umsetzung und Prüfung benötigt wird:

- Referenz auf den geprüften Figma-Kontext und seinen tatsächlichen Umfang;
- Zweck sowie erwartetes Verhalten, relevante Varianten und Zustände;
- Anforderungen an Zugänglichkeit oder Responsive-Verhalten, sofern sie für
  die Frage bestimmt wurden;
- offene Bedeutungs- oder Umsetzungsfragen;
- eine gemeinsame, prüfbare Abnahme.

Figma trägt visuelle und designnahe Struktur. Code trägt die ausführbare
Umsetzung. `docs/` enthält verbindliche Regeln und Entscheidungen. Die Wiki
ordnet diese Orte ein, statt ihren Inhalt zu kopieren.

## Gemeinsame Verantwortung

Design erläutert Absicht und priorisiert offene Fragen. Development prüft
Machbarkeit, technische Folgen und fehlende Informationen. Review prüft, ob
Quelle, Evidenz, Grenze und Abnahme sichtbar sind. Der Agent bereitet den
bestätigten Kontext vor, ersetzt aber keine dieser fachlichen Prüfungen.

## Besondere Grenze: Übergaben zwischen Dateien

„Kopieren“, „verknüpfen“, „verschieben“ und „rekonstruieren“ erhalten nicht
dieselben Eigenschaften. Für eine lokale Kopie einer Main-Komponente mit
Varianten und Properties ist im geprüften Scope die native Figma-Übernahme
erforderlich; ein Import oder Nachbau ist kein stillschweigender Ersatz. Die
Funktionsgrenze ist in der
[Figma-MCP-Tooling-Dokumentation](../docs/tooling/figma-mcp-tooling.md)
dokumentiert.

**Nächster Schritt:** Nach der gemeinsamen Abnahme nur wiederkehrende oder
folgenreiche Unklarheiten als möglichen Befund in [System entwickeln und aus
der Praxis lernen](system-development-and-learning.md) überführen.
