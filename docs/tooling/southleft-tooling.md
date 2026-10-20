# Southleft: Design Systems MCP und Figma Console MCP

Status: Entwurf

Southleft besteht hier aus zwei technisch und methodisch verschiedenen
Werkzeugen. Beide sind nicht das Figma-eigene MCP.

## A. Southleft Design Systems MCP

Skill: `design-systems-assistant`  
Server/Toolgruppe: `design_systems` bzw. `design_systems_mcp`

### Evidenzstatus und Einsatzgrenze

Repository-Anspruch, konfigurierte Verbindung und tatsächlich gelieferte
Antwortqualität sind getrennte Befunde. Das MCP darf nur als externe
Evidenzquelle gelten, wenn eine konkrete Abfrage fachlich passende,
quellenzuordenbare Treffer liefert. Eine erreichbare Toolfunktion, ein
Kategorienamen oder eine Repository-Behauptung belegen den zugänglichen Korpus
nicht.

Der öffentliche Endpunkt lieferte im Test vom 2026-07-28 bei WCAG-, DTCG- und
Komponentenabfragen ausschließlich einen unpassenden Sample-Button-Eintrag;
die Chat-Oberfläche brach auch bei einer Grundfrage mit einem Cloudflare-
Worker-Ressourcenfehler ab. Bis ein begrenzter Wiederverfügbarkeitstest
bestandene, passende Treffer nachweist, ist das MCP nicht als tragende
Evidenzquelle einsetzbar. Der Test und seine Statusfortschreibung stehen im
[Evaluation Log](../governance/evaluation-log.md).

### Programmatisch unterstützte Funktionen

| Gestalterische Aufgabe | Programmatische Funktion | Technischer Output | Typischer Use Case |
|---|---|---|---|
| Design-System-Wissen suchen | `search_design_knowledge` | Treffer aus der Southleft-Wissensbasis, filterbar nach Kategorie/Tags | vor einer Entscheidung zu Tokens, Komponenten oder Governance recherchieren |
| Detailpassagen suchen | `search_chunks` | relevante Textabschnitte für eine konkrete Frage | eine Empfehlung mit genauer Begründung vorbereiten |
| Themenbereich durchsuchen | `browse_by_category` | Einträge aus `figma`, `tokens`, `components`, `documentation`, `workflow`, `governance`, `accessibility`, `tools`, `case-studies` oder `foundations` | Überblick über ein Fachgebiet gewinnen |
| Wissensbasis strukturieren | `get_all_tags` | verfügbare Tags | Suchraum und Begriffe für weitere Recherche klären |
| Komponenten beraten | MCP-Wissensabfrage zu Anatomy, States, Variants und Interaction Patterns | Empfehlung, Prüffragen, Alternativen | ein Komponentenmodell oder Varianten-Set beurteilen |
| Tokens beraten | MCP-Wissensabfrage zu Naming, Theming und Governance | Benennungs-/Governance-Empfehlung | Tokenstruktur oder semantische Rollen entwickeln |
| Accessibility beraten | MCP-Wissensabfrage zu Accessibility Patterns | Prüfkriterien und Hinweise | Komponente oder Workflow auf Zugänglichkeit prüfen |
| Dokumentation beraten | MCP-Wissensabfrage zu Documentation Patterns | Struktur- und Inhaltsvorschläge | Dokumentationsseite oder Contribution-Prozess entwerfen |

### Was dieses MCP ist – und was nicht

Das Design Systems MCP ist programmatisch ein **Recherche- und
Beratungsinterface** zu einer Wissensbasis. Es kann suchen, kategorisieren und
Empfehlungen begründen. Es schreibt nicht automatisch in eine konkrete Figma-
Datei und kennt nicht automatisch deren aktuelle Nodes, Auswahl oder lokalen
Teamkontext.

Es liefert daher:

- externe bzw. allgemeine Design-System-Orientierung
- Begriffe, Muster, Prüffragen und Alternativen
- Hinweise für Tokens, Komponenten, Accessibility und Governance

Es liefert nicht automatisch:

