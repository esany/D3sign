# Tiefenaudit und Operationalisierung des Designer-Assistenzsystems

## Status und Transparenz

Dieser Befund ist ein repo-basierter Systementwicklungsbefund im Modus
`Umsetzen innerhalb bestätigter Regeln mit offenem Entscheidungsrückfluss`.
Er führt die bestätigte Konsolidierungsentscheidung D-037 aus. Einzelne
fachliche Statuswechsel bleiben davon getrennt und werden nicht stillschweigend
vorweggenommen.

| Feld | Befund |
|---|---|
| Ziel | Verborgene Anforderungen, Designerbedürfnisse, Statusbrüche und eine schlanke, deterministisch prüfbare Zielstruktur aus dem Repository herausarbeiten. |
| Gegenstand | `AGENTS.md`, `docs/`, bestätigte Decisions, Evaluation Log, bestehende Reviews, Git-Historie und GitHub-Issuebestand. |
| Nutzungsebene | `Systementwicklung` mit getrennt betrachteter fachlicher Designerwirkung |
| Modus | `Umsetzen innerhalb bestätigter Regeln` mit offenem Entscheidungsrückfluss |
| Rolle | `Architecture`, `Governance`, `Review`, mit Designfokus |
| Gelesene Funktionen | gezielte Repository-Suche, Quellenabgleich, Git-Historie, öffentlicher GitHub-Issue-Read-only-Abruf |
| Nicht ausgeführt | kein Figma-Aufruf, keine Figma-/Token-/Komponentenänderung, keine Wiki-Pflege, keine neue Runtime, keine Issue-Mutation |
| Ergebnisstatus | `freigegeben zur Konsolidierung`; Einzel- und Regelstatus bleiben dort offen, wo eine eigene fachliche Entscheidung erforderlich ist |

## 1. Kernbefund

Das Repository beschreibt bereits die richtige Systemidee: keine autonome
Designmaschine und keine generische Agentenplattform, sondern einen
kontrollierten Arbeitsvertrag zwischen Designer:in, Assistenz, begrenzter
Design-Evidenz und Repository.

Der tragfähige Kern lautet:

```text
Designerfrage
  → Scope und Abnahme klären
  → kleinste passende Quelle und Capability wählen
  → Evidenz mit Auslassungen sichern
  → fachlich lesbaren Befund vorbereiten
  → Designer:in bewertet und entscheidet
  → Status, Entscheidung und nächster Schritt repo-first sichern
```

Die Hauptschwäche liegt nicht in fehlenden weiteren Tools. Sie liegt darin,
dass bereits vorhandene Regeln und Anforderungen noch nicht überall als ein
einziger ausführbarer Pfad gelten:

1. D-009 bis D-016 sind formal `Entwurf`, werden aber praktisch als Regeln
   referenziert.
2. D-019 und E-071 bilden einen sichtbaren Statuskonflikt für die Wiki-Pflege.
3. Base-Template-Stufen, S0–S2-Reviews und historische Figma-Piloten werden
   nebeneinander gelesen, obwohl sie unterschiedliche Reife- und
   Autoritätsstufen haben.
4. Der Toggle-Test erzeugte mehrere überlappende Review-Artefakte, statt einen
   einzigen fachlich entscheidungsfähigen Realfall zu liefern.
5. Die S1-Objekte sind als Pilotvertrag beschrieben, aber ihr Einsatz als
   verbindlicher Arbeitsvertrag ist noch nicht entschieden.

Damit fehlt weniger Wissen als eine scharf gesetzte Status-, Quellen- und
Übergangslogik.

## 2. Verborgene Anforderungen aus dem Kontext

### 2.1 Designerrolle

Der Designer ist fachlicher Eigentümer von Zweck, Bedeutung, Priorität,
visueller Systemlogik, Zuständen, Accessibility, Qualität und Abnahme. Er ist
kein technischer Operator und darf nicht gezwungen werden, Node-IDs, MCP-
Funktionen, API-Parameter oder unaufgelöste Toolgrenzen zu interpretieren.

