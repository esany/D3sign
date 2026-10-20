# Figma-eigenes MCP: Fähigkeiten, Aktionen und Grenzen

Status: Entwurf

Dieses Dokument beschreibt das Figma-eigene Plugin/MCP
`figma@openai-curated-remote`. Es ist die Quelle für link- oder filebezogenen
Figma-Kontext und für die dort unterstützten Figma-Workflows. Die konkreten
MCP-Namen können je nach Client anders dargestellt werden; die Fähigkeiten
bleiben dieselben.

## Fähigkeitsrepertoire

| Gestalterische Aufgabe | Programmatische Fähigkeit / Skill | Technischer Output | Typischer Use Case |
|---|---|---|---|
| Datei, Seite oder Node verstehen | `figma_get_design_context`, bei großen Antworten `figma_get_metadata` | strukturierter Node-/Layout-/Komponenten-Kontext; Metadatenkarte | einen Screen vor einer Umsetzung oder einem Review nachvollziehen |
| visuelle Referenz abrufen | `figma_get_screenshot` | Screenshot des angeforderten Nodes | Layout, Hierarchie und visuelle Abweichungen gemeinsam prüfen |
| Assets übernehmen | `figma_download_assets` | exportierter Node und Original-Asset-Quellen | Bilder/SVGs für eine Implementierung korrekt wiederverwenden |
| Bibliotheken und Tokens finden | `figma_get_libraries`, `figma_search_design_system` | abonnierte/verfügbare Libraries sowie passende Komponenten, Variablen und Styles | bestehende Bausteine vor einer Neuerstellung finden |
| Variablen-Definitionen prüfen | `figma_get_variable_defs` | Variable-Definitionen und Referenzen | Token-Mapping für Code oder Library-Review |
| Screen in Code übersetzen | `figma-design-to-code` / `figma-implement-design` plus Kontext-/Screenshot-Funktionen | Code-Entwurf als Repräsentation des Designs, nicht automatisch projektfertiger Code | Figma-Frame als React/Web- oder andere Zielimplementierung umsetzen |
| Code-Implementierung abgleichen | Design-to-Code-Workflow plus Screenshot/Projektprüfung | visuelle und strukturelle Abweichungsliste | vor Abschluss eines Figma-zu-Code-Tasks |
| Code Connect herstellen | `figma_get_context_for_code_connect`, `figma_get_code_connect_suggestions`, `figma_add_code_connect_map`, `figma_send_code_connect_mappings` | Mapping zwischen Figma-Node und realer Code-Komponente | wiederverwendbare Komponenten im Dev Mode auffindbar machen |
| neue Figma-Datei erzeugen | `figma-create-new-file` plus `figma_create_new_file` | neue leere Datei, File-Key und URL | separaten Pilot oder neue Arbeitsgrundlage anlegen |
| Figma-Inhalte schreiben/ändern | `figma-use` plus `figma_use_figma` | native Frames, Komponenten, Variablen, Styles, Text, Layouts oder Design-System-Inhalte | einen freigegebenen Pilot in der Arbeitsfläche erzeugen oder synchronisieren |
| bestehendes Objekt dateiübergreifend lokal kopieren | **keine belegte MCP-Funktion in dieser Sitzung** | – | native Figma-Canvas-Aktion: Component Set in Quelle kopieren und in Ziel-Datei einfügen |
| Library-/Token-Struktur aus Code ableiten | `figma-generate-library` | editierbare Library-/Token-Grundlage | vorhandene Code-Tokens in eine Figma-Systemstruktur überführen |
| Website erstmals nach Figma übertragen | `figma-generate-design` | Capture-Job und editierbare Darstellung in einem bestehenden Figma-File | lokale Web-Route als visuelle Referenz importieren |
| FigJam-Diagramm erzeugen | `figma-generate-diagram` plus `figma_generate_diagram` | editierbares Diagramm in FigJam | Workflow, Entscheidungsbaum oder Systemzusammenhang darstellen |
| FigJam/Slides-Kontext lesen oder bearbeiten | `figma_use_figma`, `figma_get_figjam`, `figma-use-figjam`, `figma-use-slides` | strukturierter oder editierter FigJam-/Slides-Inhalt | Workshop-Board oder Review-Deck bearbeiten |
| Motion untersuchen | `figma_get_motion_context`, `figma-use-motion` | Motion-Kontext und Animationsparameter | Übergänge für Design und Implementierung beschreiben |
| Motion implementieren | `figma-implement-motion` | Produktionsorientierte Animationsumsetzung | Designbewegung in Code übertragen |
| SwiftUI/iOS übersetzen | `figma-swiftui` | SwiftUI-orientiertes Mapping oder Code | iPhone-/iPad-Ansichten implementieren |
| Agenten-/Codebase-Regeln erzeugen | `figma-create-design-system-rules` | projektbezogene Regeldatei nach Codebase-Analyse | Figma-zu-Code-Konventionen im Repository festhalten |

