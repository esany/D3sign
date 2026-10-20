# S1 – Pilotvertrag für Arbeitsauftrag und Befund

## Status und Transparenz

Dieser Vertrag ist ein begrenzter, reversibler Pilot im Modus `Pilot`. Er ist
kein kanonisches Schema, keine neue Decision und keine Erweiterung der
Governance. Die Darstellung prüft, ob die bestehende Arbeitsteilung in
strukturierte, nachvollziehbare Objekte übersetzt werden kann.

| Feld | Einordnung |
|---|---|
| Ziel | Einen vollständigen Designer-Assistenzlauf ohne Chatrekonstruktion beschreiben können. |
| Gegenstand | `WorkRequest`, `EvidencePacket`, `Finding`, `Decision` und `RunRecord`. |
| Nutzungsebene | `Systementwicklung`; fachliche Wirkung auf Designer:innen getrennt betrachtet. |
| Modus | `Pilot`, reversibel und synthetisch. |
| Rolle | Development, Review und Governance. |
| Quellen | S0-Reconciliation, dev-ready Plan, `AGENTS.md`, Governance, Operations und Tooling Map. |
| Automatisch ausgeführt | Vertragsableitung, Status-/Übergangsentwurf und drei synthetische Durchläufe. |
| Nicht ausgeführt | Figma-Aufruf, externe Toolfunktion, Schreibaktion, Runtime, Code und reale Designerfallprüfung. |
| Menschlich entschieden | Der Pilotvertrag wird als Grundlage für den späteren S2-Slice weitergeführt. |
| Pilotgrenze | Keine kanonische Schema-Datei, keine Statusübernahme für D-009–D-016, keine Decision-Änderung. |
| Genau ein nächster Schritt | Konkrete read-only-Figma-Capability und Integrationsfreigabe für S2 klären. |

## 1. Zweck und Ablauf

Der Vertrag bildet genau diesen Arbeitsgang ab:

```text
WorkRequest
  → Klärung und Scope
  → Capability-Auswahl
  → EvidencePacket
  → Finding
  → menschliche Decision
  → RunRecord im Repository
```

Der Vertrag trennt fachliche Verantwortung von technischer Unterstützung:

- Designer:innen bringen Frage, Gegenstand, Bedeutung, Priorität und Abnahme
  ein.
- Die Assistenz klärt, begrenzt, wählt eine passende Capability, strukturiert
  Evidenz und bereitet Optionen vor.
- Figma liefert nur den tatsächlich gelesenen Designkontext.
- Das Repository hält Quelle, Status, Entscheidung und nächsten Schritt.

Eine Speicherung erzeugt keine fachliche Freigabe. Ein Vorschlag bleibt ein
Vorschlag, bis ein Mensch ihn bewertet.

## 2. Pilotobjekte

### 2.1 `WorkRequest`

**Zweck:** Ein fachliches Anliegen so begrenzen, dass eine passende Quelle und
Funktion gewählt werden kann.

| Feld | Pflicht | Bedeutung | Quelle |
|---|---:|---|---|
| `request_id` | ja | stabile Laufkennung | Evaluation/Arbeitsnachweis |
| `question` | ja | fachliche Frage in verständlicher Sprache | Rollen/User Stories, AGENTS |
| `subject` | ja | konkreter Figma-/Repository-Gegenstand | AGENTS, Workflows |
| `usage_level` | ja | `fachliche Nutzung`, `Systementwicklung` oder `verbunden` | D-025, AGENTS |
| `mode` | ja | `Lesen`, `Vorschlag`, `Pilot` oder `Umsetzen` | Base Template, AGENTS |
| `role` | ja | `Design`, `Development`, `Review`, `Governance` oder `neutral` | AGENTS, D-009 als offener Kandidat |
| `action` | ja | lesen, analysieren, vorschlagen, validieren oder schreiben | Prompting Guide |
| `scope` | ja | tatsächlich betroffener Umfang | AGENTS, D-018 |
| `non_scope` | ja | bewusst ausgeschlossene Bereiche | AGENTS, S0 |
| `expected_result` | ja | erwarteter Befund oder Nachweis | AGENTS |
| `acceptance` | ja | menschlich prüfbare Abnahme | AGENTS, Evaluation Framework |
| `human_owner` | ja | fachlich verantwortliche Person/Rolle | Rollen/User Stories, NIST-Übertragung |
| `status` | ja | Kandidatenstatus des Auftrags | Status-/Übergangsmodell |

**Abbruchbedingungen:** fehlende Frage, fehlender Gegenstand, unklarer Umfang,
fehlende Abnahme oder impliziter Schreibumfang.