### 2.2 Designer-Pains

Aus Rollen/User Stories, Audits und Reviews sind folgende konkrete Schmerzen
belegt:

- relevante Informationen liegen über Prosa, historische Pfade und Reviews
  verteilt;
- Status und praktische Nutzung fallen auseinander;
- Toolantworten werden zu schnell als semantische Aussage gelesen;
- eine reine Variablen- oder Strukturauflistung hilft nicht bei der fachlichen
  Entscheidung;
- fehlender Kontext wird durch zusätzliche Tabellen und Toolaufrufe kompensiert;
- neue Regeln und alte Regeln können parallel weiterleben;
- der Chat droht zum einzigen Ort zu werden, an dem Bedeutung und Anschluss
  verständlich sind;
- Figma-Dokumentation kann formal vollständig wirken, ohne Vertrauen,
  Unterstützung und Verlässlichkeit herzustellen.

### 2.3 Designerbedürfnisse

Der Designer braucht vor einer Bewertung:

1. die fachliche Frage in verständlicher Sprache;
2. den konkreten Gegenstand und seinen tatsächlichen Scope;
3. die Bedeutung des geprüften Zustands oder Elements;
4. die aktuelle visuelle oder strukturelle Ausprägung;
5. die bestehende semantische Vergleichsbasis;
6. die funktionale Konsequenz einer Zuweisung oder Abweichung;
7. eine klare Trennung zwischen belegt, abgeleitet und offen;
8. genau eine nächste Entscheidung oder Handlung.

Er braucht keine Rohdatenansicht, in der er die fachliche Bedeutung aus
Variablennamen, Node-IDs oder Toolstatus rekonstruieren muss.

### 2.4 Zentrale Arbeitsteilung

| Mensch | Assistenz | Quelle/Tool |
|---|---|---|
| Frage, Zweck, Bedeutung, Priorität, Qualitätsurteil, Decision und Abnahme | Scope klären, kleinste Capability wählen, Evidenz strukturieren, Unsicherheit markieren, Optionen vorbereiten | zeigt nur den tatsächlich zugänglichen Design- oder Repository-Stand |

Technische Ausführbarkeit verleiht keine fachliche Entscheidungsbefugnis.

## 3. Bestehende Schätze, die erhalten werden müssen

Die folgenden Strukturen sind bereits belastbare Bausteine und dürfen nicht
durch eine neue generische Architektur ersetzt werden:

- `AGENTS.md` als unmittelbarer Arbeitsvertrag;
- `docs/README.md` als Quellen- und Funktionsrouting;
- bestätigte Decisions D-017, D-018, D-025, D-026, D-028, D-029 und D-031 bis
  D-036;
- `docs/operations/workflows.md` mit kleinstem Toolzugriff, Stopps und
  Token-/Iterationsökonomie;
- `docs/governance/base-template.md` mit Bausteinvertrag,
  Entscheidungsrechten und Test-zu-Evaluation-Rückfluss;
- `docs/foundations/design-principles.md` und `standards.md` mit Bedeutung
  vor Ausprägung, Wiederverwendung, Rollen-Tokens und kleinen Migrationen;
- `docs/governance/role-needs-and-user-stories.md` als fachliche
  Anforderungsquelle;
- S1 mit `WorkRequest`, `EvidencePacket`, `Finding`, `Decision` und
  `RunRecord` als bereits ausgearbeiteter, aber noch nicht kanonischer
  Kandidatenvertrag;
- Evaluation Log als Nachweis- und Lernrückfluss;
- Wiki-Freeze aus E-071 als bewusste Pflegegrenze.

Diese Elemente bilden den Bestand. Die Aufgabe ist Statusklärung und
Operationalisierung, nicht Neuerfindung.

## 4. Überholte, doppelte und verwaiste Pfade