- ein verbindliches Projektprinzip
- eine Analyse eurer konkreten Figma-Datei
- eine fertige Figma-Komponente
- eine Freigabe für eure Marke, Domäne oder Nutzergruppe
- empirische Evidenz aus eurem Projekt

## B. Southleft Figma Console MCP

Toolgruppe: `figma_console_mcp`  
Voraussetzung: verbundene Figma-Console-/Desktop-Bridge, geöffnete bzw.
zugängliche Datei und ein aktueller Bridge-Zustand.

### Was „lokale/interaktive Figma-Aktion“ bedeutet

Dieses MCP arbeitet über die verbundene Figma-Session. Es kann die aktuelle
Datei, Auswahl und Bridge-Umgebung inspizieren und über spezialisierte Tools
oder `figma_execute` Änderungen an nativen Figma-Inhalten ausführen. Es ist
damit näher an einer interaktiven Figma-Console als an einer reinen
linkbasierten Kontextabfrage.

### Arbeitet es über Selektion?

**Ja, Selektion ist ein wichtiger Einstieg, aber nicht der einzige.**

- `figma_get_selection` liest die aktuell ausgewählten Nodes.
- Viele Aufgaben können dadurch direkt auf dem markierten Bereich arbeiten.
- Zusätzlich sind explizite Node-IDs, Datei-/Seitenkontext, offene Dateien,
  fokussierte Slides und Suchfunktionen möglich.
- Für reproduzierbare Team-Workflows sind explizite IDs und eine dokumentierte
  Zielseite robuster als eine nur visuell gesetzte Auswahl.

### Programmatisch unterstützte Funktionen

| Gestalterische Aufgabe | Programmatische Funktion | Technischer Output | Typischer Use Case |
|---|---|---|---|
| aktuelle Auswahl inspizieren | `figma_get_selection` | ausgewählte Nodes und Eigenschaften | markierte Komponente schnell prüfen oder gezielt bearbeiten |
| offene Dateien/Status prüfen | `figma_list_open_files`, `figma_get_status`, `figma_reconnect` | Session-, Datei- und Bridge-Status | vor einer schreibenden Aktion sicherstellen, dass die richtige Datei verbunden ist |
| Komponenten suchen | `figma_search_components`, `figma_get_component`, `figma_get_component_details` | lokale Komponenten und Eigenschaften | vorhandene Komponente instanziieren oder analysieren |
| Library-Komponenten/Variablen lesen | `figma_get_library_components`, `figma_get_library_variables`, `figma_get_library_component_by_key` | Bibliotheksinhalte und Schlüssel | lokale Library vor Duplikation oder Migration prüfen |
| Design-System auditieren | `figma_audit_design_system`, `figma_get_design_system_summary`, `figma_get_design_system_kit` | Audit-/Zusammenfassungsbefund | Systemzustand, Abdeckung und auffällige Lücken erfassen |
| Komponente analysieren | `figma_analyze_component_set`, `figma_get_component_for_development_deep` | Varianten-, Property- und Entwicklungsdetails | Component Set oder Übergabe an Entwicklung verstehen |
| Accessibility prüfen | `figma_audit_component_accessibility`, `figma_scan_code_accessibility` | Accessibility-Befund | Kontrast, Semantik oder implementierte Accessibility gezielt prüfen |
| visuell prüfen | `figma_take_screenshot`, `figma_capture_screenshot`, `figma_get_component_image` | Screenshot/Komponentenbild | Abstände, Ausrichtung, Proportionen, Überläufe und visuelle Balance prüfen |
| Design-Parität prüfen | `figma_check_design_parity` | Vergleichsbefund | Figma-Entwurf gegen Implementierung oder Referenz abgleichen |
| Figma-Code ausführen | `figma_execute` | JavaScript-Ausführung über Figma Plugin API | gezielte native Änderungen oder Abfragen, wenn kein Spezialtool genügt |
| Nodes erzeugen/ändern | `figma_create_child`, `figma_clone_node`, `figma_move_node`, `figma_resize_node`, `figma_rename_node`, `figma_delete_node` | native Node-Änderungen | Pilotbereich strukturieren, umbenennen oder aufräumen |
| Komponenten instanziieren | `figma_instantiate_component`, Property-/Slot-Funktionen | Instanz und Property-/Slot-Änderungen | bestehende Library-Komponente in einem Pilot verwenden |
| Variablen/Tokens lesen | `figma_get_variables`, `figma_browse_tokens`, `figma_get_token_values` | Variablen, Modi und Werte | Tokenstruktur untersuchen oder dokumentieren |
| Variablen/Tokens schreiben | `figma_setup_design_tokens`, Batch-/Update-Funktionen | Collections, Modi und Variablen | Tokenpilot atomar aufbauen oder viele Werte ändern |
| Kommentare/Annotationen bearbeiten | `figma_get_comments`, `figma_post_comment`, `figma_get_annotations`, `figma_set_annotations` | Kommentare und Annotationen | Review- und Übergabehinweise direkt am Design festhalten |
| Dokumentation/Changelog erzeugen | `figma_generate_component_doc`, `figma_generate_changelog` | Figma-nahe Dokumentation oder Änderungsübersicht | Komponentenpflege und Release-Kommunikation unterstützen |
| Versionen vergleichen | `figma_get_file_versions`, `figma_diff_versions`, `figma_get_changes_since_version` | Versions-/Änderungsbefund | kontrollierte Migration oder Review vorbereiten |
| FigJam/Slides direkt bearbeiten | `figjam_*`, Slide-Tools wie `figma_create_slide`, `figma_set_slide_transition` | native Board-/Slide-Änderungen | Workshop- oder Präsentationsartefakte über die Bridge pflegen |

