# Research und Konzeptbefund: Designer-QA-Unterstützung

## Status

Dieser Befund ist ein unverbindlicher Architekturvorschlag im Modus
`Vorschlag`. Er ist kein neuer Standard, keine bestätigte Decision und kein
Ausführungsauftrag für Figma, Code oder Infrastruktur.

## Transparenznachweis

| Feld | Einordnung |
|---|---|
| Modus | `Vorschlag` mit anschließendem `Status sichern` |
| Nutzungsebene | Verbunden: `Fachliche Nutzung` und `Systementwicklung`, getrennt bewertet |
| Rolle | `Review` und `Governance`, fachlicher Fokus `Design` |
| Gegenstand | Repository-Architektur für fachliche Designer-QA mit agentischer Unterstützung |
| Interne Quellen | `AGENTS.md`, `docs/README.md`, Base Template, Decisions, Evaluation Framework und Log, Rollen/User Stories, Workflows, Checklists, Tooling Map, aktuelle Reviews |
| Externe Quellen | werden im Research-Abschnitt mit Quelle, Datum und Übertragbarkeitsgrenze ausgewiesen |
| Automatisch ausgeführt | Repository-Inventur, Quellenabgleich, Befundstruktur und Konzeptentwurf |
| Nicht verändert | Figma, externe Systeme, kanonische Decisions, Wiki-Detailseiten und Tool-Konfigurationen |
| Menschlich zu prüfen | Geltungsbereich des Konzepts, Priorität, spätere Regelsetzung und ein erster realer QA-Fall |

## Arbeitsfrage

Wie muss die bestehende Struktur so umgebaut werden, dass sie Designer:innen
bei fachlicher Qualitäts- und Entscheidungsarbeit mit Figma unterstützt, ohne
eine allgemeine Agentenplattform, eine Design-to-Code-Infrastruktur oder eine
neue Toolabhängigkeit zu erzeugen?

## Interner Ausgangsbefund

### Was bereits tragfähig ist

- Der Designer ist fachlich verantwortlicher Mensch für Zweck, Semantik,
  Nutzung, visuelle Systemlogik, Zustände, Accessibility und Abnahme.
- Der Agent darf Kontext erschließen, passende Funktionen auswählen, Evidenz
  strukturieren, Unsicherheit markieren und Vorschläge vorbereiten.
- Figma-Struktur, Screenshot oder Variablenwerte werden nicht automatisch als
  fachliche Bedeutung, Accessibility-Nachweis oder Freigabe behandelt.
- `PROMPT`/`AUSFÜHREN`, Scopebegrenzung, Evidenzstatus, menschliche Freigabe und
  Test-zu-Evaluation-Rückfluss bilden eine belastbare Kontrolllogik.
- D-034 bis D-036 und E-067 bis E-070 schützen vor Zielverschiebung bei
  Komponentenaufträgen: Erstellen, Prüfen und Dokumentieren werden getrennt.
- D-017, D-025, D-026, D-028, D-029, D-031, D-032 und D-033 sichern Leanheit,
  Tool-Fit, externe Abhängigkeiten, Kosten-/Freigabeprüfung und selektive
  Übernahme von Wissen.

### Zentrale Designer-Rolle

Der Designer ist kein technischer Bediener des Agenten und kein bloßer
QA-Eingabegeber. Er bringt die fachliche Frage, die Bedeutung und die
Entscheidung ein. Er muss keine MCP-Funktion, Node-ID oder API-Syntax kennen.
Er muss aber beurteilen können, ob ein Befund für Nutzung, Systemlogik,
Zustände, Tokens, Accessibility und visuelle Qualität relevant ist.

### Zentrale Bedingung der Arbeitsteilung

Die fachliche Frage, Bedeutung, Priorität und Freigabe bleiben beim Menschen.
Die Maschine arbeitet nur innerhalb einer begrenzten, belegbaren
Unterstützungsfunktion:

```text
fachliche Frage → minimale Quelle → passende Funktion → Evidenzstatus
→ begrenzte Ableitung → menschliche Entscheidung
```

Ohne fachliche Frage darf das Tool nicht den Scope definieren. Ohne belegte
Evidenz darf der Agent keine Bedeutung behaupten. Ohne menschliche Bewertung
wird ein Ergebnis weder zur Regel noch zur Freigabe.

## Bereits sichtbare Architekturprobleme