| Pfad | Befund | Behandlung im Audit |
|---|---|---|
| D-009 bis D-016 | Als Entwurf geführt, aber praktisch mehrfach referenziert | Statusdrift als zentrale Architekturentscheidung markieren; keine automatische Bestätigung |
| D-019 / E-071 | Bestätigte Wiki-Entscheidung und aktueller vorläufiger Freeze nicht abschließend reconciliert | Konflikt sichtbar halten; keine Wiki-Reaktivierung |
| Base Template v0.1/v0.2/v0.3 | Historische Entwicklungsstaffelung neben späterem S0–S6-Zielbild | nicht als aktuelle Lieferroadmap behandeln |
| `s2-toggle-variable-read` / `s2-toggle-variant-audit` | Überlappende S2-Befunde; Rohwerte und Variantstruktur wurden getrennt dokumentiert, aber noch nicht in einen entscheidungsfähigen Realfall überführt | als historische Evidenz behalten; nicht als allgemeines Auditmuster weiterverbreiten |
| S2 Capability-Readiness | Technischer Kandidat mit offenem Freigabe-/Scope-Status | nicht als allgemeine Capability-Registry oder aktive Produktfunktion behandeln |
| Wiki-Detailseiten | Bestand vorhanden, Pflege pausiert | erhalten, nicht routinemäßig synchronisieren |
| GitHub-Issues | Read-only-Abgleich am 2026-10-20 ergab keine offenen Issues; einziger Treffer war der gemergte PR #1 | keine Schließung, kein Nachfolger, keine künstliche Issue-Struktur |

Es wurde nichts gelöscht. Vor einer späteren Kürzung muss jeweils Zweck,
Schutzwirkung, Zielquelle und Linkzuordnung belegt werden.

## 5. Zielarchitektur für verlässliche Praxis

Die bestehende S1-Struktur wird als Kandidat genutzt. Es wird kein neuer
paralleler Vertrag eingeführt.

### Gate 0 – Arbeitsauftrag reif

Pflichtangaben: Frage, Gegenstand, Nutzungsebene, Modus, Rolle, Aktion, Scope,
Nicht-Scope, Ergebnis und Abnahme.

**Stopp:** Wenn Frage, Gegenstand oder Abnahme fehlen.

### Gate 1 – Quelle und Capability passend

Die Assistenz wählt die kleinste passende Quelle und Funktion. Sie nennt den
tatsächlichen Scope, erwartete Rückgabe und Grenzen.

**Stopp:** Wenn die Funktion die bestätigte Frage nicht beantworten kann oder
eine breitere Inventarisierung nur aus Gewohnheit entstehen würde.

### Gate 2 – Evidenz belastbar

`EvidencePacket` enthält Quelle, Capability, tatsächlichen Lesescope,
Beobachtungen, Auslassungen, Datenklasse, Toolstatus und Vollständigkeit.

**Stopp:** Wenn Auslassungen nicht sichtbar sind oder technische Evidenz als
fachliche Bedeutung gelesen werden müsste.

### Gate 3 – Befund entscheidungsfähig

`Finding` trennt Beobachtung, begrenzte Ableitung, mögliche Auswirkung,
Optionen, Unsicherheit und genau einen nächsten Schritt. Die Ausgabe beginnt
mit der fachlichen Bedeutung und zeigt technische Details nur dort, wo sie die
Entscheidung unterstützen.

**Stopp:** Wenn der Designer die Bedeutung aus Rohdaten rekonstruieren müsste.

### Gate 4 – Menschliche Decision

Der Designer bestätigt, verwirft, priorisiert, beauftragt Nacharbeit oder lässt
den Punkt offen. Die Assistenz empfiehlt höchstens; sie setzt keine neue Regel.

**Stopp:** Jede automatische fachliche Freigabe, semantische Umdeutung oder
Accessibility-Abnahme.

### Gate 5 – Repository-Rückfluss

`RunRecord` verweist auf Befund, Status, menschliche Beteiligung,
Entscheidung/Offenheit, Repository-Pfad und genau einen nächsten Schritt.

**Stopp:** Wenn der Rückfluss eine doppelte Regelquelle, unklare Statuswerte
oder einen neuen unverbundenen Dokumentationspfad erzeugen würde.