### Wofür ist „visueller Zustand prüfen“?

Das ist keine abstrakte Qualitätsfloskel. Der Screenshot dient je nach Auftrag
für:

- **Gestalter:innen:** Hierarchie, Rhythmus, Ausrichtung, Proportionen,
  Typografie, Überläufe und visuelle Balance beurteilen.
- **Agenten:** Nach einer Änderung prüfen, ob die erzeugten Nodes tatsächlich
  dort liegen, die erwarteten Größen haben und nicht „floating“ oder falsch
  verschachtelt sind.
- **Entwicklung/Übergabe:** Figma und implementierte Darstellung vergleichen.
- **Accessibility-Review:** sichtbare Kontraste und Zustände als Hinweis prüfen;
  der Screenshot ersetzt keinen vollständigen Accessibility-Test.

Die Console-Toolbeschreibung verlangt nach visuellen Änderungen typischerweise
die Folge **Create → Screenshot → Analyse → Iteration → Verify**. Bei reinen
Lese- oder Beratungsaufgaben ist sie nicht notwendig.

### Was „Figma-Code“ bedeutet

In diesem Kontext ist damit meist **JavaScript für die Figma Plugin API** in
`figma_execute` gemeint. Das ist kein automatisch erzeugter Produktionscode
für eure Anwendung. Es ist ein Ausführungsmittel, mit dem Figma-Nodes,
Variablen, Styles oder Layouts gelesen und geändert werden.

### Grenzen und Fehlinterpretationen

- Die Auswahl kann veraltet oder falsch sein; vor jeder relevanten Aktion
  Auswahl/Datei/Node prüfen.
- Eine Bridge-Verbindung bedeutet nicht automatisch, dass die richtige Datei
  oder Seite aktiv ist.
- Ein Spezialtool ist sicherer als beliebiges `figma_execute`, wenn es für die
  Aufgabe existiert.
- Schreibtools können reale Figma-Inhalte verändern; Ziel, Umfang und
  Rückfallebene vorab benennen.
- Screenshots zeigen den aktuellen visuellen Zustand, aber keine vollständige
  Semantik, Nutzerwirksamkeit oder Accessibility.
- Audit- und Lint-Befunde sind Hinweise, keine automatische fachliche Freigabe.
- Batch-Funktionen sind effizient, erhöhen aber den Änderungsumfang; zuerst
  Variablen-/Node-Menge und Zielbereich begrenzen.
- Southleft Console ist nicht automatisch mit dem Figma-eigenen MCP, dem
  Design Systems MCP oder einer Figma-Bibliotheksquelle synchron.