### 2.2 `EvidencePacket`

**Zweck:** Sichtbare Evidenz, Quelle, Funktion und Auslassungen getrennt von
der fachlichen Deutung dokumentieren.

| Feld | Pflicht | Bedeutung | Quelle |
|---|---:|---|---|
| `evidence_id` | ja | stabile Evidenzkennung | Evaluation/Arbeitsnachweis |
| `request_id` | ja | Bezug zum Auftrag | WorkRequest |
| `source` | ja | konkrete Quelle und Referenz/Link | D-014, Tooling Map |
| `capability_id` | ja | tatsächlich verwendete Funktion | D-013 als offener Kandidat, Tooling Map |
| `scope_read` | ja | tatsächlich gelesener Umfang | Workflows, D-014 |
| `evidence_type` | ja | E0 Inventar, E1 Struktur, E2 Detail, E3 Screenshot, E4 menschlich bestätigt | Figma-Tooling |
| `observations` | ja | sichtbare Informationen ohne Deutung | D-014, Evaluation Framework |
| `omissions` | ja | nicht gelesene oder nicht sichtbare Informationen | Transparenzpflicht |
| `completeness` | ja | `complete`, `partial`, `unknown` oder `failed` | Workflows |
| `tool_status` | ja | `confirmed`, `restricted`, `unknown` oder `blocked` | AGENTS, Tooling Map |
| `captured_at` | ja | Zeitpunkt des Nachweises | Evaluation |
| `data_class` | ja | synthetisch, freigegeben, vertraulich oder gesperrt | D-031 |

**Abbruchbedingungen:** Capability nicht belegt, Scope überschritten,
Evidenz unvollständig ohne Kennzeichnung, gesperrte Datenklasse oder Quelle
nicht nachvollziehbar.

### 2.3 `Finding`

**Zweck:** Beobachtung, begrenzte Ableitung, Unsicherheit und mögliche
Auswirkung so trennen, dass ein Mensch entscheiden kann.

| Feld | Pflicht | Bedeutung | Quelle |
|---|---:|---|---|
| `finding_id` | ja | stabile Befundkennung | Evaluation |
| `request_id` | ja | Bezug zum Auftrag | WorkRequest |
| `evidence_ids` | ja | verwendete Evidenz | EvidencePacket |
| `observation` | ja | belegte Beobachtung | D-014 |
| `inference` | ja | begrenzte Ableitung oder `none` | D-014, D-028 |
| `impact` | ja | mögliche fachliche Auswirkung, keine Freigabe | Rollen/User Stories |
| `status` | ja | `visible`, `derived`, `not_assessed`, `not_proven`, `open` oder `blocked` | Transparenzpflicht, W3C-Grenze |
| `options` | ja | zulässige Handlungsoptionen inklusive Nicht-Ändern | Base Template, AGENTS |
| `recommendation` | nein | begründeter Vorschlag, niemals Entscheidung | AGENTS |
| `human_decision_id` | nein | Verweis auf menschliche Entscheidung | Decision |
| `next_step` | ja | genau eine Folgeaktion | AGENTS, Evaluation Framework |

**Abbruchbedingungen:** Ableitung ohne Evidenz, Accessibility-/Semantikbehauptung
aus rein visueller Evidenz, fehlende Optionen oder fehlender nächster Schritt.

### 2.4 `Decision`

**Zweck:** Die fachliche Bewertung durch einen Menschen von Vorschlag und
Befund trennen.

| Feld | Pflicht | Bedeutung | Quelle |
|---|---:|---|---|
| `decision_id` | ja | stabile Entscheidungskennung | Decisions |
| `finding_id` | ja | Bezug zum Befund | Finding |
| `decision_owner` | ja | verantwortliche Person/Rolle | D-002 als Grundsatz, Rollen |
| `options_considered` | ja | geprüfte Optionen inklusive Nicht-Ändern | Base Template |
| `state` | ja | `pending`, `accepted`, `rejected`, `revise` oder `deferred` | Pilotstatus |
| `rationale` | ja bei Abschluss | menschliche Begründung | Decisions |
| `scope` | ja bei Abschluss | Geltungsbereich der Entscheidung | Decisions |
| `affected_artifacts` | ja bei Abschluss | betroffene Quellen/Artefakte | Decisions |
| `rule_candidate` | ja | `yes` oder `no`, ohne automatische Regelsetzung | D-015 als offener Kandidat |
| `next_step` | ja | genau eine Folgeaktion | AGENTS |