## 6. Dev-ready Anforderungen und Akzeptanzkriterien

Diese Anforderungen sind aus dem Bestand abgeleitet und bleiben bis zur
menschlichen Entscheidung ein Vorschlag.

| ID | Anforderung | Deterministisches Akzeptanzkriterium | Quelle |
|---|---|---|---|
| REQ-01 | Jeder Lauf beginnt mit einer fachlichen Frage und einem konkreten Gegenstand. | Kein Lauf startet ohne Frage, Quelle, Scope und Abnahme. | `AGENTS.md`, Prompting Guide |
| REQ-02 | Nutzungsebene und Rolle werden getrennt ausgewiesen. | Jeder Abschluss enthält Fachliche Nutzung/Systementwicklung, Rolle und getrennte Abnahme. | `AGENTS.md`, D-025 |
| REQ-03 | Der kleinste passende Zugriff wird gewählt. | Der Befund nennt Funktion, Scope und bewusst nicht gelesene Bereiche; ein Vollinventar braucht einen belegten Trigger. | Workflows, D-017, D-026 |
| REQ-04 | Technische Evidenz und fachliche Bedeutung bleiben getrennt. | Jeder Befund hat getrennte Felder für Beobachtung, Ableitung, Unsicherheit und nicht bewertete Aspekte. | D-014, D-028, D-029 |
| REQ-05 | Der Designer kann ohne Toolsyntax entscheiden. | Die Ergebnisdarstellung beantwortet zuerst Zweck, Zustand, Rolle, Auswirkung und offene Entscheidung; Node-/API-Details sind nur Nachweis. | Role Needs, Standards |
| REQ-06 | Semantische Rollen werden vor konkreten Werten geprüft. | Ein Tokenname oder Hexwert wird nie allein als semantisch korrekt bewertet. | Design Principles, Standards |
| REQ-07 | S1-Objekte bilden den einzigen Kandidatenvertrag. | Neue Befunde ordnen sich `WorkRequest`, `EvidencePacket`, `Finding`, `Decision`, `RunRecord` zu oder begründen eine Abweichung. | S1-Pilotvertrag |
| REQ-08 | Stopps sind ausführbar. | Fehlende Quelle, unpassende Capability, unvollständige Evidenz und fehlende menschliche Entscheidung führen zu einem sichtbaren Stoppstatus. | AGENTS, Workflows |
| REQ-09 | Menschliche Entscheidung ist ein eigener Übergang. | Kein `accepted`, `bestätigt` oder Regelstatus entsteht ohne benannten menschlichen Owner. | Base Template, S1 |
| REQ-10 | Jede Regel hat eine verbindliche Quelle. | Eine neue oder geänderte Regel wird genau einer `docs/`-Quelle zugeordnet; Reviews bleiben Vorschläge. | `docs/README.md`, Checklists |
| REQ-11 | Historische und aktuelle Pfade sind unterscheidbar. | Jede überholte, pausierte oder abgelöste Struktur ist mit Status und Ziel-/Nachfolgerquelle gekennzeichnet. | S0-Reconciliation, E-071 |
| REQ-12 | Issue- und Repository-Rückfluss bleibt nachvollziehbar. | Ein geschlossenes Issue verweist auf Erledigung oder Nachfolger; ohne belegte Ablösung erfolgt keine Schließung. | Prompt, AGENTS, Repository-Praxis |
| REQ-13 | Die Pflege bleibt lean. | Kein neuer Pflichtprozess, keine doppelte Checkliste und kein paralleles Auditformat ohne belegten wiederkehrenden Nutzen. | D-017, Checklists |
| REQ-14 | Evaluation prüft Nutzen und nicht nur Form. | Ein Evaluationsbefund weist Zielbeitrag, Aufwand, Pflegekosten, Grenzen, Nichtstun-Folge und genau einen nächsten Schritt aus. | Evaluation Framework, D-029 |

## 7. Deterministische Prüfstruktur