| Befund | Status | Auswirkung |
|---|---|---|
| Regeln und Anforderungen sind über `AGENTS.md`, `docs/`, Wiki und historische Reviews verteilt. | belegt | Der Chat oder die Erinnerung des Agenten kann faktisch zur fehlenden Integrationsschicht werden. |
| D-009 bis D-016 sind im Decision Log überwiegend `Entwurf`, werden aber operativ referenziert. | belegt | Status und tatsächliche Nutzung fallen auseinander. |
| Der Wiki-Freeze E-071 ist noch nicht als Ablösung der aktiven Wiki-Pflegeentscheidungen modelliert. | belegt | D-019, Wiki-Pflegeabschnitte und der neue Freeze überlagern sich. |
| Das Base Template führt v0.1/v0.2/v0.3 als Ausbaustufen, obwohl spätere Figma-Piloten und D-034 bis D-036 bereits einen anderen Reifeverlauf zeigen. | belegt | Die Roadmap beschreibt den historischen Aufbau, nicht zuverlässig den aktuellen Zielzustand. |
| Evaluation Log und Regelkandidatenübersicht bewahren wertvolle Historie, sind aber keine kompakte aktuelle Steuerung. | belegt | Alte nächste Schritte und aktuelle Regeln müssen manuell auseinandergehalten werden. |
| Tooling Map enthält Figma-, Southleft-, Code-Connect- und externe Skillpfade, obwohl der aktuelle Zweck Designer-QA ohne Codeinfrastruktur ist. | belegt | Nicht benötigte Integrationspfade vergrößern Kontext, Pflege und Abhängigkeitsrisiko. |

## Arbeitsannahme für den Konzeptentwurf

Der aktuelle Zielgegenstand ist ein fachliches Assistenzsystem für
Designer-QA:

- Figma ist die Quelle des zu prüfenden Designzustands.
- Das Repository hält Prüflogik, Begriffe, Status, Befunde und Learnings.
- Der Agent vermittelt zwischen fachlicher Frage und passender Evidenz.
- Der Designer bewertet Bedeutung, Qualität und Konsequenz.
- Schreiben in Figma bleibt ein gesonderter, freizugebender Sonderfall.
- Code Connect, Design-to-Code, Produktionscode, Synchronisation,
  Multi-Agenten-Orchestrierung und zusätzliche Infrastruktur liegen außerhalb
  des aktuellen Scopes.

## Externer Research

### Figma MCP

Die offizielle Figma-Dokumentation beschreibt den MCP-Server als Quelle für
strukturierten Designkontext aus ausgewählten Layern, darunter Frames,
Komponenten, Layout und Variablen. Sie trennt die Aufgabe des Servers von der
Interpretation durch den Agenten und weist darauf hin, dass das Ergebnis von
Kontextqualität, Modell und Prompt abhängt. Das passt direkt zum bestehenden
Prinzip „Evidenz vor Ableitung“.

Für den aktuellen Zweck ist davon nur der read-only Teil relevant:
Designkontext, Screenshots und Variablen-/Komponenteninformationen. Schreiben,
Canvas-Generierung, Code-Generierung und Code Connect werden nicht als
Architekturvoraussetzung übernommen.

Die Figma-Dokumentation beschreibt Canvas-Schreiben weiterhin als Beta mit
menschlicher Prüfung und Cleanup. Es benötigt Edit-Rechte und den Remote-MCP;
Schreibzugriff außerhalb von Drafts setzt einen Full Seat voraus und soll
später nutzungsbasiert abgerechnet werden. Das bestätigt, Schreibzugriff als
separaten, kosten- und freigabepflichtigen Sonderfall zu behandeln.

Quellen:

- [Figma MCP: Introduction](https://developers.figma.com/docs/figma-mcp-server/)
- [What does the MCP server do, and what does my agent do?](https://developers.figma.com/docs/figma-mcp-server/mcp-vs-agent/)
- [Figma MCP: Write to canvas](https://developers.figma.com/docs/figma-mcp-server/write-to-canvas/)
- [Figma MCP: Tools and prompts](https://developers.figma.com/docs/figma-mcp-server/tools-and-prompts/)

### Model Context Protocol

Die aktuelle MCP-Spezifikation trennt Host, Client und Server. Der Host
aggregiert Kontext, kontrolliert Berechtigungen und behandelt
Nutzerfreigaben. Tools gelten als potenziell ausführbare Aktionen; explizite
Einwilligung und verständliche Autorisierung gehören zur Sicherheitslogik.

Übertragbar ist deshalb nicht die Idee „mehr Tools“, sondern die
Verantwortungstrennung: Ein Figma-Adapter liefert begrenzte Evidenz; die
Arbeitssteuerung und fachliche Entscheidung bleiben außerhalb des Adapters.

Quelle:

- [Model Context Protocol Specification](https://modelcontextprotocol.io/specification/2025-11-25)
- [MCP Architecture](https://modelcontextprotocol.io/specification/2025-11-25/architecture)

### Agentische Laufzeitmuster

Aktuelle Agenten-SDKs bündeln Guardrails, Tool-Freigaben, Human-in-the-loop
und Tracing. Diese Muster bestätigen die Notwendigkeit von Stopppunkten,
Freigaben und Nachvollziehbarkeit. Sie begründen aber keine Einführung eines
Agenten-SDKs oder einer Multi-Agenten-Laufzeit in diesem Projekt.

Für den aktuellen Reifegrad genügt die vorhandene regelgeleitete Arbeitsform:
`PROMPT`, minimale Evidenz, Befund, menschliche Bewertung und
`Status sichern`. Eine Laufzeit wird erst dann relevant, wenn ein realer
wiederkehrender Ablauf außerhalb des Chats nachgewiesen ist.

Quelle:

- [OpenAI Agents SDK](https://openai.github.io/openai-agents-python/)
- [Guardrails](https://openai.github.io/openai-agents-python/guardrails/)
- [Human-in-the-loop](https://openai.github.io/openai-agents-python/human_in_the_loop/)
- [Tracing](https://openai.github.io/openai-agents-python/tracing/)

### Accessibility als fachliche Grenze

W3C beschreibt Zustands- und Eigenschaftsinformationen als etwas, das für
assistive Technologien programmatisch verfügbar sein muss. Eine Figma-
Struktur oder ein Screenshot kann diese Anforderung nicht allein belegen.
Accessibility bleibt damit eine fachliche Prüf- und Abnahmefrage; der Agent
kann Evidenz sammeln und offene Prüfungen markieren, aber keine vollständige
Abnahme aus visueller Struktur ableiten.

Quelle:

- [W3C ARIA5: State and Property Attributes](https://www.w3.org/WAI/WCAG21/Techniques/aria/ARIA5)

## Erster Konzeptansatz für den Umbau

### Zielbild

Das System wird als **Designer-QA-Unterstützung** verstanden:

```text
Designerfrage
    ↓
Scope und Mindestquelle
    ↓
read-only Figma-Evidenz
    ↓
Befund mit Evidenzstatus
    ↓
fachliche Designerbewertung
    ↓
Entscheidung oder nächster Prüfschritt
    ↓
repo-basierter Nachweis
```

Der Designer bleibt fachlicher Eigentümer. Der Agent ist ein begrenzter
Vermittler zwischen Frage, Quelle und Befund. Das Repository ist die
Wissens- und Nachweisschicht, damit kein notwendiger Kontext im Chat verbleibt.

### Zielarchitektur in fünf kleinen Schichten

| Schicht | Aktuelle Aufgabe | Nicht enthalten |
|---|---|---|
| Fachliche Frage | Nutzung, Bedeutung, Zustände, visuelle Systemlogik und gewünschte Entscheidung benennen | technische Toolsyntax vom Designer verlangen |
| Evidenzadapter | ausgewählten Figma-Node mit kleinstem read-only Zugriff lesen | automatische semantische Interpretation |
| QA-Befund | Beobachtung, Ableitung, Unsicherheit, Quelle und Auswirkung trennen | automatische Freigabe |
| Designer-Entscheidung | bestätigen, nacharbeiten, verwerfen oder offen lassen | Delegation fachlicher Verantwortung an das Modell |
| Repository-Nachweis | bestätigte Learnings und begrenzte Konzepte versionieren | Chat als alleinige Wissensquelle |

### Aktueller Arbeitsablauf

1. Designer:in benennt eine fachliche Frage und den bekannten Figma-
   Gegenstand.
2. Agent erstellt einen verständlichen `PROMPT` mit Scope, Nicht-Scope,
   minimaler Quelle, Funktion und Abnahme.
3. Nach `AUSFÜHREN` liest der Agent nur die erforderliche Evidenz.
4. Der Befund trennt sichtbar: `sichtbar`, `abgeleitet`, `nicht bewertet`,
   `nicht nachgewiesen` und `offen`.
5. Der Agent formuliert Optionen oder einen kleinen Vorschlag.
6. Die Designer:in entscheidet fachlich.
7. Nur bestätigte, wiederverwendbare Learnings werden repo-first gesichert.

### Was der Umbau zuerst leisten soll

- aktuelle Designer-Anforderungen aus den verstreuten Quellen in einem
  überprüfbaren QA-Vertrag zusammenführen;
- aktive Regeln von historischen, offenen und späteren Infrastrukturpfaden
  trennen;
- Figma-Tooling als Evidenzadapter und nicht als fachliche Autorität führen;
- den Evaluation Log als Historie behalten, aber nicht als aktuelle
  Prozesssteuerung verwenden;
- den Wiki-Freeze respektieren und keine neue Vermittlungsschicht erzeugen;
- erst nach einem realen wiederkehrenden QA-Fall entscheiden, ob strukturierte
  Befunddaten oder eine eigene Laufzeit nötig sind.

## Repo-spezifisches Zielbild und Anforderungen

Dieser Abschnitt verdichtet den vorhandenen Bestand zu einem Zielbild für die
weitere Systementwicklung. Er ist aus den Rollenanforderungen, der bestehenden
Governance, den Figma-Learnings und den dokumentierten Fehlentwicklungen
abgeleitet. Er beschreibt daher keinen generischen Agentenbaukasten und keine
neue Produktentscheidung.

### Zielstellung

Das Repository soll schrittweise zu einem **arbeitsfähigen Assistenzsystem für
Designer:innen** umgebaut werden. Es übersetzt die vorhandene Governance in
reale, verständliche Arbeitsabläufe und hält deren Evidenz, Grenzen und
Entscheidungen nachvollziehbar fest.

Der Designer bringt fachliches Anliegen, Bedeutung, Priorität und Abnahme ein.
Das System hilft bei Klärung, Quellenwahl, begrenzter Figma-Lektüre,
Befundstruktur und Nachweisführung. Es nimmt dem Designer keine fachliche
Entscheidung ab und setzt keine technische Infrastruktur voraus, die im
Repository noch nicht belegt ist.

Damit ist das Zielbild weder eine Dokumentationsablage noch eine allgemeine
Agentenplattform. Es ist eine kontrollierte Arbeitsteilung für die vorhandene
Designer-QA-Praxis:

```text
Designeranliegen
  → geführte fachliche Klärung
  → Gegenstand, Nutzungsebene und Scope
  → minimale Quelle und passende Funktion
  → Evidenz mit sichtbarem Status
  → strukturierter Befund und begrenzte Ableitung
  → menschliche Bewertung und Entscheidung
  → repo-basierter Nachweis
  → kontrollierter Rückfluss in Evaluation und spätere Regelkandidaten
```

### Nutzer, Rollen und Systemgrenze

| Perspektive | Verbindlicher Beitrag | Nicht delegierbar bzw. nicht vorausgesetzt |
|---|---|---|
| Designer:in | fachliche Frage, Zweck, Bedeutung, Priorität, Qualitätsurteil, Entscheidung und Abnahme | keine MCP-Syntax, Node-ID- oder API-Kenntnis als Bedienvoraussetzung |
| Agent/Assistenz | Anliegen verständlich spiegeln, Scope klären, kleinste passende Funktion wählen, Evidenz sammeln, Unsicherheit markieren, Befund strukturieren und Optionen vorbereiten | keine eigenständige Bedeutungsfestlegung, Freigabe, Regelsetzung oder Priorisierung |
| Repository | ausführbare Arbeitsregeln, Quellenstatus, Befunde, bestätigte Entscheidungen und Learnings nachvollziehbar halten | kein Ersatz für die fachliche Entscheidung und keine unkommentierte Chatablage |
| Figma-Adapter | ausgewählten Designzustand read-only als Evidenz liefern: Node-Kontext, Screenshot, Komponenten-, Variablen- oder Strukturwerte | keine automatische semantische, visuelle oder Accessibility-Freigabe |

Die aktuelle Systemgrenze endet bei Designer-QA-Unterstützung, Figma-Evidenz,
Governance, Befund und Repository-Nachweis. Produktionscode, Code Connect,
Design-to-Code, Synchronisation, automatische Canvas-Schreibvorgänge,
Multi-Agenten-Orchestrierung, zusätzliche MCP-Server und eine neue Wiki-
Vermittlungsschicht sind bewusst außerhalb des Zielbilds.

### Funktionale Muss-Anforderungen

| ID | Anforderung | Ableitung aus dem Bestand |
|---|---|---|
| F-01 | Ein Designeranliegen muss in fachlicher Sprache aufgenommen und in Ziel, Gegenstand, Nutzungsebene, Modus, Rolle, Aktion, Umfang, Grenzen, Ergebnis und Abnahme überführt werden. | `AGENTS.md` Arbeitskontext; Prompting Guide |
| F-02 | Vor jeder Ausführung muss ein sichtbarer `PROMPT` Scope, Nicht-Scope, Quelle, Funktion, Grenzen und Abnahme bestätigen. `AUSFÜHREN` startet nur diesen bestätigten Auftrag. | `AGENTS.md`; `docs/operations/prompting-guide.md` |
| F-03 | Die Assistenz muss die kleinste passende Funktion und die minimale Quelle wählen und deren tatsächlichen Scope offenlegen. | D-017, D-025, D-026, D-031, D-032, D-033 |
| F-04 | Jeder Befund trennt mindestens Beobachtung/Evidenz, begrenzte Ableitung, Unsicherheit, nicht bewertete Aspekte und offene Prüfung. | Evaluation Framework; D-028, D-029 |
| F-05 | Fachliche Bedeutung, Priorität, Ausnahme, Freigabe und Regelsetzung bleiben beim Menschen. Der Agent darf Optionen und Rückfragen vorbereiten, nicht stillschweigend entscheiden. | Rollen/User Stories; D-025, D-026, D-034–D-036 |
| F-06 | Figma-Lesen bleibt read-only im Standardpfad. Schreiben ist ein gesonderter Auftrag mit eigenem Scope, expliziter Freigabe und anschließender menschlicher Prüfung. | Figma-Research; `AGENTS.md`; E-067–E-070 |
| F-07 | Ein abgeschlossener Arbeitsgang erzeugt einen repo-basierten Nachweis mit Quelle, Status, Befund, Entscheidung bzw. offener Frage und genau einem nächsten Schritt. | `AGENTS.md`; Evaluation Framework; E-071/E-072 |
| F-08 | Nicht belegbare Aussagen werden als `nicht bewertet`, `nicht nachgewiesen`, `eingeschränkt bewertet` oder `offen` geführt; aus fehlender Evidenz entsteht kein Standard. | Transparenzpflicht; D-028, D-029 |
| F-09 | Tests bleiben begrenzt, reversibel und nicht-kanonisch. Der Rückfluss lautet `Test → Befund → menschliche Bewertung → Evaluation → gegebenenfalls Übernahme`. | `AGENTS.md`; D-034–D-036 |

### Nichtfunktionale Muss-Anforderungen

- **Nachvollziehbarkeit:** Jede Ableitung ist auf eine vorhandene Quelle, eine
  konkrete Funktion und deren Scope zurückführbar.
- **Verständlichkeit:** Der Designer sieht fachlich lesbare Ergebnisse und
  muss keine Toolnamen oder technischen Parameter interpretieren, um zu
  entscheiden.
- **Begrenztheit:** Kein Ablauf erweitert seinen Umfang durch implizite
  Annahmen, Toolketten oder alte Chat-Kontexte.
- **Reversibilität:** Vorschlag und Pilot verändern keine kanonische Quelle;
  Änderungen an Regeln, Tokens, Komponenten, Figma oder Infrastruktur bleiben
  ausdrücklich freigabepflichtig.
- **Pflegearmut:** Der Umbau erzeugt keine parallele Regelablage. `docs/` ist
  für ausführbare Steuerung zuständig, `reviews/` für Vorschläge und Befunde;
  die Wiki-Pflege bleibt pausiert.
- **Grenztransparenz:** Nichtverfügbarkeit, Berechtigungen, Kosten-, Plan- und
  Toolgrenzen werden vor einer fachlichen Schlussfolgerung sichtbar gemacht.

### Zustands- und Freigabelogik

Ein Arbeitsgang darf nur in dieser Reihenfolge fortschreiten:

1. **Anliegen:** Die fachliche Frage und der bekannte Gegenstand liegen vor.
2. **Klärung:** Ziel, Nutzungsebene, Scope, Nicht-Scope und Abnahme sind
   verständlich bestätigt.
3. **Quelle/Funktion:** Die kleinste passende Quelle und Funktion sind gewählt;
   deren Grenzen sind bekannt.
4. **Evidenz:** Der gelesene Zustand ist mit Quelle und Evidenzstatus belegt.
5. **Befund:** Beobachtung und Ableitung sind getrennt; offene Prüfungen sind
   sichtbar.
6. **Menschliche Entscheidung:** Designer:in bestätigt, verwirft, priorisiert,
   beauftragt eine Rückfrage oder lässt den Punkt offen.
7. **Nachweis:** Nur der bestätigte Status wird im passenden Repository-Artefakt
   gesichert; ein möglicher Regelkandidat bleibt bis zur expliziten Regelsetzung
   unverbindlich.

Der Ablauf stoppt bei unklarem Gegenstand, fehlender Mindestquelle,
unsupportedem Tool, widersprüchlichem Status, nicht belegbarer Ableitung oder
fehlender Freigabe für eine Schreibaktion. Ein Stop ist ein sichtbarer Befund,
kein Anlass, den Scope stillschweigend zu erweitern.

### Anforderungen an Evidenz und Repository-Nachweis

Ein verwertbarer Nachweis enthält mindestens:

- fachliche Frage und konkreten Gegenstand;
- Nutzungsebene, Modus, Rolle, Scope und Nicht-Scope;
- verwendete Quelle/Funktion und deren tatsächlichen Toolingstatus;
- sichtbare Beobachtung bzw. Figma-Evidenz;
- getrennte Ableitung mit Evidenzstatus und Unsicherheit;
- menschliche Bewertung, Entscheidung oder offene Frage;
- Status des Artefakts (`Vorschlag`, `Pilot`, `bestätigt`, `offen`,
  `nicht bewertet` o. Ä. gemäß zuständiger Detailquelle);
- genau einen nächsten Schritt und den Ort des gesicherten Nachweises.

Damit bleibt der Chat ein Arbeitskanal, aber kein Wissensmonopol. Ein Ergebnis
ist erst dann systemisch verfügbar, wenn es in der zuständigen Repository-
Quelle oder als klar verknüpfter Befund auffindbar ist.

### Bewusst außerhalb des Zielbilds

Folgende Ideen werden aus den bisherigen Fehlentwicklungen ausdrücklich nicht
als versteckte Anforderungen übernommen:

- allgemeiner Agenten- oder Multi-Agenten-Runtime-Bau;
- automatische Regel-, Token- oder Komponenten-Erzeugung;
- Code Connect, Design-to-Code, Produktionscode oder Handoff-Automatisierung;
- dauerhafte Figma-Synchronisation oder ungeprüftes Canvas-Schreiben;
- Reaktivierung der Wiki-Pflege als zweite operative Wissensschicht;
- neue SDK-, Plugin- oder MCP-Abhängigkeit ohne konkreten wiederkehrenden
  Bedarf und vorherige Freigabe;
- ein lokaler QA-Pilot als Ersatz für den noch ausstehenden systemischen
  Architekturabgleich.

### Offene Architekturentscheidungen

Diese Punkte sind bewusst offen und dürfen nicht durch Implementierung
vorweggenommen werden:

1. Welche vorhandenen Regeln und Entwurfsentscheidungen werden nach dem
   Quellen-/Statusabgleich bestätigt, zusammengeführt, abgelöst oder verworfen?
2. Welche minimalen Befundfelder helfen Designer:innen im Alltag, ohne ein
   neues, parallel zu pflegendes Format zu erzeugen?
3. Welche konkrete read-only Figma-Funktion ist für den ersten validierenden
   Fall tatsächlich verfügbar und ausreichend?
4. Ab welchem nachgewiesenen Wiederholungsbedarf rechtfertigt eine strukturierte
   Befundablage oder Laufzeit mehr Nutzen als Pflege- und Abhängigkeitskosten?

### Ein nächster Systemschritt

Als nächstes wird ein **systemischer Architekturabgleich** vorbereitet: eine
Quellen-/Statusmatrix, ein konsistenter Rollen- und Arbeitsteilungsvertrag,
eine Trennung aktiver und historischer Pfade sowie ein behutsamer Migrations-
und Ablöseplan. Erst nach menschlicher Bewertung dieses Abgleichs darf ein
begrenzter read-only QA-Fall zur Validierung des Zielbilds beauftragt werden.

## Migrationskandidaten und Grenzen

| Bereich | Erste Einordnung |
|---|---|
| D-009 bis D-016 | Status- und Quellenabgleich erforderlich; nicht stillschweigend als bestätigt behandeln. |
| D-019 und Wiki-Pflegeabschnitte | Mit E-071 abgleichen; der Freeze ist noch keine ablösende Decision. |
| v0.1/v0.2/v0.3 im Base Template | Historische Entwicklungsstaffelung; nicht als aktuelles Produktziel verwenden. |
| Code Connect, Design-to-Code und Handoff | Außerhalb des aktuellen Designer-QA-Scopes; nur als spätere Grenze referenzieren. |
| externe Skills, Southleft und weitere MCPs | Beobachtungs- oder Vergleichsmaterial; kein aktueller Architekturbaustein. |
| `reviews/` | geeigneter Ort für Vorschläge und Befunde, solange daraus keine Regel abgeleitet wird. |

## Offene Entscheidungen

- Welche vorhandenen Regeln werden nach dem Statusabgleich bestätigt,
  zusammengeführt, abgelöst oder verworfen?
- Soll der erste echte QA-Fall eine Komponentenstruktur, Tokenbindung,
  Zustandsmatrix oder visuelle Konsistenz prüfen?
- Welche minimalen Befundfelder sind für Designer:innen tatsächlich nützlich,
  ohne ein neues Pflegeformat zu erzeugen?
- Welche Figma-Lesefunktion ist für diesen einen Fall im konkreten Setup
  tatsächlich verfügbar und ausreichend?

## Systemischer Umbaupfad

Ein einzelner QA-Fall ist noch kein sinnvoller nächster Schritt. Er würde den
Umbau auf eine lokale Probe verengen, bevor Quellen, Status und Zielarchitektur
bereinigt sind. Der behutsame Umbaupfad lautet:

1. **Bestand und Autorität klären:** Jede Regel, Anforderung und Quelle einer
   Funktion, einem Status, einem Scope und einer verbindlichen Detailquelle
   zuordnen. Überlagerte, historische und verwaiste Inhalte sichtbar halten,
   aber aus dem aktiven Pfad entfernen.
2. **Rollen- und Arbeitsteilung als Systemvertrag sichern:** Fachliche
   Designerkompetenz, menschliche Entscheidungen, Agentenunterstützung,
   Toolgrenzen, Freigaben und Nicht-Leistungen in einer konsistenten
   Arbeitslogik zusammenführen.
3. **Zielarchitektur und Lebenszyklus festlegen:** Designer-QA-Unterstützung,
   Evidenzadapter, Befund, Entscheidung, Repository-Nachweis und optionale
   spätere Erweiterungen voneinander abgrenzen. Keine Infrastruktur vor dem
   belegten Bedarf vorwegnehmen.
4. **Migration und Ablösung planen:** Festlegen, welche Inhalte bleiben,
   zusammengeführt, als historisch markiert, pausiert, abgelöst oder verworfen
   werden. Dabei keine Schutzwirkung und keine bestehende Entscheidungsgrenze
   stillschweigend entfernen.
5. **Erst danach validieren:** Einen realen Designer-QA-Fall als begrenzten
   read-only Pilot wählen, um die bereits entschiedene Zielarchitektur zu
   prüfen. Der Pilot darf die Architektur nicht erst implizit definieren.

## Konzeptstatus

Der Konzeptansatz ist als unverbindlicher Vorschlag dokumentiert. Er ersetzt
keine menschliche Entscheidung und setzt keine neue kanonische Architektur.
Der zuvor genannte einzelne QA-Fall als unmittelbarer nächster Schritt wird
wegen der notwendigen ganzheitlichen Architekturklärung ausdrücklich nicht
übernommen.

## Bewusst nicht entschieden

- keine neue Decision oder bestätigte Regel;
- keine neue kanonische Architekturdatei;
- keine Wahl eines zusätzlichen MCP, Plugins oder Agenten-SDKs;
- keine Figma-Schreibarchitektur;
- keine Aussage über Code-Handoff oder Code Connect;
- keine Wiki-Reaktivierung.