`accepted` bedeutet in diesem Pilotvertrag nur menschlich akzeptierter Befund
oder Vorschlag. Es bedeutet nicht automatisch `Decision.status = bestätigt`
und ersetzt nicht `REGEL SETZEN`.

**Abbruchbedingungen:** kein menschlicher Owner, keine Begründung bei
Abschluss, unklarer Geltungsbereich oder Versuch, eine Regel automatisch zu
setzen.

### 2.5 `RunRecord`

**Zweck:** Den vollständigen Lauf repo-first auffindbar machen, ohne den Chat
als notwendige Wissensquelle zu benötigen.

| Feld | Pflicht | Bedeutung | Quelle |
|---|---:|---|---|
| `run_id` | ja | Laufkennung | Evaluation |
| `request_id` | ja | WorkRequest-Bezug | WorkRequest |
| `evidence_ids` | ja | Evidenzbezug | EvidencePacket |
| `finding_id` | ja | Befundbezug | Finding |
| `decision_id` | nein | Entscheidung, falls vorhanden | Decision |
| `status_history` | ja | nachvollziehbare Zustandsfolge | Evaluation Framework |
| `human_involvement` | ja | Eingaben, Prüfung, Entscheidung | Transparenzpflicht |
| `repository_path` | ja | gesicherter Nachweisort | repo-first-Regel |
| `open_items` | ja | offene Fragen und nicht bewertete Aspekte | AGENTS |
| `completion_status` | ja | `open`, `blocked`, `recorded` oder `evaluated` | Evaluation |
| `next_step` | ja | genau eine Folgeaktion | AGENTS |

Ein `RunRecord` darf auf einen Review- oder Evaluationseintrag verweisen. Es
kopiert keine verbindliche Regel in eine zweite Quelle.

## 3. Kandidatenstatus und Übergänge

Die folgenden Werte sind ein Pilotmodell. Sie werden nicht als neue globale
Statuswerte gesetzt.

| Status | Bedeutung | Erlaubter Übergang |
|---|---|---|
| `draft` | Auftrag/Objekt wird vorbereitet | `clarification_required` oder `scoped` |
| `clarification_required` | Frage, Gegenstand oder Abnahme fehlt | zurück zu `draft` |
| `scoped` | Ziel, Scope, Nicht-Scope und Funktion sind geklärt | `evidence_pending` |
| `evidence_pending` | zugelassene Capability wird ausgeführt | `evidence_ready` oder `blocked` |
| `evidence_ready` | Evidenz mit Auslassungen liegt vor | `finding_ready` |
| `finding_ready` | Beobachtung und Ableitung sind getrennt | `human_review` |
| `human_review` | Entscheidung des Menschen steht aus | `accepted`, `rejected`, `revise` oder `deferred` |
| `accepted` | Mensch hat Befund/Vorschlag akzeptiert | `recorded` |
| `rejected` | Mensch hat Befund/Vorschlag verworfen | `recorded` |
| `revise` | Nacharbeit oder Rückfrage erforderlich | `clarification_required` oder `scoped` |
| `deferred` | bewusst offen gelassen | `recorded` |
| `blocked` | Ausführung wegen Grenze oder fehlender Evidenz gestoppt | `clarification_required` oder `recorded` |
| `recorded` | Nachweis ist repository-basiert gesichert | `evaluated` nur bei eigenständigem Learning |
| `evaluated` | Evaluation hat Rückflussentscheidung erhalten | kein automatischer Regelübergang |

### 3.1 Pflichtübergänge

- `draft → scoped` nur bei vollständig bestätigtem WorkRequest;
- `scoped → evidence_pending` nur mit Capability, Scope und Datenklasse;
- `evidence_pending → evidence_ready` nur mit Quelle, tatsächlichem Scope und
  Toolingstatus;
- `evidence_ready → finding_ready` nur mit getrennten Beobachtungen;
- `finding_ready → human_review` nur mit sichtbaren Unsicherheiten und Optionen;
- `human_review → accepted/rejected/revise/deferred` nur durch Menschen;
- jeder Abschluss → `recorded` nur mit Repository-Pfad und genau einem nächsten
  Schritt;
- jeder Schreibversuch außerhalb eines separat freigegebenen Pfades →
  `blocked`.

## 4. Rollenmatrix für den Pilotvertrag

