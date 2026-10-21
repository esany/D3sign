# Decisions

Status: Laufend

Dieses Entscheidungslog hält wichtige Annahmen, Entscheidungen, Begründungen,
Alternativen und offene Punkte fest.

## Pflege und Status

Ein Eintrag ist erforderlich bei einer folgenreichen Entscheidung, Freigabe,
Ausnahme, Ablehnung oder Ablösung einer Regel. Routineanwendungen bestätigter
Regeln werden nicht einzeln erfasst.

Zulässige Statuswerte: `Entwurf`, `bestätigt`, `abgelöst`, `verworfen`.
Neue Einträge enthalten mindestens Datum, Status, Entscheidung, Begründung,
Geltungsbereich und betroffene Artefakte. Bei Statuswechsel wird der bestehende
Eintrag fortgeschrieben; kein doppelter Eintrag für dieselbe Entscheidung.

## Übersicht

| ID | Status | Geltungsbereich | Kurzentscheidung |
|---|---|---|---|
| D-001 | Entwurf | Governance- und Template-Struktur | Base Template und Project Template werden getrennt geführt. |
| D-002 | Entwurf | Mensch–Maschine-Arbeitsteilung | Entscheidungsrechte steuern schreibende und standardverändernde Aktionen. |
| D-003 | Entwurf | Entscheidungslog | Folgenreiche Entscheidungen werden fortlaufend und statusbasiert gepflegt. |
| D-004 | Entwurf | Menschliche Vermittlung | Eine lebendige Wiki erklärt Entwicklung, Steuerung und Quellen nach menschlicher Informationslogik. |
| D-005 | Entwurf | Evaluation | Wiederkehrende Prüfung verbindet Design Ops, Lean, Operationalisierbarkeit und menschliche Verständlichkeit. |
| D-006 | Entwurf | Figma-Kontext | Repository, Figma, Code und Wiki tragen getrennte, verlinkte Kontextverantwortung; v0.2 prüft dies read-only. |
| D-007 | abgelöst | Entwicklungsmodus | Der frühere projektnahe Vertikalschnitt wird durch den generischen Library-Fokus von D-011 abgelöst. |
| D-008 | Entwurf | KI-Tooling-Tests | Tests bleiben isoliert und ergebnisoffen; Übernahme ins Zielsystem braucht menschliche Freigabe. |
| D-009 | abgelöst | Arbeitsrollen | Durch `AGENTS.md` und die zuständigen Governance-/Rollenquellen abgelöst; Rollen steuern Perspektive und Output, nicht Entscheidungsbefugnis. |
| D-010 | abgelöst | Transparenz und Selbsterklärung | Durch `AGENTS.md`, Base Template, Checklists und Evaluation abgelöst; Automatik, menschliche Steuerung und offene Entscheidungen bleiben getrennt ausgewiesen. |
| D-011 | Entwurf | Generischer Design-System-Grundbaustein | v0.1 fokussiert Library-Regeln und isolierte Tooling-Tests; Projektkits und Entwurfsdateien bleiben Zielbild. |
| D-012 | Entwurf | Ausbaustufen | v0.1 bleibt Regelgrundlage; v0.2 prüft read-only Tooling mit externen Testfixtures. |
| D-013 | abgelöst | Agentenverantwortung für Toolwahl und Prompting | Durch `AGENTS.md`, Prompting Guide und Tooling Map abgelöst; der Agent wählt die passendste Funktion und weist Einschränkungen aus. |
| D-014 | abgelöst | Evidenz vor fachlicher Ableitung | Durch `AGENTS.md`, Evaluation Framework und Workflows abgelöst; Evidenzstatus und Grenzen stehen vor fachlichen Ableitungen. |
| D-015 | abgelöst | Regelkandidaten und explizite Regelsetzung | Durch `AGENTS.md` und Decision Log abgelöst; `REGEL SETZEN` bleibt die ausdrückliche menschliche Anweisung. |
| D-016 | abgelöst | Delta-Nachweis bei „Status sichern“ | Durch `AGENTS.md` und Evaluation Log abgelöst; jeder Sicherungslauf weist das konkrete Delta aus. |
| D-017 | bestätigt | Aktive Ziel-, Lean- und Proportionalitätsprüfung | Der Agent prüft vor Zustimmung oder Erweiterung aktiv Zielbeitrag, Wiederverwendung, Leanheit, Operationalisierbarkeit und Tokenaufwand und weist auf Overhead oder Zielabweichung hin. |
| D-018 | bestätigt | Menschlich verständlicher `PROMPT`-/`AUSFÜHREN`-Ablauf | `PROMPT` klärt Auftrag, Scope, Toolwahl und Grenzen; erst `AUSFÜHREN` startet die bestätigte Aktion. |
| D-019 | bestätigt | Menschenzentrierte Wiki und `WIKI PRÜFEN` | Die Wiki vermittelt ohne Vorwissen; der Befehl prüft regelmäßig Informationsarchitektur, Verständlichkeit, Arbeitsteilung und kognitive Last. |
| D-021 | bestätigt | Rollen, User Stories und progressive Wiki-Vermittlung | Rollenbedürfnisse gehören in die Governance; die Wiki vermittelt sie selektiv über Orientierung, Entscheidungshilfe und Detailkontext. |
| D-022 | bestätigt | Technisch, agentisch und informationell versierter Review | `Review` prüft zusätzlich Tooling, agentische Arbeitsteilung, Informationsarchitektur, Wissensvermittlung, Zielpassung und praxistaugliche Leanheit. |
| D-023 | bestätigt | Zielgruppen- und Schichtpassung von Dokumentationsinhalten | Operative Dateien bleiben maschinenorientiert; erklärende und didaktische Inhalte gehören in die Wiki. Jede Änderung prüft Zielgruppe, Zweck, Inhaltstyp und Nicht-Scope. |
| D-024 | bestätigt | Mehrstufige Wiki-Link- und Quellenprüfung | Linktests trennen technische Gültigkeit, strukturelle Pflichtfeldabdeckung und semantische Zielpassung; der Testumfang wird vollständig ausgewiesen. |
| D-025 | bestätigt | Nutzungsebene und schlanke Agenten-Einstiegskarte | Fachliche Nutzung und Systementwicklung werden getrennt ausgewiesen; Details liegen genau einmal in der zuständigen Quelle. |
| D-026 | bestätigt | Übernahmeart und funktionsgenaues Toolrouting | Übernahmeart und Erhaltungsziel werden vor der Toolwahl geklärt; Ersatzwege benötigen eine neue Auswahl. |
| D-027 | Entwurf | Pflege- und Statussynchronisation | Praktisch verwendete Regelkandidaten werden zentral sichtbar gemacht und vor einer verbindlichen Nutzung statusgeprüft. |
| D-028 | bestätigt | Externe Wissens-MCPs | Externe Wissens-MCPs zählen nur bei passenden, quellenzuordenbaren Antworttreffern als Evidenz; Erreichbarkeit allein reicht nicht. |
| D-029 | bestätigt | Entwicklungspriorisierung | Systementwicklung ordnet Maßnahmen nach Nutzen, Aufwand und Nichtstun-Folge ein; nur ein begründeter Kandidat oder unmittelbarer Nutzen rechtfertigt eine weitere Iteration. |
| D-030 | bestätigt | Ausführungsfreigabe in `PROMPT` | Jeder ausführungsbereite `PROMPT` endet mit einer konkreten `AUSFÜHREN`-Abschlusszeile. |
| D-031 | bestätigt | KI-gestützte externe Dienste im Gestaltungskontext | Einsatz nur innerhalb der dokumentierten ISMS-, Daten-, Lizenz- und Freigabegrenzen. |
| D-032 | bestätigt | Bewertung neuer Fundstücke | Fundstücke werden auf Mehrwert, Integrationsgrad und übertragbares Wissen geprüft, nicht nur auf eine Toolaufnahme. |
| D-033 | bestätigt | Übernahme von Wissen aus externen Skills | Wiederverwendbare Ablaufprinzipien werden selektiv übernommen; fremde Skill-Sammlungen werden dadurch nicht automatisch installiert oder freigegeben. |
| D-034 | bestätigt | Erweiterungsfähigkeit von Komponentenverträgen | Das Base Template standardisiert keine Projektvarianten vorab, muss aber spätere Erweiterungs- und Migrationsarten im Vertrag unterscheidbar machen. |
| D-035 | bestätigt | Vertrauensfähige Figma-Komponentendokumentation | Figma-Komponentendokumentation gilt nur als erfüllt, wenn sie Vertrauen, Unterstützung und Verlässlichkeit praktisch herstellt; formale Objektvollständigkeit reicht nicht. |
| D-036 | bestätigt | Trennung von Komponenten-Erstellung, -Prüfung und -Dokumentation | Ein Komponentenauftrag muss vor Ausführung unterscheiden, ob eine Komponente erstellt, geprüft, dokumentiert oder in definierter Reihenfolge kombiniert wird. |
| D-037 | bestätigt | Quellen-, Status- und Pfadkonsolidierung | Die freigegebene Status-/Quellenmatrix und der Gate-basierte Arbeitsvertrag bilden die verbindliche Konsolidierungsgrundlage; offene Einzelentscheidungen werden separat geklärt, historische Pfade nicht als aktuelle Ausführungswege behandelt. |

