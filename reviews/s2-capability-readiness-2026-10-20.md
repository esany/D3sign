# S2 – Read-only-Figma-Capability-Readiness

## Status und Transparenz

Dieses Artefakt ist ein begrenzter Readiness-Pilot im Modus `Pilot`. Es
bereitet genau eine read-only-Figma-Capability für S2 vor, führt sie aber nicht
aus und erteilt keine Integrations- oder Datenfreigabe.

**Arbeitsstand:** Historischer Capability-Kandidat. Er ist nicht der aktuelle
Arbeitsweg und wird bis zu einer späteren, gesonderten Freigabe nicht weiter
ausgebaut.

| Feld | Einordnung |
|---|---|
| Ziel | Einen einzelnen, eng begrenzten Figma-Lesepfad für S2 prüfbar vorbereiten. |
| Gegenstand | `figma_get_metadata` für einen ausdrücklich benannten Figma-Node oder eine Page. |
| Nutzungsebene | `Systementwicklung`; fachliche Verständlichkeit für Designer:innen wird mitbewertet. |
| Modus | `Pilot`, read-only, reversibel. |
| Rolle | `Development`, `Review` und `Governance`. |
| Quellen | `AGENTS.md`, `docs/README.md`, Tooling Map, Figma-MCP-Tooling, Workflows, S2-Plan, S1-Vertrag und E-073. |
| Automatisch ausgeführt | Repo- und Tooloberflächenabgleich, Kandidatenvergleich, synthetischer Adaptertest und Dokumentation. |
| Nicht ausgeführt | Kein Figma-Aufruf, kein Zugriff auf FileKey/Node, kein Screenshot, kein Variablenabruf, keine Schreibaktion. |
| Menschlich zu entscheiden | Ob der Kandidat für einen konkreten read-only-Testlauf freigegeben wird. |
| Pilotgrenze | Kein Capability-Register, keine neue Regel, kein Figma- oder Datenzugriff. |
| Genau ein nächster Schritt | Konkreten File-/Node-Scope und die interne read-only-Integrationsfreigabe entscheiden. |

## 1. Kandidat

### `figma.read.metadata.node.v1-candidate`

| Feld | Befund |
|---|---|
| Tatsächliche Funktion | `mcp__codex_apps__figma_get_metadata` / `figma_get_metadata` |
| Anbieterpfad | Figma-App-MCP im aktuellen Agent-Tooling |
| Readinessstatus | Werkzeugoberfläche sichtbar; in dieser Prüfung `nicht getestet` |
| Berechtigung | read-only; keine Figma-Schreibfunktion |
| Eingabe | `fileKey` und ein exakter `nodeId` für Node oder Page |
| Ausgabe | XML-Metadaten mit Node-IDs, Layer-Typen, Namen, Positionen und Größen |
| Evidenztyp | `E1` – Strukturmetadaten |
| S1-Anschluss | `EvidencePacket.source`, `capability_id`, `scope_read`, `observations`, `omissions`, `tool_status` |
| fachlicher Zweck | Einen konkret benannten Arbeitsgegenstand technisch lokalisieren und seine sichtbare Struktur begrenzen. |
| Nicht enthalten | Keine visuelle Qualitätsaussage, keine Variablenwerte, keine Semantik-, Accessibility- oder Abnahmeentscheidung. |

Der Kandidat ist absichtlich enger als ein vollständiger Design-Context-Abruf.
Er erzeugt nur eine strukturelle Landkarte für einen bereits benannten
Gegenstand. Eine Dateiübersicht ohne ausdrücklichen Auftrag ist kein zulässiger
Ersatz für einen konkreten Scope.

## 2. Kandidatenvergleich

| Kandidat | Status in diesem Pilot | Warum nicht der S2-Erstkandidat |
|---|---|---|
| `figma_get_metadata` | ausgewählter Kandidat, nicht getestet | kleinster strukturbezogener Abruf für einen exakten Node/Page-Scope |
| `figma_get_design_context` | verfügbar sichtbar, nicht getestet | liefert breiteren Design-/Code-Kontext und ist für eine konkrete Design-to-Code-Ausführung gedacht |
| `figma_get_screenshot` | verfügbar sichtbar, nicht getestet | nur erforderlich, wenn die fachliche Frage einen visuellen Sichtbefund verlangt |
| `figma_get_variable_defs` | verfügbar sichtbar, nicht getestet | nur passend bei einer konkreten Variablen- oder Tokenfrage am Node |
| `figma_use_figma` | verfügbar sichtbar, nicht ausgewählt | allgemeine Plugin-API mit Schreibfähigkeit; außerhalb des read-only-Slices |
| Figma-Console-Funktionen | Oberfläche sichtbar, nicht ausgewählt | separater Bridge-/Console-Pfad, nicht als bestehender S2-Integrationsweg bestätigt |

Die Auswahl ist keine allgemeine Rangfolge aller Figma-Funktionen. Sie gilt nur
für den vorbereiteten S2-Readiness-Fall mit einer strukturellen Frage an einem
bereits benannten Gegenstand.

## 3. Adaptervertrag

### 3.1 Zulässiger Input

Vor einem späteren Testlauf müssen alle folgenden Felder bestätigt sein:

| Feld | Pflicht | Prüfung |
|---|---:|---|
| `file_key` | ja | stammt aus einem vom Menschen bereitgestellten Figma-Link oder Setup |
| `node_id` | ja | exakt aus dem Link oder bestätigtem Kontext extrahiert; nie geraten |
| `scope` | ja | ein Node oder eine Page, keine implizite gesamte Datei |
| `question` | ja | konkrete Strukturfrage in verständlicher Sprache |
| `data_class` | ja | freigegebene Datenklasse vor Abruf |
| `human_owner` | ja | fachlich verantwortliche Person oder Rolle |
| `acceptance` | ja | prüfbarer Nachweis für den begrenzten Abruf |