| Aktivität | Designer:in | Assistenz/Host | Development | Review/Governance |
|---|---|---|---|---|
| Frage und Bedeutung | verantwortlich | klärt sprachlich | nicht festlegen | auf Nachvollziehbarkeit prüfen |
| Scope und Nicht-Scope | bestätigt | schlägt Struktur vor | technisch abbilden | Grenzpassung prüfen |
| Capabilitywahl | muss nicht technisch wählen | verantwortlich innerhalb Policy | Adaptergrenze liefern | Tool-Fit prüfen |
| Evidenz | fachlich einordnen | sammeln/strukturieren | Fehlerstatus abbilden | Vollständigkeit prüfen |
| Ableitung | fachlich bewerten | begrenzt vorschlagen | nicht autonom entscheiden | Beleg prüfen |
| Decision | entscheidet/freigibt | vorbereitet | nicht ersetzen | Nachweis prüfen |
| Repository-Record | prüft Inhalt | vorbereitet | speichert technisch | Status/Rückfluss prüfen |
| Regelsetzung | gibt explizit frei | erkennt Kandidat | setzt nicht automatisch | Decision Log prüfen |

## 5. Eingebetteter Kandidatenvertrag

Die folgende YAML-Struktur ist nur Bestandteil dieses Pilots. Sie wird nicht als
Schema-Datei installiert.

```yaml
work_request:
  request_id: wr-example-001
  question: "Welche belegbaren visuellen Zustände sind am ausgewählten Gegenstand sichtbar?"
  subject: "konkreter, vom Menschen benannter Gegenstand"
  usage_level: fachliche_nutzung
  mode: pilot
  role: design
  action: analysieren
  scope: "ein benannter Gegenstand und seine sichtbaren Zustände"
  non_scope: "keine Figma-Änderung, keine Accessibility-Abnahme, kein Code"
  expected_result: "strukturierter Befund mit Evidenzstatus"
  acceptance: "Designer:in kann Befund und offene Grenze bewerten"
  human_owner: "Designer:in"
  status: scoped

evidence_packet:
  evidence_id: ep-example-001
  request_id: wr-example-001
  source: "konkrete Quelle/Referenz"
  capability_id: "capability.read-only.candidate"
  scope_read: "bestätigter Gegenstand"
  evidence_type: E2
  observations: []
  omissions: []
  completeness: partial
  tool_status: restricted
  captured_at: "YYYY-MM-DD"
  data_class: synthetisch

finding:
  finding_id: finding-example-001
  request_id: wr-example-001
  evidence_ids: [ep-example-001]
  observation: "sichtbare Beobachtung"
  inference: none
  impact: "mögliche fachliche Auswirkung"
  status: visible
  options: ["bestätigen", "nachfragen", "nicht ändern"]
  recommendation: null
  human_decision_id: null
  next_step: "menschliche Bewertung einholen"

decision:
  decision_id: decision-example-001
  finding_id: finding-example-001
  decision_owner: "Designer:in"
  options_considered: ["bestätigen", "nachfragen", "nicht ändern"]
  state: pending
  rationale: null
  scope: null
  affected_artifacts: []
  rule_candidate: no
  next_step: "menschliche Bewertung einholen"

run_record:
  run_id: run-example-001
  request_id: wr-example-001
  evidence_ids: [ep-example-001]
  finding_id: finding-example-001
  decision_id: decision-example-001
  status_history: [draft, scoped, evidence_pending, evidence_ready, finding_ready, human_review]
  human_involvement: "Auftrag und Scope bestätigt; Decision offen"
  repository_path: "reviews/s1-work-and-finding-contract-2026-10-20.md"
  open_items: ["konkrete Capability und Evidenz noch setupabhängig"]
  completion_status: open
  next_step: "menschliche Bewertung einholen"
```

## 6. Synthetische Validierungsfälle

### Fall A – ausreichend geklärter Gegenstand

**Eingang:** Eine Designerin fragt nach sichtbar belegbaren Zuständen eines
konkret benannten Gegenstands und schließt Figma-Schreiben, Code und
Accessibility-Abnahme aus.

**Erwarteter Ablauf:**

```text
draft → scoped → evidence_pending → evidence_ready
→ finding_ready → human_review
```

**Erwarteter Nachweis:** WorkRequest, EvidencePacket und Finding sind möglich;
`Decision.state = pending`, weil noch keine menschliche Bewertung vorliegt.

**Genau ein nächster Schritt:** Menschliche Bewertung einholen.

### Fall B – fehlender Scope

**Eingang:** „Prüfe die ganze Library“ ohne benannte Frage, Seite, Section,
Komponente oder Abnahme.

**Erwarteter Ablauf:**

```text
draft → clarification_required → blocked
```

**Warum:** Eine größere Toolabfrage darf den Scope nicht selbst definieren.

**Genau ein nächster Schritt:** Konkreten Gegenstand und Abnahme nachreichen.

### Fall C – Evidenz ohne menschliche Entscheidung