**Hinweis zur Nummerierung:** D-020 ist nicht vergeben; im geprüften
Projektbestand ist keine historische Decision oder Referenz dazu dokumentiert.

## Regelkandidaten und Statusabgleich

Diese Übersicht macht sichtbar, wo Entscheidungsstatus und praktische Nutzung
auseinanderfallen. `Entwurf` bedeutet hier ausdrücklich: noch keine
verbindliche Regelsetzung.

| Regelkandidat oder Decision | Dokumentierter Status | Praktisch referenziert in | Nächste Klärung |
|---|---|---|---|
| D-009 | abgelöst | `AGENTS.md`, Prompting Guide, Role Needs | Keine separate Regelsetzung; Schutzwirkung ist in den Zielquellen verankert. |
| D-010 | abgelöst | `AGENTS.md`, Base Template, Checklists, Evaluation | Keine separate Regelsetzung; Transparenzpflicht ist in den Zielquellen verankert. |
| D-013 | abgelöst | `AGENTS.md`, Prompting Guide, Tooling Map | Keine separate Regelsetzung; Toolwahl bleibt fallbezogen und begrenzt. |
| D-014 | abgelöst | `AGENTS.md`, Evaluation Framework, Workflows | Keine separate Regelsetzung; Evidenzreihenfolge ist in den Zielquellen verankert. |
| D-015 | abgelöst | `AGENTS.md`, Decision Log | Keine separate Regelsetzung; `REGEL SETZEN` bleibt erhalten. |
| D-016 | abgelöst | `AGENTS.md`, Evaluation Log | Keine separate Regelsetzung; Delta-Nachweis bleibt im Sicherungsabschluss erhalten. |
| Evaluation-Log-ID-Abgleich | Regelkandidat | E-038 | Read-only-Test erfolgreich; menschlich entscheiden, ob übernehmen, als Pilot fortführen oder verwerfen. |
| Status-Sinnabgleich | Regelkandidat | E-039 | An einem folgenreichen Sicherungslauf prüfen; erst danach Übernahme, Pilot oder Verwerfung entscheiden. |
| Kontextstart und Wiederaufnahme | Regelkandidat | E-041, E-045 | An vier Startarten auf Kontextverlust, Auffindbarkeit, Ebenentrennung und Aufwand prüfen; erst danach Übernahme, Pilot oder Verwerfung entscheiden. |
| `START CHAT`: Kontextstart mit aufgabenbezogener Toolbereitschaft | Regelkandidat | E-042, E-045 | An vier echten Starts prüfen: Kurzcode übernimmt Kontext selbst, Ebenen sind passend getrennt, nur benötigtes Tooling geprüft; danach übernehmen, fortführen oder verwerfen. |
| Testkarte für Kontext-Shortcuts | Regelkandidat | E-043, E-045 | Den Baustein in vier realen Startarten anwenden; nur bei belegtem Nutzen und ohne Zusatzlast über Übernahme entscheiden. |
| Semantischer Button-Vertrag mit Zustands- und Support-Matrix | Regelkandidat | E-055, E-056, E-057 | Eine konkrete Button-Variante als Aktion, Toggle oder Menu Button klassifizieren und daran prüfen, ob der Vertrag projektspezifisch bleibt oder als Foundation-Regelkandidat weitergeführt wird. |
| Ebenentrennung für Figma-Pilotdokumentation | Regelkandidat | E-058 | An der V2-Button-Pilotfläche prüfen, ob `Bausteinfläche` und `Pilotannotation` getrennt werden sollen; erst danach als Template-Struktur übernehmen, fortführen oder verwerfen. |
| Schrittweiser Figma-Pilotaufbau | Regelkandidat | E-058 | Beim nächsten Figma-Piloten prüfen, ob Wrapper zuerst, kleiner Schreibscope und direkte Screenshot-/Metadatenvalidierung als verbindlicher Tooling-Ablauf taugen. |
| Scope- und Abdeckungsprüfung für Figma-Lesefunktionen | Regelkandidat | E-063, Workflows, Tooling Map | An einer zweiten mehrseitigen Datei prüfen, ob Share-Link-Anker, gewünschter Scope und die Abdeckungsgrade von Metadaten- und Root-Inventar getrennt und verständlich bleiben. |
| KI-orientiertes Figma-Inventar | Regelkandidat | E-065, Workflows, Tooling Map, Checklists | An einem weiteren Fall prüfen, ob der Inventar-Trigger (fehlender direkter Kontext oder ausdrücklich beauftragte Übersicht) die nächste Entscheidung erleichtert, ohne eine Standardphase, neue Dateitaxonomie oder Library-Annahme zu erzeugen. |
| D-036 | bestätigt | E-067, E-068, D-035, Standards, Checklists, Prompting Guide | Beim nächsten Figma-Komponentenauftrag anwenden: Erstellung, Prüfung und Dokumentation getrennt ausweisen; Dokumentation ersetzt keine Komponente. |
| Aufbaustufe und Generation im Figma-Komponentenpilot trennen | Regelkandidat | E-068 | Beim nächsten Button-/Figma-Durchlauf prüfen, ob der Prompt ausdrücklich zwischen fachlicher Aufbaustufe und konkreter Figma-Generation unterscheidet und dadurch Iterationsdrift verhindert. |
| Prüfgate für reinen Figma-Komponentenbau | Regelkandidat | E-069, D-036, Checklists | Beim nächsten reinen Button-Komponentenbau anwenden: Auftragstyp, Komponenten-Gegenstand, Anatomy, Varianten, Properties, Overrides, Scope und Sichtbarkeit prüfen; danach Regelsetzung, Überarbeitung oder Verwerfung entscheiden. |

Die Tabelle ist ein Pflege- und Transparenznachweis, keine automatische
Bestätigung. Eine praktische Referenz darf eine Entwurfsentscheidung nicht
als bestätigt ausgeben.

## Einträge

### D-001 – Leanes Initial-Setup als wiederverwendbarer Projektstart

- **Datum:** 2026-07-21
- **Status:** Entwurf – im ersten Projektfall prüfen
- **Entscheidung:** Das neue `docs/governance/base-template.md` ist die fachliche,
  projektübergreifende Baseline und der wiederverwendbare Basisbaustein. Die
  operativen Artefakte sind nach `governance/`, `foundations/`, `operations/`
  und `tooling/`
  getrennt; `templates/project-template.md` ist davon getrennt die Vorlage für
  projektspezifische Ergänzungen. Ein konkretes Projektkit mit Brand-, Produkt-
  und Architekturdaten wird erst bei Bedarf daraus abgeleitet – statt vorab
  eine vollständige Komponenten-, Token- oder Automatisierungsarchitektur
  festzulegen.
- **Begründung:** Es macht die für Mensch und Agent notwendigen Entscheidungen
  explizit, ohne vor dem ersten Anwendungsfall unnötige Standards zu erfinden.
- **Nicht Teil des ersten Setups:** Framework-Vorgaben, Atomic-Design-Taxonomie,
  vollständige Tokens, CI-Pipelines oder automatisierte Figma-Synchronisation.
- **Betroffene Artefakte:** `AGENTS.md`, `docs/governance/base-template.md`,
  `docs/README.md`, `templates/project-template.md`

### D-002 – Entscheidungsrechte für Mensch und Agent

- **Datum:** 2026-07-21
- **Status:** Entwurf – im ersten Projektfall prüfen
- **Geltungsbereich:** Schreibende und standardverändernde Arbeit in allen
  Projekten, die das Base Template anwenden.
- **Entscheidung:** Agenten dürfen bestätigte Regeln innerhalb eines
  freigegebenen, reversiblen Umfangs anwenden. Bei unklaren Quellen, neuen
  Regeln oder Bausteinen, großen Reichweiten, Überschreiben, Löschen,
  Veröffentlichung und Ausnahmen erstellen sie einen Entscheidungsbefund;
  Menschen geben die Entscheidung oder Freigabe.
- **Begründung:** Technische Schreibfähigkeit soll nicht zu stillschweigender
  fachlicher Entscheidungsbefugnis führen.
- **Betroffene Artefakte:** `AGENTS.md`, `docs/governance/base-template.md`,
  `docs/operations/checklists.md`, `docs/operations/prompting-guide.md`

### D-003 – Fortlaufende Pflege des Entscheidungslogs

- **Datum:** 2026-07-21
- **Status:** Entwurf – im ersten Projektfall prüfen
- **Geltungsbereich:** `docs/governance/decisions.md`
- **Entscheidung:** Das Entscheidungslog enthält nur folgenreiche
  Entscheidungen, Freigaben, Ausnahmen, Ablehnungen und Ablösungen. Es wird
  über eine Übersicht und die Statuswerte `Entwurf`, `bestätigt`, `abgelöst`
  und `verworfen` fortlaufend gepflegt.
- **Begründung:** Die relevanten Entscheidungen bleiben auffindbar, ohne das
  Log mit Routineausführungen zu überladen.
- **Betroffene Artefakte:** `AGENTS.md`, `docs/governance/decisions.md`,
  `docs/governance/base-template.md`, `docs/operations/checklists.md`