Fehlt ein Feld, bleibt der Lauf `blocked` oder `clarification_required`.

### 3.2 Erwarteter EvidencePacket

```yaml
evidence_packet:
  evidence_id: ep-s2-example-001
  request_id: wr-s2-example-001
  source: "Figma-Link mit bestätigtem FileKey und Node-ID"
  capability_id: figma.read.metadata.node.v1-candidate
  scope_read: "ein bestätigter Node oder eine bestätigte Page"
  evidence_type: E1
  observations:
    - "Node-ID, Layer-Typ, Name, Position und Größe aus dem Tooloutput"
  omissions:
    - "keine visuellen Eigenschaften, Variablenwerte oder fachliche Bedeutung"
  completeness: partial
  tool_status: unknown
  captured_at: "YYYY-MM-DD"
  data_class: freigegeben
```

`tool_status` darf erst nach einem tatsächlichen Lauf `confirmed` oder
`failed` werden. Eine sichtbare Tooldefinition oder konfigurierte Verbindung
belegt keine erfolgreiche Ausführung.

## 4. Fehler- und Stopplogik

| Situation | Status | Reaktion |
|---|---|---|
| FileKey oder Node-ID fehlt | `clarification_required` | keinen Toolaufruf starten |
| Node-ID ist geraten oder nicht nachvollziehbar | `blocked` | Quelle nachfordern |
| Figma-Tool ist im Setup nicht erreichbar | `blocked` | keine Ersatzfunktion als gleichwertig ausgeben |
| Berechtigung, Plan oder Datenklasse ungeklärt | `blocked` | interne Freigabe klären |
| Output enthält nur Teilstruktur | `partial` | Auslassung dokumentieren; keine Vollständigkeit behaupten |
| Output ist leer oder nicht verwertbar | `failed` oder `unknown` | Ursache nicht raten; menschliche Prüfung oder Scopekorrektur |
| fachliche Bedeutung soll aus Metadaten folgen | `not_proven` | Finding darf nur die sichtbare Struktur enthalten |
| Schreibfunktion wird angefordert | `blocked` | separaten, ausdrücklich freigegebenen Schreibpfad verlangen |

## 5. Synthetische Validierung

### Fall A – ausreichend begrenzter Auftrag

**Eingang:** Eine Designerin benennt einen konkreten Figma-Node, fragt nach
seiner sichtbaren Struktur und schließt Screenshot, Variablenprüfung, Figma-
Änderung und Accessibility-Abnahme aus.

**Erwartung:**

```text
draft → scoped → evidence_pending → evidence_ready
→ finding_ready → human_review
```

Der Adaptervertrag ist möglich. Ein echter Toolstatus bleibt offen, weil kein
Figma-Aufruf Bestandteil dieses Pilots ist.

### Fall B – fehlender Gegenstand

**Eingang:** „Lies die Library-Struktur“ ohne FileKey, Page, Node oder konkrete
Abnahme.

**Erwartung:**

```text
draft → clarification_required → blocked
```

Ein Root-Inventar darf nicht eigenständig als Scope gewählt werden.

### Fall C – falsche fachliche Ableitung

**Eingang:** Metadaten nennen eine Component-Instance. Daraus soll automatisch
geschlossen werden, dass sie semantisch korrekt, barrierefrei oder als
Library-Standard freigegeben ist.

**Erwartung:**

```text
evidence_ready → finding_ready → not_proven → human_review
```

Die Strukturbeobachtung bleibt zulässig; die fachliche oder inklusive Aussage
bleibt unbewiesen.

## 6. Freigabegegenstand

Die S2-Freigabe muss sich auf genau diesen begrenzten Umfang beziehen:

1. konkrete Figma-Datei bzw. freigegebener FileKey;
2. konkreter Node- oder Page-Scope;
3. `figma_get_metadata` als einzige ausgeführte Capability;
4. read-only-Berechtigung und zulässige Datenklasse;
5. ein synthetischer oder ausdrücklich freigegebener Testfall;
6. EvidencePacket als Abnahmeformat;
7. menschliche Prüfung des resultierenden Findings;
8. keine anschließende Figma-Änderung.

Eine Freigabe dieses Kandidaten ermächtigt nicht zu `get_design_context`,
`get_screenshot`, `get_variable_defs`, `use_figma`, Console-Bridge-Funktionen,
Code Connect oder S3.

## 7. Repo-first-Delta

- **Neu gesichert:** S2-Kandidat, Kandidatenvergleich, Adaptervertrag,
  Fehler-/Stopplogik und drei synthetische Fälle.
- **Geändert:** E-073 erhält den S2-Readiness-Anschluss und die konkrete
  offene Freigabeentscheidung.
- **Bewusst nicht übernommen:** kein Figma-Aufruf, kein File-/Node-Zugriff,
  kein Capability-Register, keine Runtime, keine neue Regel, keine Decision,
  keine Schema-Datei und keine Wiki-Änderung.
- **Weiterhin offen:** konkrete Figma-Quelle, Datenklasse, Berechtigung,
  Testfreigabe und menschliche Abnahme.

## 8. Genau ein nächster menschlicher Entscheid

Soll `figma_get_metadata` für einen konkret benannten File-/Node-Scope als
read-only-S2-Pilot freigegeben werden, nachdem Datenklasse, Berechtigung und
Abnahme bestätigt sind?