Die Architektur ist erst dev-ready, wenn folgende Prüfungen maschinell oder
regelbasiert möglich sind:

### Strukturprüfungen

- Pflichtfelder des Arbeitsauftrags vorhanden;
- Statuswert aus zulässigem Vokabular;
- Übergang entspricht dem zulässigen Lebenszyklus;
- Quelle und Repository-Pfad vorhanden;
- genau ein nächster Schritt;
- `Nicht geprüft` nicht leer, wenn die Prüfung begrenzt war.

### Quellenprüfungen

- Links und Abschnittsanker technisch gültig;
- Regel verweist auf genau eine verbindliche Quelle;
- Review verweist auf seine operative Zielquelle;
- historische Quelle bleibt erreichbar, wenn sie als Ablösung referenziert wird.

### Governanceprüfungen

- neue Regel nicht automatisch aus einem Test übernommen;
- menschlicher Owner bei Decision vorhanden;
- Figma-/Tooling-Evidenz nicht als Semantik- oder Accessibility-Abnahme
  ausgezeichnet;
- Schreiben außerhalb bestätigter Grenzen blockiert;
- Issue-Schließung nur mit Beleg oder Nachfolger.

### Menschliche Prüfung

Deterministische Checks ersetzen nicht die fachliche Bewertung von Bedeutung,
Priorität, visueller Qualität, Nutzerwirkung oder Designintention. Diese
Grenze ist Teil des Systems und kein fehlender Automatisierungsgrad.

## 8. Issue- und Artefakt-Disposition

Der öffentliche Issue-Abgleich des Ziel-Repositories wurde read-only
durchgeführt. Es existieren keine offenen Issues. PR #1 ist geschlossen und
gemergt; er dokumentiert bereits die Architekturübernahme und benötigt keinen
Nachfolger.

Deshalb wurden keine Issues geschlossen, neu angelegt oder umetikettiert.
Diese Entscheidung ist bewusst und entspricht der Regel, keine externe
Mutation ohne belegten Arbeitsbedarf zu erzeugen.

Die überlappenden Toggle-Reviews bleiben als historische Nachweise erhalten.
Sie werden nicht als kanonische Auditstruktur übernommen. Eine spätere
Konsolidierung erfordert eine eigene, begrenzte Entscheidung über Quellen-
und Funktionszuordnung.

## 9. Repository-Rückfluss

Neu gesichert wird dieser konsolidierte Tiefenaudit als Vorschlag. Der
Evaluation Log erhält einen Nachweis über:

- die rekonstruierten Designeranforderungen;
- die Status- und Quellenbrüche;
- den deterministischen Gate-Vorschlag;
- den Issue-Abgleich ohne Mutation;
- die bewusst nicht übernommene generische Auditstruktur;
- den offenen menschlichen Entscheid.

Nicht verändert werden bestätigte Decisions, `AGENTS.md`, Wiki-Detailseiten,
Figma, Tokens, Komponenten und externe Toolkonfigurationen.

## 10. Freigabe und aktueller Anschluss

Die Gate-basierte Konsolidierungsgrundlage ist durch D-037 bestätigt. Die
Anforderungen und Akzeptanzkriterien sind damit als Arbeitsgrundlage
freigegeben; einzelne Decision-Status bleiben offen, wenn sie eine eigene
fachliche Begründung oder Ablösung benötigen.

## 11. Status- und Quellenbereinigung nach Ausführung

Die Arbeitsstandmarkierungen wurden nur dort ergänzt, wo der spätere
Repository-Stand den Status eindeutig einordnet:

- S0-Reconciliation bleibt historischer Begründungsnachweis;
- der S2-Capability-Readiness-Text bleibt ein historischer Kandidat und kein
  aktiver Arbeitsweg;
- beide Toggle-S2-Dateien bleiben historische Evidenz und werden nicht als
  kanonisches Auditformat fortgeführt;
- der Dev-ready Plan bleibt Vorschlagsquelle, seine S0–S2-Pfade werden aber
  nicht als aktuelle Ausführungsroadmap behandelt.