### D-004 – Getrennte, menschliche Projekt-Wiki

- **Datum:** 2026-07-21
- **Status:** Entwurf – im ersten Projektfall prüfen
- **Geltungsbereich:** `wiki/`
- **Entscheidung:** Eine getrennte, lebendige Wiki vermittelt Menschen
  Projektzweck, Zusammenhänge, aktuellen Stand, Bewertungsfragen und die
  Funktion der Steuerungsdateien. Sie verweist direkt auf deren verbindliche
  Fassung, folgt aber einer eigenständigen menschlichen Informationslogik. Bei
  jeder folgenreichen Entwicklungsänderung wird sie im selben Arbeitsschritt
  aktualisiert. Nach jeder strukturellen Änderung werden Wiki-Navigation und
  Quellenverweise geprüft. Die operativen Maschinenartefakte unter `docs/` bleiben schlank
  und werden nicht um erläuternden Vermittlungskontext erweitert.
- **Begründung:** Strukturierte Maschinenartefakte sind keine ausreichende
  Aneignungs- und Bewertungsform für Menschen. Transparenz braucht eine eigene,
  lesbare Darstellung ohne operative Doppelpflege.
- **Betroffene Artefakte:** `AGENTS.md`, `docs/governance/decisions.md`, `wiki/`

### D-005 – Wiederkehrende Qualitäts- und Verständlichkeitsevaluation

- **Datum:** 2026-07-21
- **Status:** Entwurf – am ersten Projektfall kalibrieren
- **Geltungsbereich:** Steuerungsartefakte, Projekt-Wiki und relevante
  Entwicklungsänderungen.
- **Entscheidung:** Eine wiederkehrende Evaluation prüft operative
  Design-Ops-Konformität, Lean, Operationalisierbarkeit und die menschliche
  Vermittlungsqualität. Ergebnisse werden als Kurzbefund im Evaluation Log
  erfasst; Korrekturen werden in die zuständigen Steuerungsdateien und bei
  Bedarf in die Wiki zurückgeführt.
- **Begründung:** Die Struktur bleibt nur dann wirksam, wenn sie regelmäßig
  gegen tatsächliche Steuerbarkeit und menschliches Verständnis geprüft wird.
- **Betroffene Artefakte:** `AGENTS.md`, `docs/governance/evaluation-framework.md`,
  `docs/governance/evaluation-log.md`, `wiki/`

### D-006 – Kontextverantwortung zwischen Repository, Figma, Code und Wiki

- **Datum:** 2026-07-23
- **Status:** Entwurf – am read-only Tooling-Test v0.2 prüfen
- **Geltungsbereich:** Figma-Kontext, Design-to-Code und menschliche
  Projektvermittlung.
- **Entscheidung:** Das Repository hält Governance, Entscheidungen und
  Umsetzungsregeln; Figma hält visuelle Systemstruktur und designnahe
  Annotationen; Code hält ausführbare Implementierung; die Wiki vermittelt
  Bedeutung und Entwicklungsstand. Die Ebenen verlinken einander, ohne
  verbindliche Inhalte vollständig zu duplizieren.
- **Begründung:** Eine explizite Kontextverantwortung reduziert Drift,
  Rückfragen und widersprüchliche Quellen.
- **Betroffene Artefakte:** `wiki/figma-context-and-handoff.md`,
  `wiki/governance-and-sources.md`, `docs/tooling/figma-mcp-tooling.md`,
  `docs/tooling/southleft-tooling.md`

### D-007 – Iterative Entwicklung über testbare Vertikalschnitte

- **Datum:** 2026-07-23
- **Status:** abgelöst durch D-011 am 2026-07-23
- **Geltungsbereich:** Entwicklung des Base Templates und seiner fachlichen
  Bausteine.
- **Entscheidung:** Jede Iteration prüft eine begrenzte fachliche Annahme und
  liefert einen anwendbaren Baustein samt Abnahme. v0.1 beschränkt sich auf die
  semantische Einordnung einer konkreten Benutzerhandlung, einen
  Bausteinvertrag und eine projektspezifische Ableitung. Weitere Ebenen,
  Bausteine oder Automatisierungen werden erst nach belegtem Bedarf ergänzt.
- **Begründung:** Kleine Vertikalschnitte liefern frühe Nutzungsevidenz und
  begrenzen Dokumentations-, Freigabe- und Änderungsaufwand.
- **Betroffene Artefakte:** `docs/governance/base-template.md`,
  `docs/foundations/semantic-model.md`, `docs/operations/checklists.md`,
  `templates/project-template.md`, `wiki/project-portrait.md`,
  `wiki/working-model.md`

### D-008 – Getrennte KI-Tooling-Tests

- **Datum:** 2026-07-23
- **Status:** Entwurf – mit dem ersten Tooling-Test prüfen
- **Geltungsbereich:** KI- und Figma-Tooling im Rahmen des Base Templates.
- **Entscheidung:** KI-Tooling wird zunächst in kleinen, isolierten und
  reversiblen Tests geprüft. Ein Testbefund ist kein Standard und verändert
  keine kanonische Quelle. Eine Übernahme in Base Template, Project Template,
  Projektkit oder Figma-Library benötigt menschliche Bewertung, Evaluation und
  gegebenenfalls eine dokumentierte Entscheidung.
- **Begründung:** So bleibt die Entwicklung ergebnisoffen, token- und
  aufwandsarm sowie unter menschlicher Kontrolle.
- **Betroffene Artefakte:** `AGENTS.md`, `docs/governance/base-template.md`,
  `docs/operations/checklists.md`, `wiki/working-model.md`,
  `wiki/project-portrait.md`

### D-009 – Rollen als sichtbarer Arbeitskontext

- **Datum:** 2026-07-23
- **Status:** abgelöst durch `AGENTS.md` und die zuständigen Governance-/Rollenquellen am 2026-10-21
- **Geltungsbereich:** Aufträge an Agenten sowie menschliche Review- und
  Übergabesituationen.
- **Entscheidung:** Aufträge können die Perspektive `Design`, `Development`,
  `Review` oder `Governance` angeben. Die Rolle begrenzt und fokussiert den
  erwarteten Output, verleiht aber keine Freigabe- oder
  Standardisierungsbefugnis. Ohne Angabe gilt eine neutrale Analyse.
- **Begründung:** Perspektivische Klarheit erhöht Verständlichkeit und
  reduziert unnötigen Kontext, ohne starre Agenten-Personas zu erzeugen.
- **Betroffene Artefakte:** `AGENTS.md`,
  `docs/operations/prompting-guide.md`, `wiki/working-model.md`,
  `wiki/project-portrait.md`

### D-010 – Transparenz als Systemanforderung

- **Datum:** 2026-07-23
- **Status:** abgelöst durch `AGENTS.md`, Base Template, Checklists und Evaluation am 2026-10-21
- **Geltungsbereich:** Agentenbefunde, Test- und Entwicklungsabschlüsse sowie
  menschliche Wiki-Einordnung.
- **Entscheidung:** Jeder relevante Befund weist Arbeitsmodus, Rolle, Quellen,
  Aktion, automatisch ausgeführte Schritte, unveränderte Bereiche, menschliche
  Vorgaben und Entscheidungen, offene Punkte sowie genau einen nächsten
  prüfbaren Schritt aus. Die Wiki erklärt diese Trennung für Dritte ohne
  vorausgesetzten Chat-Kontext.
- **Begründung:** Niederschwellige Praxistauglichkeit setzt voraus, dass weder
  Automatik noch menschliche Verantwortung aus einem plausiblen Ergebnis
  erschlossen werden müssen.
- **Betroffene Artefakte:** `AGENTS.md`,
  `docs/governance/base-template.md`, `docs/operations/checklists.md`,
  `docs/governance/evaluation-framework.md`, `wiki/README.md`,
  `wiki/working-model.md`, `wiki/project-portrait.md`,
  `wiki/evaluation-and-review.md`

### D-011 – Generischer Library-Grundbaustein vor Projektkit und Entwurf

- **Datum:** 2026-07-23
- **Status:** Entwurf – an weiteren Regel- und Tooling-Tests prüfen
- **Geltungsbereich:** Base Template und seine Foundations.
- **Entscheidung:** Der aktuelle Ausbau fokussiert einen generischen
  Design-System-Grundbaustein. Er beschreibt Regeln für Design Principles,
  semantische Rollen, Token-Ebenen, Komponenten, Varianten, Zustände,
  Accessibility und isolierte KI-/Figma-Tooling-Tests. Ein Projektkit mit
  projektspezifischer Library und Entwurfsdateien bleibt eine spätere,
  abgeleitete Ebene und wird nicht in v0.1 vorweggenommen.
- **Begründung:** Die Trennung hält die Baseline technologie-, marken- und
  produktneutral, während reale, historisch gewachsene Libraries als
  Anschauungs- und Testmaterial dienen können.
- **Betroffene Artefakte:** `docs/governance/base-template.md`,
  `docs/foundations/`, `docs/operations/checklists.md`,
  `templates/project-template.md`, `wiki/`

### D-012 – Ausbaustufen zwischen Regelgrundlage und Projektableitung