**Eingang:** Ein synthetisches EvidencePacket enthält eine sichtbare
Beobachtung, aber keine fachliche Bewertung.

**Erwarteter Ablauf:**

```text
scoped → evidence_pending → evidence_ready
→ finding_ready → human_review
```

**Nicht zulässig:** `accepted`, `recorded` als fachlich abgeschlossen oder
`Decision.status = bestätigt`.

**Genau ein nächster Schritt:** Menschliche Bewertung des Befunds einholen.

## 7. Quellenabgleich

| Vertragsprinzip | Quelle | Pilotstatus |
|---|---|---|
| Arbeitskontext vor Aktion | `AGENTS.md` | abgebildet, nicht neu gesetzt |
| PROMPT/AUSFÜHREN | D-018, D-030, Prompting Guide | Gate im WorkRequest/Übergangsmodell |
| Nutzungsebene und schlanker Kontext | D-025, `docs/README.md` | Pflichtfeld |
| Funktionsgenaues Toolrouting | D-026, Tooling Map | Capability-Feld und Stop |
| Evidenz vor Ableitung | D-014 als Entwurf, Workflows, Evaluation Framework | sichtbar als Pilotprinzip, nicht bestätigt |
| Regelkandidat und explizite Regelsetzung | D-015 als Entwurf, `AGENTS.md` | `rule_candidate`, keine automatische Übernahme |
| Delta-Nachweis | D-016 als Entwurf, `AGENTS.md` | RunRecord- und Evaluation-Pflicht |
| externe KI-/Datenfreigabe | D-031 | Datenklasse und Toolstatus |
| menschliche Rollen/User Stories | D-021/D-022, Rollenquelle | Rollenmatrix |
| Accessibility-Grenze | W3C-Research im dev-ready Plan | `not_assessed`/`not_proven` statt Abnahme |

## 8. Pilotgrenzen und bewusst nicht übernommen

- Keine neue kanonische Schema-Datei unter `docs/` oder `schemas/`;
- keine neuen globalen Statuswerte;
- keine Bestätigung von D-009 bis D-016;
- keine Decision-Log-Änderung außer dem Evaluation-Rückfluss;
- kein Figma-Aufruf und keine Capability-Freigabe;
- keine automatische Semantik-, Accessibility- oder Qualitätsabnahme;
- keine neue Runtime, API, Queue, SDK-, MCP- oder Plugin-Abhängigkeit;
- keine Wiki-Änderung;
- kein realer Designerfall und keine Kunden-/Projektinhalte.

## 9. S1-Ergebnis und offene Felder

**Ergebnis:** Die bestehende Governance lässt sich in fünf getrennte
Vertragsobjekte und einen kontrollierten Lebenszyklus übersetzen. Der Pilot
zeigt, dass fehlender Scope, fehlende Evidenz und fehlende menschliche
Entscheidung als unterschiedliche Stopps modellierbar sind.

**Offen:**

- Ob die fünf Objekte im Alltag tatsächlich weniger Aufwand erzeugen als die
  aktuelle freie Dokumentation;
- ob die vorgeschlagenen Felder für Designer:innen verständlich genug sind;
- welche konkrete Figma-Capability ein späterer S2-Slice nutzen darf;
- ob Markdown/YAML als Zwischenform genügt oder ein späteres JSON-Schema
  wirtschaftlich gerechtfertigt ist;
- welche D-009–D-016-Regelkandidaten nach Praxisvalidierung bestätigt werden.

**Delta-Nachweis:**

- **Neu gesichert:** Pilotvertrag, Status-/Übergangsmodell, Rollenmatrix,
  YAML-Kandidat und drei synthetische Fälle.
- **Geändert:** E-073 erhält den S1-Anschluss und den Pilotstatus.
- **Bewusst nicht übernommen:** kanonische Schema-Datei, neue Regel, Figma-
  Capability, Runtime, Wiki-Änderung und reale Designprüfung.
- **Weiterhin offen:** menschliche Bewertung des Vertrags und Entscheidung über
  S2/S3.

## 10. Menschliche Entscheidung und nächster Schritt

**Freigabe erteilt:** Der Pilotvertrag wird als ausreichende Grundlage für den
späteren S2-Slice weitergeführt.

Diese Freigabe setzt keine Figma-Capability, keine externe Integration und
keine Schreibberechtigung frei. S2 bleibt bis zur gesonderten Klärung und
Freigabe eines konkreten read-only-Figma-Integrationswegs gesperrt.

**Genau ein nächster Schritt:** Eine konkrete read-only-Figma-Capability mit
Scope, Berechtigung, Datenklasse und Abnahme für S2 festlegen.
