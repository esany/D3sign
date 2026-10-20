# Figma- und Design-System-Tooling

Status: Entwurf

Dieses Cheatsheet hilft Menschen und Agenten bei der Auswahl des passenden
Werkzeugs. Nicht alle Skills werden gleichzeitig verwendet. Immer den kleinsten
Workflow wählen, der die Aufgabe vollständig abdeckt.

Für die Formulierung des Auftrags siehe den [Prompting Guide](../operations/prompting-guide.md).
Die technischen Repertoires sind getrennt dokumentiert:

- [Figma-eigenes MCP](figma-mcp-tooling.md)
- [Southleft-Tooling](southleft-tooling.md)

## Schnellentscheidung

| Aufgabe | Primäres Werkzeug | Ergebnis |
|---|---|---|
| Eine konkrete Figma-Datei, Seite oder Node verstehen | Figma-eigenes MCP | Strukturierter Kontext, Metadaten, Screenshots, Assets |
| Einen konkreten Figma-Screen als Code umsetzen | Figma `figma-design-to-code` / `figma-implement-design` | Projektkonformer UI-Code |
| Bestehende Figma-Komponente mit Code verbinden | Figma `figma-code-connect` / `figma-code-connect-components` | Code-Connect-Zuordnung |
| Neue Figma-Datei anlegen | Figma `figma-create-new-file` | Neue leere Figma-Datei |
| Figma-Komponentenbibliothek oder Tokenstruktur erzeugen | Figma `figma-generate-library` | Editierbare Library-/Token-Grundlage |
| Code oder eine Website nach Figma übertragen | Figma `figma-generate-design` | Editierbare Figma-Darstellung |
| FigJam-Diagramm erstellen | Figma `figma-generate-diagram` | FigJam-Diagramm |
| FigJam-Inhalt bearbeiten | Figma `figma-use-figjam` | Bearbeiteter FigJam-Inhalt |
| Figma-Slides bearbeiten | Figma `figma-use-slides` | Bearbeitete Slides |
| Motion oder Animation aus einem Design ableiten | Figma `figma-implement-motion` / `figma-use-motion` | Bewegungs-/Animationsumsetzung |
| SwiftUI/iOS-Umsetzung | Figma `figma-swiftui` | SwiftUI-orientierte Umsetzung |
| Allgemeine Design-System-, Token- oder Accessibility-Beratung mit passenden, quellenzuordenbaren Treffern | Southleft Design Systems MCP | Externe Empfehlung oder Review; bei fehlenden Treffern Grenze ausweisen und auf Primärquellen zurückfallen |
| Figma-Datei über Southlefts Console-/Bridge-Ansatz inspizieren oder bearbeiten | Southleft Figma Console MCP | Direkte Figma-Inspektion oder Canvas-Aktion über die Console/Bridge |
| Projektbezogene Agenten-/Codebase-Regeln erstellen | Figma `figma-create-design-system-rules` | `AGENTS.md`, `CLAUDE.md` oder Cursor-Regeln |

## Ausführungsregeln

- Bei konkreter Figma-Implementierung in Code: die Reihenfolge aus [Figma MCP
  Tooling](figma-mcp-tooling.md) einhalten: exakten Design-Kontext abrufen,
  Screenshot desselben Nodes abrufen, dann Assets/Code erzeugen und validieren.
- Vor `use_figma` immer den Skill `figma-use` laden.
- Vor `create_new_file` immer `figma-create-new-file` laden.
- Vor `generate_diagram` immer `figma-generate-diagram` laden.
- Für Design-to-Code zuerst `figma-design-to-code` oder
  `figma-implement-design` laden; danach die dort verlangte MCP-Reihenfolge
  einhalten.
- Keine Figma-Aktion mit einem Beratungs-Tool simulieren.
- Ein externes Wissens-MCP ist nur dann Evidenzquelle, wenn die konkrete
  Abfrage fachlich passende und quellenzuordenbare Treffer liefert. Eine
  erreichbare Verbindung oder ein Toolversprechen genügt nicht.