- **Datum:** 2026-07-23
- **Status:** Entwurf – mit dem ersten read-only Test prüfen
- **Einordnung:** Historische Roadmap; nicht aktueller Ausführungsweg (2026-10-21)
- **Geltungsbereich:** Lieferumfang v0.1, KI-/Figma-Tooling-Tests und spätere
  Projektableitung.
- **Entscheidung:** v0.1 bleibt auf generische Library-Regeln und eine
  operationalisierte Testkarte begrenzt. v0.2 ist der nächste read-only Test
  der KI-/Figma-Lesefähigkeit. Dafür dürfen reale Projekt-Libraries als externe
  Testfixtures verwendet werden; sie sind weder Zielsystem noch Quelle für
  generische Standards. Schreibende Tooling-Tests und Projektableitungen bleiben
  spätere, separat zu bewertende Stufen.
- **Begründung:** Die Ausbaustufen halten den aktuellen Regelkern klein und
  machen den größeren Tooling-Schritt prüfbar, ohne ihn vorwegzunehmen.
- **Betroffene Artefakte:** `docs/governance/base-template.md`,
  `docs/operations/checklists.md`, `wiki/project-portrait.md`,
  `wiki/working-model.md`, `wiki/figma-context-and-handoff.md`

### D-013 – Agentenverantwortung für Toolwahl, Prompting und transparente Einschränkungen

- **Datum:** 2026-07-24
- **Status:** abgelöst durch `AGENTS.md`, Prompting Guide und Tooling Map am 2026-10-21
- **Geltungsbereich:** Alle KI-/Figma-/Design-System-Aufträge mit mehreren
  möglichen Zugriffsebenen oder begrenzten Tool- und Tokenressourcen.
- **Entscheidung:** Der Agent bestimmt selbst die benötigte Informationsebene,
  wählt die kleinste passende und tokensparende Tool-Funktion und formuliert
  dafür den passenden internen Systemprompt. Die Optimierung darf die
  ursprüngliche Absicht, den vereinbarten Umfang oder die Abnahme nicht
  stillschweigend verändern. Ist die Anfrage durch Tool-, Kontext- oder
  Tokenlimits nur eingeschränkt oder nicht ausführbar, weist der Agent vor der
  Handlung oder im Befund explizit auf die Einschränkung, die Auswirkung und
  die verbleibende Alternative hin. Bei einer folgenreichen Einschränkung wird
  gezielt rückgefragt; es wird keine Ersatzhandlung interpretiert oder
  vorweggenommen. Ein Tooling-Defizit wird außerdem getrennt vom fachlichen
  Befund bewertet und darf nicht als fachliche Schwäche des geprüften Systems
  erscheinen; nicht erreichbare Aspekte erhalten den Status `nicht bewertet`
  oder `eingeschränkt bewertet`.
- **Begründung:** Leaner Tooleinsatz und Tokenökonomie sollen den Menschen
  entlasten, nicht die fachliche Kontrolle oder das Vertrauen in den Befund
  schwächen. Vollständige Transparenz über Toolwahl, Prompt-Scope und Grenzen
  ist Voraussetzung für eine nachvollziehbare Mensch–Maschine-Arbeitsteilung.
- **Betroffene Artefakte:** `AGENTS.md`, `docs/tooling/tooling-map.md`,
  `docs/operations/prompting-guide.md`,
  `docs/governance/evaluation-framework.md`,
  `docs/governance/evaluation-log.md`, `wiki/figma-context-and-handoff.md`

### D-014 – Evidenz- und Toolingstatus vor fachlicher Ableitung

- **Datum:** 2026-07-24
- **Status:** abgelöst durch `AGENTS.md`, Evaluation Framework und Workflows am 2026-10-21
- **Geltungsbereich:** Kurz- und Vollprüfungen, Tooling-Tests und ihre Wiki-
  Einordnung.
- **Entscheidung:** Jeder Evaluationsblock beginnt mit dem Evidenz- und
  Toolingstatus: Arbeitsmodus, gewählte Funktion, tatsächlicher Scope,
  automatisch sichtbare Informationen, nicht sichtbare Informationen,
  Vollständigkeit und Unsicherheit. Erst danach werden fachliche Befunde,
  Design-Ops-Bewertungen oder Empfehlungen formuliert. Reicht die Evidenz für
  eine Aussage nicht aus, lautet der Status `nicht bewertet` oder
  `eingeschränkt bewertet`.
- **Begründung:** Menschen müssen vor jeder Interpretation erkennen können, was
  der Agent tatsächlich gesehen hat und wo eine Aussage endet. Das verhindert,
  dass eine plausible Ableitung als vollständige Systemkenntnis missverstanden
  wird.
- **Betroffene Artefakte:** `AGENTS.md`,
  `docs/governance/evaluation-framework.md`,
  `docs/governance/evaluation-log.md`, `wiki/figma-context-and-handoff.md`

### D-015 – Regelkandidaten und explizite Regelsetzung

- **Datum:** 2026-07-24
- **Status:** abgelöst durch `AGENTS.md` und Decision Log am 2026-10-21
- **Geltungsbereich:** Wiederkehrende Befunde, Arbeitsmuster und mögliche neue
  Governance- oder Arbeitsregeln.
- **Entscheidung:** Der Agent prüft selbst, ob ein Befund über den Einzelfall
  hinaus wiederverwendbar oder steuerungsrelevant ist. Er kennzeichnet dies als
  `Regelkandidat`. Ist unklar, ob daraus eine verbindliche Regel werden soll,
  fragt er gezielt: „Regelkandidat erkannt. Soll ich ihn als Regel setzen?“ Ohne
  Zustimmung bleibt der Inhalt Vorschlag oder Befund und verändert keine
  verbindliche Quelle. Das Codewort `REGEL SETZEN` erteilt die ausdrückliche
  Anweisung, den geprüften Regelkandidaten in die zuständigen Steuerungsdateien
  zu überführen und im Decision Log zu verankern.
- **Begründung:** Der Mensch soll nicht selbst erkennen müssen, wann ein
  Einzelfall zur Governance wird; zugleich darf keine stille Verregelung
  entstehen.
- **Betroffene Artefakte:** `AGENTS.md`, `docs/governance/decisions.md`,
  `docs/governance/evaluation-log.md`, `wiki/`

### D-016 – Konkreter Delta-Nachweis bei „Status sichern“

- **Datum:** 2026-07-24
- **Status:** abgelöst durch `AGENTS.md` und Evaluation Log am 2026-10-21
- **Geltungsbereich:** Steuerbefehl `Status sichern` und seine menschliche
  Rückmeldung.
- **Entscheidung:** Jeder Sicherungslauf endet mit den vier Delta-Feldern
  `Neu gesichert`, `Geändert`, `Nicht übernommen` und `Offen`. Die Angaben
  beziehen sich auf den vorherigen gesicherten Stand und nennen die betroffenen
  Dateien oder Quellen konkret.
- **Begründung:** Menschen müssen erkennen können, was sich durch den Befehl
  tatsächlich verändert hat; ein allgemeiner Abschlussstatus reicht nicht aus.
- **Betroffene Artefakte:** `AGENTS.md`, `wiki/quick-controls.md`,
  `docs/governance/decisions.md`

### D-017 – Aktive Ziel-, Lean- und Proportionalitätsprüfung

- **Datum:** 2026-07-24
- **Status:** bestätigt – im nächsten realen Entwicklungsfall praktisch prüfen
- **Geltungsbereich:** Alle Vorschläge, Regelkandidaten, neuen Dateien,
  Evaluationsschritte und strukturellen Erweiterungen.
- **Entscheidung:** Der Agent prüft aktiv, ob eine angefragte oder selbst
  erkannte Änderung dem Ziel dient, lean bleibt, operationalisierbar ist und
  einen vertretbaren Token- und Pflegeaufwand besitzt. Vor einer Neuanlage
  prüft er, ob ein bestehendes Artefakt genügt. Er darf einer Nutzeridee
  widersprechen, wenn sie redundant, überdimensioniert oder zielwidrig wäre,
  und muss den Befund kurz transparent rückmelden. Rollen und Evaluationen
  werden aktiv angewendet, aber nicht automatisch als zusätzliche Dateien oder
  Ebenen erzeugt.
- **Begründung:** Menschliche Steuerung braucht einen prüfenden Partner, nicht
  bloße Zustimmung. Leanheit und Tokenökonomie sind Qualitätskriterien der
  Lösung, nicht nur nachträgliche Dokumentationsprüfungen.
- **Betroffene Artefakte:** `AGENTS.md`,
  `docs/governance/evaluation-framework.md`,
  `docs/governance/decisions.md`, `docs/governance/evaluation-log.md`,
  `wiki/working-model.md`

### D-018 – Menschlich verständlicher `PROMPT`-/`AUSFÜHREN`-Ablauf

- **Datum:** 2026-07-24
- **Status:** bestätigt – im nächsten realen Auftrag praktisch prüfen
- **Geltungsbereich:** Unstrukturierte Aufträge mit unklarem Kontext,
  insbesondere Figma-, Design-System- und Tooling-Aufgaben.