Die Decision-Status D-009 bis D-016 sowie D-019 wurden nicht verändert. Ihre
Disposition bleibt eine menschliche Entscheidung. Die Wiki bleibt im
vorläufigen Freeze aus E-071. Der Issue-Abgleich ergab weiterhin keine offenen
Issues; es wurde keine externe Mutation ausgeführt.

## 12. Einzel-Dispositionen für D-009 bis D-016

Die folgende Matrix ist durch D-037 als Arbeitsgrundlage freigegeben. Sie
ändert die Einzelstatus im Decision Log noch nicht.

| Decision | Aktuelle Einordnung | Tatsächliche Zielquelle | Vorgeschlagene Disposition | Begründung und Folge |
|---|---|---|---|---|
| D-009 Rollen | Entwurf, praktisch in `AGENTS.md`, Prompting Guide und Role Needs verwendet | `AGENTS.md` plus `docs/governance/role-needs-and-user-stories.md` | `zusammenführen` | Die Schutzwirkung ist aktiv; die Decision darf nicht parallel als eigenständige Regel fortbestehen. Einzelstatus bleibt bis zur Statusentscheidung sichtbar. |
| D-010 Transparenz | Entwurf, praktisch in Transparenzpflicht, Base Template und Checklists verwendet | `AGENTS.md`, `docs/governance/base-template.md`, `docs/governance/evaluation-framework.md` | `zusammenführen` | Die Pflichtfelder und Rollenklärung existieren bereits; der offene Status erzeugt Statusdrift. |
| D-011 Library-Grundbaustein | Entwurf, als generischer Foundation-Rahmen weiterhin relevant | `docs/governance/base-template.md`, `docs/foundations/` | `als Entwurf offen halten` | Der Grundbaustein bleibt Vorschlags-/Foundationmaterial und ist kein konkretes Projektziel. |
| D-012 Ausbaustufen | Entwurf mit historischer v0.1/v0.2/v0.3-Staffelung | `reviews/designer-assistance-dev-plan-2026-10-20.md` und E-074/E-075 | `historisch markieren` | Die alte Roadmap darf nicht parallel als aktuelle Lieferplanung gelesen werden. |
| D-013 Toolwahl | Entwurf, praktisch in `AGENTS.md`, Prompting Guide und Tooling Map verwendet | `AGENTS.md`, `docs/operations/prompting-guide.md`, `docs/tooling/tooling-map.md` | `zusammenführen` | Toolwahl und Scope sind bereits ausführbar geregelt; die Capability bleibt fallbezogen. |
| D-014 Evidenzstatus | Entwurf, praktisch im Evaluation Framework und in jedem neueren Befund verwendet | `AGENTS.md`, `docs/governance/evaluation-framework.md`, `docs/operations/workflows.md` | `zusammenführen` | Evidenz vor Ableitung ist aktive Arbeitslogik; der Status muss mit der Quelle synchronisiert werden. |
| D-015 Regelkandidaten | Entwurf, praktisch über `REGEL SETZEN` und AGENTS-Governance verwendet | `AGENTS.md`, `docs/governance/decisions.md` | `zusammenführen` | Die Schutzwirkung bleibt erhalten; automatische Regelsetzung bleibt ausgeschlossen. |
| D-016 Delta-Nachweis | Entwurf, praktisch durch `Status sichern` und Evaluation angewendet | `AGENTS.md`, `docs/governance/evaluation-log.md` | `zusammenführen` | Der Delta-Nachweis ist Teil des bestehenden Rückflusses; keine zusätzliche Statusablage nötig. |

Für D-009, D-010 und D-013 bis D-016 ist der nächste fachliche Schritt eine
gebündelte Statusentscheidung über Zusammenführung und Ablösung der
historischen Einzelentries. D-011 bleibt bis zur gesonderten Foundation-
Bewertung offen. D-012 wird als historische Roadmap markiert, ohne die
Entwicklungsgeschichte zu löschen.