## Was bedeutet „verbindliche Reihenfolge“?

Die Reihenfolge gilt **nur für einen konkreten Figma-zu-Code- oder
Figma-Implementierungsauftrag**. Sie verhindert, dass ein Agent aus einem
Screenshot oder aus Vermutungen direkt Code erzeugt:

1. **Exakten Node-Kontext holen** – Struktur, Größen, Layout, Komponenten und
   relevante Eigenschaften lesen.
2. **Bei zu großer Antwort Metadaten holen** – die Node-Landkarte lesen und nur
   die benötigten Nodes erneut anfordern.
3. **Screenshot desselben Nodes holen** – visuelle Referenz für Hierarchie,
   Proportionen und sichtbare Zustände.
4. **Erst dann Assets und Umsetzung starten** – vorhandene Assets, Tokens und
   Komponenten verwenden.
5. **Zum Schluss validieren** – visueller Vergleich und bei Code zusätzlich
   funktionale Zustände prüfen.

Für reine Beratung, Dokumentationsarbeit, FigJam oder Southleft Design Systems
ist diese Reihenfolge nicht automatisch erforderlich.

Vor speziellen Schreib-/Erzeugungsfunktionen gelten zusätzliche Skill-
Vorbedingungen: `figma-use` vor `use_figma`, `figma-create-new-file` vor
`create_new_file`, `figma-generate-diagram` vor `generate_diagram` und
`figma-design-to-code` vor dem entsprechenden Design-to-Code-Kontext.

## Was dieses MCP nicht automatisch liefert

Gestalter:innen sollten folgende Fehlinterpretationen vermeiden:

- **Kontext ist keine Bedeutung:** Der MCP kann Struktur und Eigenschaften
  liefern, entscheidet aber nicht, was eine Information fachlich bedeutet.
- **Screenshot ist kein Qualitätsbeweis:** Er zeigt den sichtbaren Zustand, sagt
  aber nicht automatisch, ob Workflow, Accessibility oder Interaktion sinnvoll
  sind.
- **Node-Struktur ist keine Dokumentationsqualität:** Vorhandene Frames,
  Textanker oder Tabellen belegen nur, dass Objekte existieren. Eine
  Figma-Komponentendokumentation braucht zusätzlich visuelle Lesbarkeit,
  Informationshierarchie und menschliche Abnahme.
- **Generierter Code ist kein Projektcode:** Der Output muss an Architektur,
  Komponenten, State, Routing, Datenzugriff und Tests des Projekts angepasst
  werden.
- **Gefundene Komponenten sind nicht automatisch passend:** Suche liefert
  Kandidaten; Nutzung und Semantik müssen geprüft werden.
- **Tokens sind keine vollständige Design-Sprache:** Variablenwerte erklären
  nicht automatisch Rollen, Zustände oder fachliche Regeln.
- **Assets sind keine Lizenzprüfung:** Der MCP liefert Quellen/Exports, aber
  keine rechtliche Freigabe oder Markenentscheidung.
- **Write-Fähigkeit ist keine Freigabe:** Vor Änderungen müssen Zielseite,
  Umfang, bestehende Library und Rückfallebene geklärt sein.
- **Schreiben ist kein Datei-Transfer:** `use_figma` bearbeitet oder erzeugt
  Inhalte für einen adressierten `fileKey`. Im hier geprüften
  Funktionsumfang gibt es keine belegte native Zwischenablage- oder
  Node-Transfer-Funktion zwischen zwei bestehenden Dateien. Eine
  Rekonstruktion, ein Asset-Upload oder eine Library-Instanz ist kein Ersatz
  für eine lokale Kopie einer Main-Komponente.
- **Code Connect ist kein automatisches Mapping:** Node, Code-Quelle und
  Komponentengrenzen müssen eindeutig sein.
- **Figma ersetzt keine Nutzerprüfung:** Gestalterische, fachliche und
  inklusive Qualität braucht menschliche Review und gegebenenfalls Tests.