- **Entscheidung:** `PROMPT` erzeugt eine verständliche Auftragsbestätigung
  mit Ziel, Quelle, „Ich prüfe“/„Ich prüfe nicht“, Arbeitsmodus, Rolle,
  passender Tool-Funktion, Grenzen, offenen Fragen und Abnahme. Der Agent
  wählt die technische Funktion selbst und zeigt sie als kurzen Nachweis,
  ohne kryptische interne Details zum Bedienzwang zu machen. Erst die explizite
  Antwort `AUSFÜHREN` startet die bestätigte Aktion. Der Mensch muss keinen
  strukturierten Block kopieren; technische IDs wie Set-Keys sind nur
  Transparenzdaten.
- **Begründung:** Unstrukturierte Eingaben dürfen nicht stillschweigend
  interpretiert werden. Die zweistufige Interaktion reduziert Fehlaufrufe,
  Iterationen und Tokenverbrauch und hält die menschliche Kontrolle sichtbar.
- **Betroffene Artefakte:** `AGENTS.md`,
  `docs/operations/prompting-guide.md`, `wiki/quick-controls.md`,
  `docs/governance/decisions.md`, `docs/governance/evaluation-log.md`,
  `wiki/working-model.md`

### D-019 – Menschenzentrierte Wiki und routinemäßige Informationsarchitekturprüfung

- **Datum:** 2026-07-27
- **Status:** bestätigt
- **Geltungsbereich:** `wiki/`, ihre Quellenverweise und die menschliche
  Einordnung von Agenten- und Projektarbeit.
- **Entscheidung:** Die Wiki ist eine eigenständige Menschenschicht. Jede
  Wiki-Seite muss ohne Chat-, Struktur- oder Modellvorwissen Zweck,
  Hauptaussage, Relevanz, Status, Arbeitsteilung, offene Entscheidung und
  nächsten prüfbaren Schritt vermitteln. Fachbegriffe werden beim ersten
  Auftreten erklärt oder verlinkt. Verbindliche Detailregeln bleiben in
  `AGENTS.md` oder `docs/`; die Wiki ordnet sie ein und verweist auf die
  Quelle.

  `WIKI PRÜFEN` ist der standardisierte Review-Befehl für diese Schicht. Er
  prüft Seitenschnitt, Vermittlungslogik, Quellenrückbindung, Transparenz,
  kognitive Last und interne Links. Der Befund enthält einen Gesamtstatus,
  seitenweise Lücken, höchstens einen kleinen Anpassungsvorschlag pro Befund
  und genau einen nächsten prüfbaren Schritt. Neue Dateien oder Regeln werden
  durch die Prüfung nicht automatisch erzeugt.
- **Begründung:** Maschinenlesbare Steuerungsdateien sind keine ausreichende
  Form menschlicher Aneignung. Dritte müssen Bedeutung, Verantwortung und
  Handlungsmöglichkeiten erkennen können, ohne implizites Projektwissen zu
  besitzen. Die feste Prüfung verhindert, dass die Wiki nur wächst, ohne
  verständlicher zu werden.
- **Betroffene Artefakte:** `AGENTS.md`,
  `docs/governance/evaluation-framework.md`,
  `docs/operations/checklists.md`, `docs/governance/decisions.md`,
  `wiki/README.md`, `wiki/working-model.md`, `wiki/evaluation-and-review.md`,
  `wiki/quick-controls.md`, `wiki/project-portrait.md`

### D-021 – Rollen, User Stories und progressive Wiki-Vermittlung

- **Datum:** 2026-07-27
- **Status:** bestätigt – praktische Rollenvalidierung ausstehend
- **Geltungsbereich:** Rollenperspektiven, User Stories, Wiki-
  Informationsarchitektur und menschenzentrierte Evaluationskriterien.
- **Entscheidung:** Die verbindlichen Rollenbeschreibungen, ihre
  User Stories, Bedürfnisse und Prüffoki werden im Governance-Artefakt
  `docs/governance/role-needs-and-user-stories.md` geführt. Die Wiki enthält
  keine eigenständige Rollen- oder Persona-Sammlung, sondern vermittelt
  relevante Inhalte für Menschen entlang selektiver Lesepfade.

  Wiki-Seiten müssen progressive Offenlegung ermöglichen: zuerst Zweck,
  Hauptaussage, Relevanz und Status; danach Auswahl- und Handlungshinweise;
  anschließend Begründung, Beispiele und Evidenz; zuletzt verbindliche Quellen
  und Detailregeln. Überschriften, Statuslabels, Tabellen, Links und
  Codeformatierung werden semantisch zur Lesbarkeit eingesetzt.
- **Begründung:** Rollen und User Stories sind Steuerungs- und
  Anforderungswissen. Ihre doppelte Pflege in der Wiki erzeugt Drift. Menschen
  brauchen dagegen eine verständliche, selektiv lesbare Vermittlung, die je
  nach Frage nur den erforderlichen Kontext öffnet.
- **Betroffene Artefakte:** `AGENTS.md`,
  `docs/governance/evaluation-framework.md`,
  `docs/governance/role-needs-and-user-stories.md`,
  `docs/governance/decisions.md`, `wiki/README.md`,
  `wiki/working-model.md`, `wiki/evaluation-and-review.md`,
  `wiki/governance-and-sources.md`

### D-022 – Technisch, agentisch und informationell versierter Review

- **Datum:** 2026-07-27
- **Status:** bestätigt – praktische Validierung ausstehend
- **Geltungsbereich:** Anforderungen, Tooling-Vorschläge, Wiki-
  Strukturänderungen, neue Regeln, Piloten und Standardübernahmen.
- **Entscheidung:** Die bestehende Rolle `Review` erhält einen technisch,
  agentisch und informationsarchitektonisch versierten Prüffokus. Sie bewertet
  Zielbeitrag, Zeitpunkt, technische Machbarkeit, Tool- und Promptpassung,
  Evidenzgrenzen, Token-/Zeit-/Iterationsaufwand, Pflegekosten,
  Informationsdesign, Wissensvermittlung, progressive Offenlegung,
  semantische Lesbarkeit und Praxistauglichkeit im Designer-Alltag.

  Der Review-Fokus darf Anforderungen begrenzen, Alternativen vorschlagen,
  fehlende Voraussetzungen benennen und bei Zielabweichung widersprechen. Er
  erteilt keine fachliche Freigabe und setzt keine Standards eigenständig.
  State-of-the-art Empfehlungen benötigen eine belastbare Quelle oder einen
  begrenzten Test. Die kleinste verhältnismäßige Teststufe wird gewählt.
- **Begründung:** Technische Machbarkeit allein reicht nicht, wenn ein
  Werkzeug, eine Wissensstruktur oder eine Wiki-Seite im Entwurfsalltag nicht
  verständlich und handlungsfähig macht. Die kombinierte Prüfung verhindert
  blinde Toolbegeisterung, Dokumentationsdrift und überdimensionierte Lösungen.
- **Betroffene Artefakte:** `AGENTS.md`,
  `docs/governance/role-needs-and-user-stories.md`,
  `docs/governance/evaluation-framework.md`,
  `docs/operations/checklists.md`, `docs/governance/decisions.md`,
  `docs/governance/evaluation-log.md`,
  `wiki/figma-context-and-handoff.md`, `wiki/evaluation-and-review.md`

### D-023 – Zielgruppen- und Schichtpassung von Dokumentationsinhalten

- **Datum:** 2026-07-27
- **Status:** bestätigt
- **Geltungsbereich:** Alle Änderungen an `AGENTS.md`, `docs/` und `wiki/`.
- **Entscheidung:** Vor jeder Dokumentationsänderung werden Zielgruppe,
  Artefaktzweck, Inhaltstyp, Detailtiefe und Nicht-Scope geprüft. Operative
  Dateien unter `docs/` enthalten primär ausführbare Regeln, Prüfschritte,
  Statuswerte und Nachweise. Erklärende, motivierende, didaktische oder
  kontextualisierende Inhalte gehören in die Wiki und werden von dort auf die
  verbindliche Quelle verlinkt. Eine Datei darf keine Inhalte aufnehmen, die
  nur wegen ihrer thematischen Nähe passen.
- **Begründung:** Die vorherige Erweiterung von `checklists.md` vermischte
  maschinenorientierte Prüfung mit menschlicher Einordnung und erzeugte damit
  unnötigen Kontext sowie Fehlinterpretationsrisiko. Die Regel macht die
  Zielgruppen- und Zweckprüfung vor der Änderung verpflichtend.
- **Prüfnachweis:** Der Agent weist bei strukturellen Änderungen kurz
  Artefakt, Zielgruppe, Zweck, Inhaltstyp, Nicht-Scope und bestehende passendere
  Quelle aus. Bei unklarer Passung wird nicht geschrieben, sondern rückgefragt
  oder ein begrenzter Vorschlag vorgelegt.
- **Betroffene Artefakte:** `AGENTS.md`,
  `docs/governance/evaluation-framework.md`,
  `docs/governance/decisions.md`, `docs/operations/checklists.md`,
  `docs/governance/evaluation-log.md`, `wiki/governance-and-sources.md`

### D-024 – Mehrstufige Wiki-Link- und Quellenprüfung