- Bei `START CHAT` nur das für die konkrete Aufgabe benötigte Werkzeug auf
  Verfügbarkeit, tatsächlichen Scope, Zugriff oder Laufzeit und belastbare
  Alternative prüfen; keine pauschale Toolinventur ausführen.

## Quellenbasierter Figma-Entscheidungsbaum

Dieser Entscheidungsbaum operationalisiert den Workflow
[KI-gestützte Figma-Arbeit](../operations/workflows.md#ki-gestutzte-figma-arbeit).
Er ist die Figma-spezifische Ausprägung der
[Arbeitsprinzipien für evidenzbasierte Toolnutzung](../operations/workflows.md#arbeitsprinzipien-fur-evidenzbasierte-toolnutzung):
Vor jedem Toolaufruf müssen fachliche Frage, minimal erforderliche Quelle und
möglicher Evidenzstatus geklärt sein. Ein fehlgeschlagener oder nicht
getesteter Abruf wird nicht als allgemeine Produktgrenze von Figma oder MCP
ausgegeben.

### Statussprache für Toolbefunde

| Status | Bedeutung |
|---|---|
| `sichtbar` | direkt im geprüften Tooloutput enthalten |
| `abgeleitet` | aus sichtbaren Daten plausibel geschlossen, aber nicht direkt belegt |
| `getestet` | in diesem Setup erfolgreich ausgeführt |
| `fehlgeschlagen` | in diesem Setup ausgeführt, aber mit Fehler oder ohne verwertbares Ergebnis |
| `nicht getestet` | nicht aufgerufen oder nicht im bestätigten Scope |
| `nicht nachgewiesen` | mit den erfolgreich ausgeführten Funktionen nicht belegbar |
| `blockiert` | durch Plan, Seat, Freigabe, Zugriff, Bridge oder Datenklasse verhindert |

### Erstentscheidung nach Quelle

| Vorliegende Quelle | Erste passende Aktion | Typischer Output | Grenze oder Stopppunkt |
|---|---|---|---|
| Projektlink oder Projekt-ID | nur Datei anlegen oder Projektort bestimmen | Projekt-/Ablagebezug | keine Designanalyse; für Inhalte Datei- oder Node-Link anfordern |
| File-Link oder FileKey ohne Node | `get_libraries`, `search_design_system` oder filebezogene Code-Connect-/Library-Funktion, sofern verfügbar | abonnierte Libraries, verfügbare Libraries, Komponenten-/Variablen-/Style-Kandidaten | keine vollständige Seiten- oder Frameanalyse behaupten; für konkrete Inhalte Node-Link anfordern |
| File- oder Share-Link, Dateiinventar ausdrücklich gefragt | read-only Root-Inventar mit `use_figma` nach `figma-use`, sofern Zugriff und Freigabe vorliegen | im geprüften Setup sichtbare Page-IDs | ein einzelner Metadatenabruf ist keine alleinige Evidenz für eine vollständige Page-Liste; Ursache abweichender Rückgaben nicht raten |
| Share-Link mit Node-ID, Scope nicht ausdrücklich benannt | technische Anker aus Link ableiten; Scope klären | FileKey, Node-ID und Dateityp als verfügbare Adresse | Node-ID nicht als automatische Beschränkung auf diesen Node behandeln; bei unklarer Absicht gezielt nach Datei-, Page- oder Node-Scope fragen |
| Page-, Section-, Frame-, Component- oder Instance-Link mit Node-ID | `get_design_context` und bei visueller Bewertung `get_screenshot` | vom Tool generierte Designkontext-Repräsentation, Node-IDs, sichtbare Struktur, Screenshot | gilt nur für den geprüften Node und seine sichtbare bzw. zurückgegebene Tiefe |
| großer Node oder unklarer Zielbereich | erst Metadaten/Node-Landkarte, falls verfügbar; sonst kleinere Node-Quelle verlangen | Auswahl der relevanten Teilstruktur | keinen Vollbefund aus unvollständigem oder abgeschnittenem Kontext ableiten |
| konkrete Library- oder Wiederverwendungsfrage | `get_libraries`, danach `search_design_system` mit enger Query und bei Bedarf Library-Key | Kandidaten für Komponenten, Variablen und Styles | Suchtreffer sind Kandidaten, keine bestätigte semantische Passung |
| konkrete Token-/Variable-Frage an einem Node | `get_variable_defs` für genau diesen Node | sichtbare Variable-Definitionen oder `{}` | `{}` heißt nicht „keine Tokens in der Datei“, sondern nur kein Nachweis am geprüften Node |
| Asset-, Bild- oder Icon-Frage | `download_assets` für genau diesen Node | Node-Export, Raw Images oder SVG-Assets, soweit vorhanden | Asset-URLs sind temporär; Asset-Abruf beweist keine Lizenz- oder Semantikfreigabe |
| Development-Handoff mit realem Codebezug | Code Connect nur nach Plan-/Seat-/Codebasisprüfung | Mapping- oder Snippet-Kontext | bei Plan-/Seat-Fehler `blockiert`; nicht durch generierte Snippets ersetzen |
| lokale Auswahl, Canvas-Audit oder Batch-Aktion | Southleft Console oder `use_figma`, sofern Bridge bzw. Plugin-API-Zugriff verfügbar und freigegeben ist | Auswahl, lokale Nodes, Audit oder native Canvas-Aktion | Verfügbarkeit zuerst testen; ohne belegten Zugriff nicht als Lesepfad ausgeben |
| allgemeine Design-System- oder Accessibility-Beratung | Southleft Design Systems MCP nur mit passenden, quellenzuordenbaren Treffern; sonst Primärquellen | Prüffragen, Alternativen, Best-Practice-Hinweise | ersetzt keine konkrete Figma-Evidenz und keine Projektentscheidung |

### Funktionswahl nach Aufgabe

| Aufgabe | Funktion zuerst | Benötigte Quelle | Danach nur wenn nötig |
|---|---|---|---|
| Dateiaufbau oder verfügbare Pages verstehen | read-only Root-Inventar mit `use_figma` nach `figma-use`, sofern Dateiübersicht ausdrücklich verlangt und Zugriff freigegeben ist | FileKey; kein zusätzlicher Share-Link bei erfolgreich zurückgegebenen Page-IDs | `get_metadata` für eine ausgewählte Page; Ergebnis nur als im konkreten Setup sichtbares Inventar ausweisen |
| Struktur eines konkreten Artefakts verstehen | `get_design_context` | Node-Link oder FileKey + Node-ID | Screenshot zur visuellen Prüfung; kleinerer Node bei zu großem Kontext |
| visuelle Qualität oder Lesbarkeit prüfen | `get_screenshot` | Node-Link oder FileKey + Node-ID | Design-Kontext, wenn Layer-/Auto-Layout-Ursache geklärt werden muss |
| bestehende Bausteine vor Neubau finden | `get_libraries` → `search_design_system` | FileKey, Suchbegriff, optional Library-Key | konkreten Kandidaten erst mit passender Component-/Node-Quelle prüfen |
| Variablenbindung prüfen | `get_variable_defs` | FileKey + Node-ID | weitere Nodes nur bei konkreter Lücke oder Vergleichsfrage |
| Bilder oder SVGs übernehmen | `download_assets` | FileKey + Node-ID | lokale Sicherung nur bei freigegebenem Umsetzungsauftrag |
| Code aus Figma ableiten | `get_design_context` nach `figma-design-to-code` | exakter Implementierungs-Node | Screenshot, Assets, Projektcode-Prüfung und visuelle Validierung |
| Figma schreiben oder programmatisch inspizieren | `use_figma` nach `figma-use` | FileKey, Zielseite/Node, bestätigter Scope | kleine Schreibschritte, Node-ID-Rückgabe, Screenshot-/Strukturcheck |
| neue Figma-Datei anlegen | `create_new_file` nach `figma-create-new-file` | PlanKey, optional Project-ID, Dateiname | danach `use_figma` für Inhalte |

### Testbefund: Abdeckungsgrad ähnlicher Lesefunktionen

Funktionsname oder grobe Zweckbeschreibung begründen keine Gleichwertigkeit
des Abdeckungsgrads. Im Testfall `Base Template – Figma Pilot` lieferte
`get_metadata(fileKey)` ohne Node nicht dieselbe Page-Liste wie ein
read-only Root-Inventar via `use_figma`. Der Root-Abruf zeigte vier Pages;
die daraus zurückgegebenen Page-IDs waren für Page-Metadaten verwendbar.

Der Befund gilt nur für dieses getestete Setup. Er erklärt weder die Ursache
der Abweichung noch eine allgemeine Grenze von Figma oder des MCP. Bei einer
vollständigen Dateiübersicht wird deshalb eine einzelne Lesefunktion erst nach
einem passenden Vergleich als ausreichend behandelt.

### KI-orientiertes Figma-Inventar

Ein Inventar beschreibt nicht die Datei um ihrer selbst willen. Es macht
Arbeitsobjekte für eine konkrete Folgefrage identifizierbar und trennt dabei
sichtbare Struktur von vermuteter oder bestätigter Systembedeutung.

Inventarisierung ist kein Arbeitsschritt und keine Standardphase. Sie wird nur
ausgelöst, wenn der direkte Arbeitskontext nicht ausreicht, um Arbeitsobjekt
oder Funktion sicher zu bestimmen, oder wenn die Dateiübersicht selbst
ausdrücklich beauftragt ist.

| Ausgangslage | Erste Aktion | Inventar |
|---|---|---|
| konkreter Node oder Bereich plus konkrete Frage | direkten Kontext lesen | nicht erstellen |
| konkrete Page plus konkrete Frage | nur zur Adressierung nötige Metadaten lesen | nicht erstellen |
| Dateiübersicht ausdrücklich beauftragt | begrenztes Datei-/Page-Inventar | erstellen |
| relevantes Arbeitsobjekt ohne Überblick nicht bestimmbar | begrenztes Auswahl- oder Vergleichsinventar | erstellen |
| Scope unklar, Übersicht aber nicht zur Klärung nötig | gezielt rückfragen | nicht erstellen |

| Inventar | KI-Frage | Minimale Felder | Zulässige Ableitung |
|---|---|---|---|
| Strukturinventar | Was ist sichtbar? | Arbeitsobjekt, Name, ID, direkte Bereiche, Komponenten/Instanzen soweit sichtbar, Evidenztyp | technische Landkarte und Auswahl weiterer Quellen |
| Systeminventar | Welche Systembedeutung ist belegt, möglich oder ausgeschlossen? | Arbeitsobjekt-Typ, Library-/Tokenbezug, Systemstatus, Vertragsrelevanz | Kandidaten und offene Fragen, keine automatische Standardübernahme |
| Arbeitsinventar | Was ist der kleinste sinnvolle nächste Schritt? | Dokumentations-, Review- und Änderungsbedarf, Risiko, nächste Aktion | begründete Lesefolge oder menschliche Rückfrage |

Arbeitsobjekt-Typen sind `Page`, `Section`, `Frame`, `Komponente`, `Pattern`,
`Projektausprägung` und `Experiment`. Sie sind keine verpflichtende
Figma-Dateistruktur. `sichtbar in Figma` bedeutet weder
`Basis-Library-Kandidat` noch fachlich bestätigt.

| Evidenztyp | Bedeutung | Keine zulässige Verkürzung |
|---|---|---|
| `E0` | Dateiinventar: sichtbare Pages und technische IDs | keine Aussage über Inhalte oder Bedeutung |
| `E1` | Strukturmetadaten: Page-/Node-Hierarchie und Eigenschaften | keine vollständige visuelle oder semantische Bewertung |
| `E2` | Detailkontext am konkreten Node | keine Aussage über nicht gelesene Bereiche |
| `E3` | Sichtkontext per Screenshot | keine Accessibility-, UX- oder Fachabnahme |
| `E4` | menschlich bestätigte Bedeutung oder Entscheidung | keine technische Vollständigkeitsbehauptung ohne passende Quelle |

Die Evidenztypen sind Kontextarten, keine Qualitätsrangfolge. Welche davon
passt, richtet sich nach der Frage, nicht nach einer pauschalen Stufenlogik.

### Rückfrage- und Abbruchregeln

- Wenn ein bekannter direkter Kontext die bestätigte Frage beantwortet, wird
  nicht inventarisiert.
- Wenn die fachliche Frage einen konkreten Inhalt betrifft, aber nur ein
  File-Link vorliegt, fragt der Agent nach einem Node-, Section-, Frame- oder
  Component-Link.
- Wenn eine Funktion in diesem Setup scheitert, wird der Status
  `fehlgeschlagen` oder `blockiert` dokumentiert; ein anderer Weg ist nur
  zulässig, wenn er dieselbe bestätigte Frage beantwortet.
- Wenn der gewünschte Befund eine ganze Datei oder mehrere Seiten betrifft,
  wird der Umfang zuerst in Page-/Section-/Node-Schritte aufgeteilt, statt
  ungezielt immer neue Nodes zu lesen.
- Wenn ein Tool nur Kandidaten, Screenshots oder generierte Repräsentationen
  liefert, werden daraus keine fachlichen Standards, keine Codequalität und
  keine Accessibility-Abnahme abgeleitet.
- Wenn ein Schreib- oder Transferweg nicht direkt belegt ist, stoppt der
  Agent vor Rekonstruktion, Import oder Ersatzhandlung und legt Optionen vor.

## Verbindliche Einsatzgrenze für KI-gestützte externe Dienste

Diese Regeln gelten für KI-Tools und KI-Funktionen im Kontext der Kreation,
einschließlich Figma, Miro, Plugins, APIs, MCP-Servern und deren
Integrationswegen. Die zugrunde liegende Entscheidung ist
[D-031](../governance/decisions.md#d-031--ki-gestutzte-externe-dienste-im-gestaltungskontext).

- Agentische Unterstützung ist nur zulässig, wenn eine intern freigegebene
  KI-Alternative nutzbar ist, ohne die KI-Verarbeitung des Tool-Anbieters
  zwingend zu aktivieren.
- Jede Nutzung benötigt eine ISB-Prüfung und ISMS-Dokumentation für das
  konkrete Tool, den Integrationsweg und den Anwendungsfall. Vertrags-,
  Regulierungs- und Datenschutzvorgaben des Projekts haben Vorrang.
- Zugriffe erfolgen ausschließlich über freigegebene Integrationen, Plugins,
  APIs oder MCP-Server. Berechtigungen sind rollenbasiert und minimal; Lesen,
  Vorschlag und Schreiben werden getrennt freigegeben.
- Unternehmenskonto, SSO/MFA sowie nachvollziehbare Zugänge und Änderungen
  sind Voraussetzung. Vor Nutzung müssen Datenfluss, Auftragsverarbeitung,
  Unterauftragsverarbeiter, Speicherort, Löschkonzept und mögliche
  Trainingsnutzung für den konkreten Dienst geklärt sein.
- Zulässig sind nur freigegebene Inhalte, allgemeine UI-Konzepte, Wireframes,
  Design-System-Bausteine sowie synthetische oder freigegebene Beispieldaten.
  Ohne gesonderte Freigabe sind personenbezogene Daten, vertrauliche
  Kundeninformationen, Zugangsdaten, Tokens, API-Keys, Secrets sowie
  sicherheitsrelevante Architektur- oder Betriebsinformationen ausgeschlossen.
- KI-Ergebnisse sind Vorschläge und fachlich sowie gestalterisch zu prüfen.
  Schreibzugriff setzt Versionierbarkeit, verantwortliche Zuordnung und
  menschliche Freigabe vor produktiver oder kundensichtbarer Verwendung voraus.

Für Figma und Miro werden Workspace, Datei, Seite beziehungsweise Board und
der erlaubte Integrationsweg jeweils separat festgelegt. Export-, Import- und
Screenshot-Funktionen sowie aktivierbare Anbieter-KI sind Teil dieser Prüfung.

### Toolstatus: Lizenz, Machbarkeit und ISMS

Eine öffentliche Lizenz- oder Planinformation ist kein Freigabenachweis. Die
folgende Übersicht hält den am 2026-07-28 sichtbaren Stand für die im Projekt
verwendeten oder angesprochenen Dienste fest; konten-, vertrags- und
anwendungsfallspezifische Angaben bleiben offen, bis sie intern belegt sind.

| Dienst / Integrationsweg | Lizenz- und Planreferenz | Sichtbare Limitierung | ISMS- und Nutzungsstatus | Warnung |
|---|---|---|---|---|
| Figma-eigenes MCP `figma@openai-curated-remote` | Figma-[Nutzungsbedingungen](https://www.figma.com/legal/tos/) und [DPA](https://www.figma.com/legal/dpa/) für den Figma-Dienst; Lizenz-/Vertragsgrundlage des Connectors, konkreter Unternehmensvertrag, Plan und Plugin-/MCP-Freigabe: `offen` | Tatsächlicher Zugriff, Workspace-/Dateibereich, Konto, SSO/MFA, Datenfluss und Schreibberechtigung: `nicht bewertet` | ISB-/ISMS-Freigabe für diesen Integrationsweg: `offen` | **STOPP:** Keine Projekt- oder Kundendaten übermitteln und keine Aktion ausführen, bis die konkrete Freigabe dokumentiert ist. |
| Figma AI | [Figma AI Terms](https://www.figma.com/legal/ai-terms/) (Stand 2026-06-24); konkrete AI-Credits-Subscription und KI-Einstellungen: `offen` | Seat-Credits und gegebenenfalls PAYG sind plan- und kontenabhängig; Credits werden monatlich erneuert und nicht übertragen | Anbieter-KI bzw. deren Datenverarbeitung ist für den Anwendungsfall nicht freigegeben dokumentiert | **STOPP:** Nicht aktivieren oder verwenden, solange keine interne Ausnahme bzw. Freigabe vorliegt. |
| Southleft Design Systems MCP | Repository-Referenz `southleft/design-systems-mcp`; Lizenz, Vertrag, Plan und Subprozessoren: `nicht bewertet` | Laufzeitbefund E-033: keine belastbaren, passenden Treffer; tatsächlicher Korpus und Limits: `nicht bewertet` | ISB-/ISMS-Freigabe: `offen` | **STOPP:** Keine Projektinhalte eingeben. Der Dienst ist zusätzlich keine tragende Evidenzquelle. |
| Miro einschließlich KI-/Plugin-/API-Integration | [Miro Terms](https://miro.com/legal/terms-of-service/), [AI Terms](https://miro.com/legal/ai-features-addendum/) und [DPA](https://miro.com/legal/documents/Miro-Data-Processing-Addendum.pdf); konkreter Vertrag und Plan: `offen` | Keine Miro-Integration ist in diesem Projekt konfiguriert oder geprüft | ISB-/ISMS-Freigabe, erlaubte Boards und Anbieter-KI-Einstellung: `offen` | **STOPP:** Nicht integrieren oder nutzen, bis Freigabe und erlaubter Bereich dokumentiert sind. |

**Warnlogik:** `STOPP` bedeutet fehlende zwingende Freigabe oder unzulässige
Datenklasse; keine Nutzung. `EINSCHRÄNKUNG` bedeutet offene Lizenz-, Plan-,
Datenfluss- oder Laufzeitfrage; ausschließlich synthetische bzw. freigegebene
Daten und kein Schreiben. `HINWEIS` kennzeichnet nicht sicherheitskritische
Machbarkeits- oder Limitierungsfragen. Nicht belegte Angaben bleiben
`offen` oder `nicht bewertet`; eine installierte Verbindung, ein Repository
oder ein Anbietertext ersetzt keine interne Freigabe.

## Eingabe-Checkliste für Menschen

Vor dem Auftrag möglichst angeben:

- Figma-Link oder genaue Datei/Node, falls vorhanden
- gewünschtes Ergebnis: verstehen, beraten, in Code übersetzen oder in Figma
  ändern
- Zielplattform bzw. Framework, falls Code entstehen soll
- gewünschter Schreibumfang: lesen, Vorschlag, Pilot oder direkte Änderung
- relevante Projektdateien und bestehende Konventionen

## Agenten-Entscheidungslogik

0. Geht ein Objekt zwischen Dateien, Systemen, Libraries oder Accounts über?
   → zuerst Übernahmeart, Erhaltungsziel und Funktionsklasse klären. Erst
   danach einen direkten Transfer-, Canvas-, Library- oder
   Rekonstruktionsweg prüfen; keine Ersatzhandlung wählen.
1. Betrifft die Aufgabe eine konkrete Figma-Datei oder Arbeitsfläche? → Figma-
   eigenes MCP oder bewusst Southleft Console MCP wählen.
2. Geht es nur um allgemeine Beratung? → Southleft Design Systems zuerst mit
   einer kleinen, passenden Abfrage prüfen. Fehlen belastbare Treffer, Grenze
   ausweisen und Primärquellen statt Toolannahmen verwenden.
3. Geht es um Code aus einem Figma-Node? → Figma-Design-to-Code plus Figma-
   eigenes MCP.
4. Geht es um lokale/interaktive Canvas-Inspektion oder Batch-Aktionen? →
   Southleft Figma Console MCP, sofern die Bridge verfügbar ist.
5. Geht es um neue oder geänderte Figma-Inhalte ohne Bridge? → passendes
   Figma-eigenes Schreib- oder Erzeugungs-Skill.
6. Ist die Aufgabe unklar? → zuerst Ziel, gewünschtes Artefakt und bei einer
   Übernahme die Übernahmeart klären; nicht
   mehrere Tools auf Verdacht aufrufen.

### Verantwortung für die Funktionswahl

Die Auswahl der passgenauen Tool-Funktion liegt beim Agenten, nicht beim
Menschen. Vor dem ersten Aufruf bestimmt der Agent, ob Datei-/Objekttransfer,
Library-, Collection-, Variablen-, Node-, Komponenten- oder Canvas-Kontext
benötigt wird und wählt dafür die kleinste verfügbare Funktion, die die
bestätigte Aktion tatsächlich ausführen kann.

Wenn ein Werkzeug nur einen engeren Ausschnitt liefert als erforderlich, darf
der Agent den Befund nicht als vollständig ausgeben. Er prüft zunächst, ob eine
passendere verfügbare Funktion existiert. Bleibt die passende Funktion unklar
oder fehlt sie, benennt der Agent die Lücke und stellt eine gezielte Rückfrage;
er verlagert die technische Tool-Auswahl nicht als Fehlersuche auf den Menschen.

Die gewählte Funktion, ihr tatsächlicher Scope und die nicht abgedeckten
Informationen werden im Transparenznachweis festgehalten.