- **Datum:** 2026-07-27
- **Status:** bestätigt
- **Geltungsbereich:** `wiki/`, insbesondere Orientierungs- und
  Quellenlandkarten sowie Wiki-zu-`docs`-Verweise.
- **Entscheidung:** Jeder Linktest unterscheidet drei Ebenen: technische
  Gültigkeit (Datei, Syntax, Anker), strukturelle Vollständigkeit (erwartete
  Tabellenzeilen, Spalten und klickbare Pflichtfelder) und semantische
  Quellenpassung (Linktext, Einstiegsseite und zuständige verbindliche Quelle).
  Der Testbericht weist geprüfte Dateien, Links, Tabellen, Pflichtfelder,
  Fehlerarten und nicht geprüfte Ebenen getrennt aus. Ein Dateiexistenz- oder
  Ankercheck darf nicht als vollständiger Link- oder Quellenreview bezeichnet
  werden.
- **Begründung:** Der frühere Test prüfte technische Ziele, aber nicht, ob die
  Orientierungslandkarte in jeder Zeile vollständig verlinkt und fachlich
  passend war. Dadurch konnte `0 Fehler` trotz unvollständiger menschlicher
  Navigation entstehen.
- **Betroffene Artefakte:** `AGENTS.md`,
  `docs/operations/checklists.md`,
  `docs/governance/evaluation-framework.md`,
  `docs/governance/decisions.md`, `docs/governance/evaluation-log.md`,
  `wiki/governance-and-sources.md`, `wiki/evaluation-and-review.md`

### D-025 – Trennung der Nutzungsebene und schlanke Agenten-Einstiegskarte

- **Datum:** 2026-07-27
- **Status:** bestätigt
- **Geltungsbereich:** `AGENTS.md`, `docs/`, Wiki-Einordnung und
  Evaluationsbefunde.
- **Entscheidung:** Jeder Auftrag und Befund weist neben Modus und
  Rolle eine Nutzungsebene aus: `Fachliche Nutzung` oder
  `Systementwicklung`. `AGENTS.md` enthält nur unmittelbar ausführungs-
  relevante Sicherheits- und Routingregeln; Details liegen genau einmal in
  der zuständigen Detailquelle. Vor Kürzung oder Verschiebung wird eine
  Quellen-/Funktionszuordnung erstellt und die Schutzwirkung für Lesen, Pilot
  und Standardänderung nachgewiesen.
- **Begründung:** Die reale Nutzung im Gestaltungsalltag und die
  Weiterentwicklung des Repros haben unterschiedliche Ziele, Evidenzen und
  Abnahmen. Eine kurze Einstiegskarte reduziert Pflege- und Tokenaufwand,
  sofern keine Funktion oder Schutzwirkung verloren geht.
- **Betroffene Artefakte:** `AGENTS.md`, `docs/README.md`,
  `docs/governance/base-template.md`, `docs/operations/prompting-guide.md`,
  `docs/operations/checklists.md`

### D-026 – Übernahmeart und funktionsgenaues Toolrouting

- **Datum:** 2026-07-27
- **Status:** bestätigt
- **Geltungsbereich:** Auftragsklärung und Toolwahl bei Übernahmen zwischen
  Dateien, Systemen, Libraries oder Accounts.
- **Entscheidung:** Vor der Toolwahl klärt der Agent die Übernahmeart
  (`lokale Kopie`, `verknüpfte Instanz`, `Verschieben` oder
  `Rekonstruktion`) und das Erhaltungsziel. Anschließend bestimmt er die
  Funktionsklasse und prüft den tatsächlichen Scope der konkreten Funktion.
  Deckt sie die bestätigte Aktion nicht ab, stoppt der Agent; Import,
  Rekonstruktion oder ein anderer Ersatzweg benötigen eine neue menschliche
  Auswahl.
- **Begründung:** Ein gleiches Ergebnis kann technisch unterschiedliche
  Beziehungen zwischen Quelle und Ziel bedeuten. Die Reihenfolge schützt vor
  stillschweigender Rekonstruktion, ungewollten Library-Verknüpfungen und
  falschem Toolrouting.
- **Betroffene Artefakte:** `AGENTS.md`,
  `docs/governance/base-template.md`,
  `docs/operations/prompting-guide.md`,
  `docs/tooling/tooling-map.md`, `docs/operations/checklists.md`,
  `wiki/figma-context-and-handoff.md`,
  `docs/governance/evaluation-log.md`.

### D-027 – Pflege- und Statussynchronisation

- **Datum:** 2026-07-28
- **Status:** Entwurf – als Regelkandidat praktisch prüfen
- **Geltungsbereich:** Entscheidungslog, operative Quellen, Quick Controls und
  Evaluationspflege.
- **Entscheidungskandidat:** Eine zentrale Kandidatenübersicht weist für jede
  praktisch referenzierte, aber noch nicht bestätigte Entscheidung Status,
  Fundstellen und nächste Klärung aus. Vor einer verbindlichen Nutzung wird
  geprüft, ob die Entscheidung bestätigt, als Pilot begrenzt oder aus den
  operativen Quellen entfernt werden muss. `REGEL SETZEN` synchronisiert
  Status, verbindliche Quelle, Decision Log und Evaluation-Nachweis.
- **Begründung:** Ohne diesen Abgleich können Entwurfsentscheidungen faktisch
  als Regeln wirken, obwohl ihre Freigabe noch fehlt.
- **Betroffene Artefakte:** `docs/governance/decisions.md`,
  `docs/operations/checklists.md`, `wiki/quick-controls.md`,
  `docs/governance/evaluation-framework.md`,
  `docs/governance/evaluation-log.md`

### D-028 – Evidenzstatus externer Wissens-MCPs

- **Datum:** 2026-07-28
- **Status:** bestätigt
- **Geltungsbereich:** Externe Wissens-MCPs in Tooling Map, Prompting Guide,
  Southleft-Tooling und Evaluation.
- **Entscheidung:** Ein externes Wissens-MCP wird erst dann als Evidenzquelle
  verwendet, wenn die konkrete Abfrage fachlich passende und
  quellenzuordenbare Treffer liefert. Eine konfigurierte Verbindung,
  sichtbare Toolfunktion, Kategorienamen oder eine Repository-Beschreibung
  reicht dafür nicht. Fehlen passende Treffer, weist der Befund die
  Tooling-Grenze aus und verwendet eine Primärquelle als Rückfallebene.
- **Begründung:** Der öffentliche Southleft Design Systems MCP war erreichbar,
  lieferte jedoch bei WCAG-, DTCG- und Komponentenabfragen nur einen
  unpassenden Sample-Eintrag; die Chat-Oberfläche brach zusätzlich mit einem
  Worker-Ressourcenfehler ab. Die Trennung verhindert, dass technische
  Erreichbarkeit als fachliche Evidenz ausgegeben wird.
- **Betroffene Artefakte:** `docs/tooling/tooling-map.md`,
  `docs/tooling/southleft-tooling.md`,
  `docs/operations/prompting-guide.md`,
  `docs/governance/evaluation-log.md`,
  `wiki/governance-and-sources.md`.

### D-029 – Entwicklungspriorisierung und begründete Iteration

- **Datum:** 2026-07-28
- **Status:** bestätigt
- **Geltungsbereich:** Systementwicklung, Evaluation, Review und menschliche
  Einordnung von Entwicklungsbefunden.
- **Entscheidung:** Vor einer Systementwicklungsmaßnahme wird deren erwarteter
  Nutzen für die betroffene Rolle, Aufwand, Pflege- und Tokenlast, Folge des
  Nichtstuns, kleinste prüfbare Umsetzung und Abbruchkriterium sichtbar
  eingeordnet. Das Ergebnis lautet genau eines von `jetzt umsetzen`,
  `Pilot/Kandidat`, `bewusst bewahren`, `derzeit nicht relevant` oder
  `verwerfen/ablösen`. Eine weitere Iteration braucht einen zusätzlichen
  Evidenz- oder Entscheidungsgrund; Plausibilität allein genügt nicht.
- **Begründung:** Die vorhandene Lean-Prüfung bewertet bereits Zielbeitrag und
  Aufwand, machte aber die Entscheidung zwischen Umsetzung, bewusster
  Nicht-Änderung und späterem Kandidaten nicht durchgängig sichtbar. Die
  Ergänzung verhindert Aktivität ohne erkennbaren Nutzen für fachliche Nutzung
  oder Systementwicklung.
- **Betroffene Artefakte:** `docs/governance/evaluation-framework.md`,
  `docs/operations/checklists.md`, `docs/governance/evaluation-log.md` und
  `wiki/evaluation-and-review.md`.

### D-030 – Sichtbare Ausführungsfreigabe in `PROMPT`

- **Datum:** 2026-07-28
- **Status:** bestätigt
- **Geltungsbereich:** Ausführungsbereite `PROMPT`-Bestätigungen in
  `AGENTS.md`, Prompting Guide und menschlicher Schnellsteuerung.
- **Entscheidung:** Jeder ausführungsbereite `PROMPT` endet sichtbar mit
  „Mit `AUSFÜHREN` führe ich [konkret bestätigte Aktion] im Modus [Modus]
  aus.“ Die Abschlusszeile benennt nur den bereits bestätigten Auftrag. Sie
  erweitert weder Scope noch Entscheidungsrecht und ersetzt keine fachliche
  Freigabe. Eine alleinstehende Nutzernachricht `AUSFÜHREN` ist der Code zur
  Ausführung dieses unmittelbar vorher bestätigten, noch nicht ausgeführten
  Auftrags; ohne solchen Auftrag wird keine neue Aktion erraten.
- **Begründung:** D-018 schützt den Übergang von Vorschlag zu Aktion, machte
  die konkrete Handlungsaufforderung aber nicht durchgängig sichtbar. Die
  kurze Zeile reduziert Erinnerungsaufwand, macht die Freigabeschwelle
  wiedererkennbar und verhindert, dass ein `PROMPT` wie ein bloßer Vorschlag
  wirkt.
- **Betroffene Artefakte:** `AGENTS.md`,
  `docs/operations/prompting-guide.md`, `wiki/quick-controls.md`,
  `docs/governance/evaluation-log.md`.

### D-031 – KI-gestützte externe Dienste im Gestaltungskontext

- **Datum:** 2026-07-28
- **Status:** bestätigt
- **Quelle der Vorgabe:** Vom verantwortlichen internen Ansprechpartner
  übergebene verbindliche Rahmenbedingungen.
- **Geltungsbereich:** KI-Tools und KI-Funktionen in der Kreation,
  insbesondere Figma, Miro, Plugins, APIs, MCP-Server und externe
  Integrationswege.
- **Entscheidung:** Agentische Unterstützung ist nur zulässig, wenn eine
  intern freigegebene KI-Alternative ohne zwingende Aktivierung der
  KI-Verarbeitung des Tool-Anbieters genutzt werden kann. Jede Nutzung wird je
  Tool, Integrationsweg und Anwendungsfall durch den ISB geprüft und im ISMS
  dokumentiert. Projektbezogene vertragliche, regulatorische und
  datenschutzrechtliche Vorgaben haben Vorrang.

  Es dürfen ausschließlich freigegebene Integrationen verwendet werden.
  Berechtigungen sind rollenbasiert und minimal; Lesen, Vorschlag und
  Schreiben werden getrennt bewertet. Unternehmenskonto, SSO/MFA und
  nachvollziehbare Zugänge sowie Änderungen sind Voraussetzung. Datenfluss,
  Auftragsverarbeitung, Unterauftragsverarbeiter, Speicherort, Löschkonzept
  und mögliche Trainingsnutzung müssen vor dem Einsatz geklärt sein.

  Ohne gesonderte Freigabe sind personenbezogene Daten, vertrauliche
  Kundeninformationen, Zugangsdaten, Tokens, API-Keys, Secrets und
  sicherheitsrelevante Architektur- oder Betriebsinformationen ausgeschlossen.
  KI-Ergebnisse bleiben Vorschläge. Schreibende Nutzung verlangt
  Versionierbarkeit, verantwortliche Zuordnung und menschliche Freigabe vor
  produktiver oder kundensichtbarer Verwendung. Für Figma und Miro werden
  zulässige Workspaces, Dateien, Seiten beziehungsweise Boards sowie Export,
  Import, Screenshots und aktivierbare Anbieter-KI einzeln festgelegt.
- **Begründung:** Die Regeln machen Nutzung, Datenübertragung und
  Entscheidungsrechte vor der technischen Toolwahl prüfbar. Sie verhindern,
  dass Verfügbarkeit, Lizenz oder Plan eines Dienstes als ISMS-Freigabe
  missverstanden werden.
- **Offene operative Freigaben:** Konkrete ISB-/ISMS-Freigabe je Tool,
  Integrationsweg und Anwendungsfall; Unternehmensvertrag, Plan, Konto,
  SSO/MFA, Datenklassifikation und zulässiger Zielbereich.
- **Betroffene Artefakte:** `docs/tooling/tooling-map.md`,
  `docs/operations/checklists.md`, `docs/governance/evaluation-framework.md`,
  `docs/governance/evaluation-log.md`, `wiki/governance-and-sources.md`.

### D-032 – Bewertung und Integrationsgrad neuer Fundstücke

- **Datum:** 2026-07-28
- **Status:** bestätigt
- **Geltungsbereich:** Systementwicklung; externe Tools, MCP-Server, Plugins,
  APIs, Open-Source-Projekte, Methoden, Patterns und Dokumentationsansätze.
- **Entscheidung:** Neue Fundstücke werden unabhängig von einer späteren
  Toolaufnahme auf Anlass, Wirkprinzip, vorhandene Überschneidung,
  Unabhängigkeit, übertragbares Wissen, Betriebs- und Sicherheitsgrenzen sowie
  Rückbaubarkeit bewertet. Der Vergleich erfolgt je betroffener Fähigkeit in
  einer Matrix aus bestehendem Ansatz, Fundstück, Einordnung, Mehrwert und
  Risiko. Der Mehrwert und das Risiko beziehen sich dabei jeweils auf den
  vorhandenen Ansatz: mögliche Ergänzung, Ersatz- oder Rückfallebene bei
  Plan-, Paywall-, Anbieter- oder Wartungsänderung werden sichtbar geprüft.
  Kontext-/Tokenökonomie wird nur dort bewertet, wo sie für diese Fähigkeit
  relevant ist. Die Entscheidung erfolgt über die Integrationsgrade
  `beobachten`, `Erkenntnis übernehmen`, `Arbeitsmuster übernehmen`,
  `begrenzter Pilot`, `integrieren` oder `referenzieren`. Eine
  Funktionsüberschneidung beendet die Prüfung nicht, begründet aber keine
  zusätzliche Toolschicht ohne belegten Mehrwert.
- **Statuslogik:** Jedes gesicherte Fundstück erhält genau einen Status
  `beobachten`, `Pilot/Kandidat`, `integriert`, `bewusst bewahren` oder
  `verwerfen/ablösen`. Der Status beschreibt den aktuellen
  Steuerungszustand. Integrationsgrade können parallel gelten und beschreiben
  nur, ob Erkenntnis, Arbeitsmuster, Pilot, Integration oder Referenz als
  möglicher Rückfluss vorliegt; sie sind keine Freigabe oder Betriebsstatus.
- **Begründung:** Externe Fundstücke können auch ohne operative Nutzung
  wertvolle Prinzipien oder effizientere Kontextmodelle liefern. Die
  abgestufte Bewertung macht diesen Lerngewinn sichtbar, vermeidet vorschnelle
  Toolaufnahme und schützt vor zusätzlichen Abhängigkeiten, Paywalls,
  Pflegeaufwand und unklaren Datenwegen.
- **Dokumentation:** Ein Befund mit Integrationsgrad und Wiederprüfkriterium
  wird im Evaluation Log gesichert und in dessen zentraler Fundstückübersicht
  verlinkt. Diese zeigt Fundstück und Lizenz, Mehrwert, Risiko, entscheidende
  Kriterien, aktuellen Integrationsrand und Wiederprüfauslöser. Eine Wiki-Seite
  ist zusätzlich zulässig, wenn der Befund menschliche Orientierung,
  Wiederverwendung oder eine Entscheidung erklärt; sie bleibt von der
  verbindlichen Detailquelle getrennt.
- **Betroffene Artefakte:** `docs/operations/workflows.md`,
  `docs/governance/evaluation-log.md`,
  `wiki/system-development-and-learning.md`,
  `wiki/governance-and-sources.md`.

### D-033 – Übernahme von Wissen aus externen Skills

- **Datum:** 2026-07-28
- **Status:** bestätigt
- **Geltungsbereich:** Systementwicklung; externe Skills, Skriptsammlungen,
  Plugins und vergleichbare Ablaufvorlagen.
- **Entscheidung:** Aus einem externen Skill werden nur die belegten,
  wiederverwendbaren Ablaufprinzipien übernommen — nicht Installation,
  automatische Aktivierung, Zugriffsrechte oder konkrete Skripte. Ein
  übernommener Ablauf beschreibt Ziel, Voraussetzungen, Lesescope,
  Schreibgrenze, erwartetes Ergebnis und Prüfung danach. Figma-Datenabruf,
  regelbasierte Auswertung, KI-Vorschlag (falls vorhanden) und menschliche
  Entscheidung bleiben getrennt. Umfangreiche Abrufe erhalten Scope-, Tiefen-
  oder Ausgabegrenzen. Deterministisch erzeugte Dokumentation ist als
  Ableitung der sichtbaren Eingabedaten kenntlich. Plugin-API-/OAuth- und
  REST-/persönlicher-Token-Wege sind getrennte Funktions-, Datenfluss- und
  Freigabepfade. Lint-, Score- und Auditbefunde sind Vorprüfungen, keine
  Qualitäts- oder Änderungsfreigabe.
- **Begründung:** Externe Skills können nützliche Struktur und
  Kontextbegrenzung sichtbar machen, ohne eine neue Toolschicht zu erfordern.
  Die selektive Übernahme bewahrt diesen Lernwert und verhindert, dass ein
  fremder, schreibfähiger oder tokengebundener Ablauf stillschweigend zur
  Projektfunktion wird.
- **Dokumentation:** Die ausführbare Detailregel liegt im Fundstückworkflow.
  Der Ausgangsbefund bleibt im Evaluation Log; die Wiki erklärt Zweck und
  Wirkung für Menschen.
- **Betroffene Artefakte:** `docs/operations/workflows.md`,
  `docs/governance/evaluation-log.md`,
  `wiki/system-development-and-learning.md`.

### D-034 – Erweiterungsfähigkeit von Komponentenverträgen

- **Datum:** 2026-07-30
- **Status:** bestätigt
- **Geltungsbereich:** Komponentenverträge im Base Template, generische
  Library-Standards und spätere Projektableitungen.
- **Entscheidung:** Das Base Template standardisiert keine projektspezifischen
  Varianten, Zustände, Werte oder Patterns im Voraus. Ein Komponentenvertrag
  muss aber sichtbar machen, welche Teile stabile Invarianten, aktuelle
  Ausprägungen, zulässige Kontextentscheidungen, additive Erweiterungen,
  restriktive Änderungen oder semantische Korrekturen wären. Eine Erweiterung
  darf bestehende Ableitungen nur stillschweigend ergänzen, wenn sie additiv
  ist und Zweck, Rolle, Verhalten und Accessibility unverändert bleiben.
- **Begründung:** Die Regel hält das Base Template offen für reale
  Projektkomplexität, ohne daraus einen vorsorglichen Variantenkatalog zu
  machen. Sie ist an externe Best Practice anschlussfähig: Design-Systeme
  modellieren Variantenachsen, Zustände, Priorität, Intent, Appearance und
  Accessibility unterschiedlich; daher muss der Vertrag die Art der
  Entscheidung trennen, nicht eine einzige Kategorienlogik vorgeben.
- **Nicht Teil der Entscheidung:** Konkrete Button-Varianten, Farbwerte,
  Figma-Seitenstruktur, Code-Implementierung oder eine allgemeine
  Primary-/Secondary-/Warning-Taxonomie.
- **Betroffene Artefakte:** `docs/governance/base-template.md`,
  `docs/foundations/standards.md`, `docs/operations/checklists.md`,
  `wiki/project-portrait.md`.

### D-035 – Vertrauensfähige Figma-Komponentendokumentation

- **Datum:** 2026-07-30
- **Status:** bestätigt
- **Geltungsbereich:** Figma-Piloten und Figma-Dokumentation von
  Komponenten im Base-Template-Kontext.
- **Entscheidung:** Eine Figma-Komponentendokumentation gilt nicht schon dann
  als erfüllt, wenn die geforderten Frames, Textanker oder Tabellen technisch
  existieren. Sie muss Vertrauen, Unterstützung und Verlässlichkeit praktisch
  herstellen: Menschen müssen Zweck, Status, Geltung, Beispiele, offene Punkte
  und Quellen visuell lesen und bewerten können; Agenten müssen dieselben
  Informationen über sichtbare Labels, Namen und Gliederung auffinden können.
  Leere Gerüste, verdeckte Texte, kaputte Tabellen, Scheinkomplettheit oder
  dominante Pilot-/Governance-Logik gelten als nicht erfüllt.
- **Begründung:** Der Button-v3-Figma-Pilot zeigte, dass Node- und
  Textvollständigkeit keine Dokumentationsqualität beweist. Für Vertrauen in
  KI-gestützte Design-System-Arbeit muss die sichtbare Figma-Fläche zuerst als
  menschlich nutzbare Komponenten-Dokumentation funktionieren; KI-Robustheit
  ist eine Eigenschaft dieser Struktur, nicht ihr Ersatz.
- **Nicht Teil der Entscheidung:** Konkrete Button-Taxonomie, Tokenmodell,
  Code-Implementierung, Code-Connect-Mapping oder produktive Figma-Reparatur.
- **Betroffene Artefakte:** `docs/governance/base-template.md`,
  `docs/foundations/standards.md`, `docs/operations/checklists.md`,
  `docs/tooling/figma-mcp-tooling.md`, `wiki/project-portrait.md`.

### D-036 – Trennung von Komponenten-Erstellung, -Prüfung und -Dokumentation

- **Datum:** 2026-07-31
- **Status:** bestätigt
- **Geltungsbereich:** Komponentenaufträge in Figma- und Library-Kontexten,
  insbesondere Piloten, Schreibprompts, Reviews und Dokumentationsflächen.
- **Entscheidung:** Ein Komponentenauftrag muss vor Ausführung unterscheiden,
  ob die Komponente selbst erstellt, eine bestehende Komponente geprüft, eine
  Komponente dokumentiert oder mehrere dieser Schritte in einer festgelegten
  Reihenfolge kombiniert werden. Dokumentation darf eine Komponente erklären,
  kontextualisieren und prüfbar machen; sie gilt aber nicht als Ersatz für die
  Komponente.
- **Arbeitsregel:** Wenn Erstellung und Dokumentation gemeinsam beauftragt
  sind, wird zuerst der Komponenten-Gegenstand bestimmt oder erzeugt und erst
  danach genau dieser Gegenstand dokumentiert. Ist der Gegenstand nicht
  vorhanden oder nicht benannt, darf der Auftrag nicht stillschweigend als
  reine Dokumentationsfläche ausgeführt werden.
- **Begründung:** Die V3/V4-Button-Piloten zeigten einen systemischen
  Auftragsdrift: Aus dem Ziel, eine reale Library-Komponente auf Basis des
  Vertrags zu erzeugen oder zu prüfen, wurde eine formale Dokumentationsfläche
  über eine Komponente. Das wirkt zunächst produktiv, verletzt aber Vertrauen,
  Unterstützung und Verlässlichkeit, weil der eigentliche Baustein fehlt und
  die KI aus Struktur scheinbare Reife ableiten kann.
- **Konsequenz für Prompting und Review:** Vor Figma-Schreibarbeit ist die
  Auftragsart explizit auszuweisen: `erstellen`, `prüfen`, `dokumentieren` oder
  `kombiniert`. Bei kombiniertem Auftrag ist die Reihenfolge Teil der Abnahme.
  Ein Komponentenpilot ist nur erfüllt, wenn eine echte Figma-Komponente, ein
  Component Set oder ein ausdrücklich bestehender Komponenten-Gegenstand im
  Scope steht.
- **Nicht Teil der Entscheidung:** Konkrete Button-Taxonomie, visuelle
  Ausprägung, Tokenmodell, Code Connect, Accessibility-Abnahme, produktive
  Figma-Reparatur, neue Template-Datei oder neuer Skill.
- **Betroffene Artefakte:** `docs/foundations/standards.md`,
  `docs/operations/checklists.md`, `docs/operations/prompting-guide.md`,
  `docs/governance/base-template.md`, `docs/governance/evaluation-log.md`,
  `wiki/project-portrait.md`, `wiki/system-development-and-learning.md`.

### D-037 – Quellen-, Status- und Pfadkonsolidierung

- **Datum:** 2026-10-20
- **Status:** bestätigt
- **Geltungsbereich:** Quellenautorität, Arbeitsstände, Reviews, Evaluation,
  operative Arbeitswege und die weitere Systementwicklung des
  Designer-Assistenzsystems.
- **Entscheidung:** Die in E-075 geprüfte und menschlich freigegebene
  Quellen-, Status- und Pfadmatrix ist die verbindliche
  Konsolidierungsgrundlage. Der Gate-basierte Arbeitsvertrag
  `Arbeitsauftrag → passende Quelle/Capability → Evidenz → Befund →
  menschliche Decision → Repository-Nachweis` ist der aktuelle Arbeitsweg.
  D-009 bis D-016 werden einzeln gegen ihre tatsächlichen Quellen und
  Schutzwirkungen bereinigt; abgelöste Einzelentries verweisen auf ihre
  verbindlichen Zielquellen, offene Entries bleiben Entwurf. D-019 bleibt als
  ursprüngliche Wiki-Decision sichtbar; E-071 begrenzt bis zu einer eigenen
  Entscheidung die Routinepflege. Historische Roadmaps, S0–S2-
  Befunde und Capability-Kandidaten werden nicht als aktuelle Ausführungswege
  behandelt.
- **Begründung:** Das Repository besitzt die fachlichen und operativen
  Bausteine bereits. Verlässliche Praxis scheitert aktuell an Statusdrift,
  Quellenüberlagerung und parallelen Arbeitsständen, nicht an fehlender
  Tooling- oder Runtime-Komplexität. Die Konsolidierung reduziert
  Fehlinterpretation, Pflegeaufwand und KI-Slop, ohne fachliche
  Entscheidungsrechte an die Assistenz zu übertragen.
- **Nicht Teil der Entscheidung:** Keine neue Runtime, keine Figma- oder
  Tokenänderung, keine automatische semantische Bewertung, keine
  Wiki-Reaktivierung, keine automatische Bestätigung der weiterhin offenen
  Entries und keine Issue-Erzeugung.
- **Betroffene Artefakte:** `AGENTS.md`, `docs/README.md`,
  `docs/governance/decisions.md`, `docs/governance/evaluation-log.md`,
  `docs/operations/workflows.md`, `docs/operations/checklists.md`,
  `reviews/repo-deep-audit-and-operationalization-2026-10-20.md` und die
  historisch gekennzeichneten S0-/S2-/Dev-ready-Reviews.
