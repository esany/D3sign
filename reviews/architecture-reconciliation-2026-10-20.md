# S0 – Architektur-Reconciliation für das Designer-Assistenzsystem

## Status und Transparenz

Dieser Befund ist ein unverbindlicher Systementwicklungsbefund im Modus
`Vorschlag` mit anschließendem `Status sichern`. Er klärt Autorität, Status,
Rollen und Pfade für die weitere Umsetzung. Er setzt keine neue Regel und ist
keine Freigabe für Code, Figma-Schreiben oder neue Infrastruktur.

**Arbeitsstand:** Historischer S0-Reconciliation-Befund. Die aktuelle
Quellen-, Status- und Pfadbereinigung wird in E-074/E-075 fortgeführt; dieser
Befund bleibt als Begründungs- und Migrationsnachweis erhalten.

| Feld | Einordnung |
|---|---|
| Ziel | Quellenautorität, Rollenvertrag, aktive/historische Pfade und Migrationsgrenzen vor S1 klären. |
| Gegenstand | Dev-ready Plan, Research-Befund, Governance, Operations, Tooling Map und Evaluation Log des Repositorys. |
| Nutzungsebene | `Systementwicklung`; fachliche Wirkung auf Designer:innen getrennt bewertet. |
| Modus | `Vorschlag` mit anschließendem `Status sichern`. |
| Rolle | Architecture, Development und Governance mit systemisch nutzerzentriertem Fokus. |
| Automatisch ausgeführt | gezielter Quellenabgleich, Status-/Pfadmatrix, Rollenabgleich und Reconciliation-Vorschlag. |
| Nicht verändert | bestätigte Decisions, AGENTS-Regeln, Figma, externe Dienste, Wiki-Detailseiten und Toolkonfigurationen. |
| Menschlich zu entscheiden | Statusübernahme offener Regeln, Zielquellen, Migration und Freigabe von S1. |
| Tooling-Grenze | Keine bestehende Produkt-Codebasis und keine bestätigte Figma-Integrationsfreigabe im Repository. |
| Genau ein nächster Schritt | Die vorgeschlagene Autoritäts- und Statusmatrix sowie den Übergang zu S1 menschlich freigeben oder zurückweisen. |

## 1. Ergebnis in einem Satz

Das aktuell tragfähige Zielsystem ist der **repo-first Arbeitsvertrag zwischen
Designer:in, Assistenz/Host, begrenzter Figma-Evidenz und Repository**. Die
bestätigten Decisions und `AGENTS.md` bilden den ausführbaren Kern. Die älteren
Entwurfsentscheidungen D-009 bis D-016, die v0.1/v0.2/v0.3-Roadmap, Wiki-
Pflegepfade sowie Code-/Write-Pfade dürfen bis zu einer menschlichen
Statusentscheidung nicht als aktive Architektur behandelt werden.

## 2. Quellen- und Autoritätsmatrix

| Quelle | Dokumentierter Status | Tatsächliche Funktion | Reconciliation-Ergebnis |
|---|---|---|---|
| `AGENTS.md` | unmittelbarer Arbeitsvertrag | Arbeitskontext, Modi, Rollen, Entscheidungsrechte, Transparenz, PROMPT/AUSFÜHREN, Wiki- und Toolgrenzen | **aktiv als Einstieg und Policy**; Detailregeln bleiben in ihren Quellen |
| `docs/README.md` | operative Einstiegskarte | Quellen-/Funktionsmatrix, selektiver Kontextstart und Wiki-Freeze | **aktiv als Routing**; keine zusätzliche Zielarchitektur daraus ableiten |
| `docs/governance/decisions.md` – bestätigte Einträge | `bestätigt` | Leanheit, PROMPT-Gate, Nutzungsebene, Toolrouting, Evidenz, externe KI, Komponenten- und Dokumentationsgrenzen | **tragende Regeln** für S0/S1 |
| `docs/governance/decisions.md` – D-009–D-016 | `Entwurf`, praktisch referenziert | Rollen, Transparenz, Toolwahl, Evidenz, Regelkandidaten, Delta-Nachweis | **offen**; keine stillschweigende Bestätigung |
| `docs/governance/role-needs-and-user-stories.md` | bestätigt durch D-021/D-022; praktische Validierung offen | Design-, Development-, Review- und Governance-Bedürfnisse | **fachliche Anforderungsquelle**; Nutzung noch validieren |
| `docs/governance/evaluation-framework.md` | `Entwurf` | Reihenfolge und Kriterien für Evaluation | **Methodenquelle**; nicht selbst als Architekturentscheidung behandeln |
| `docs/governance/evaluation-log.md` | laufende Historie | Befunde, Status, Rückfluss und nächste Schritte | **Historie/Nachweis**; E-073 führt diesen S0-Befund |
| `docs/governance/base-template.md` | `Entwurf – v0.1 testbereit` | generischer Design-System-Grundrahmen, historische Ausbaustufen | **historischer Vergleichspfad**, bis zur Entscheidung kein aktuelles Produktziel |
| `docs/operations/prompting-guide.md` | operative Arbeitsquelle | Auftragsformat, PROMPT/AUSFÜHREN, Rückfragen und Status sichern | **aktiv für Auftrag und Ausführung** |
| `docs/operations/workflows.md` | operative Arbeitsquelle | Figma-Kontext, Evidenz, Rückfrage-/Abbruchlogik | **aktiv für Capability- und Evidenzgrenzen** |
| `docs/operations/checklists.md` | operative Prüfsammlung | Governance-, Tooling-, Test- und Rückflusschecks | **aktiv als Prüfquelle**, Kandidaten bleiben gekennzeichnet |
| `docs/tooling/tooling-map.md` und Figma-Detailquelle | Capability- und Grenzbeschreibung | Funktionswahl und Figma-/externe Toolgrenzen | **aktiv als Referenz**, aber Capability pro Setup prüfen |
| `wiki/` | Pflege pausiert durch E-071 | menschliche Einordnung und Bestand | **pausiert**, keine operative Abhängigkeit |
| `reviews/qa-architecture-research-2026-10-20.md` | unverbindlicher Vorschlag | Research, Zielbild, systemischer Umbaupfad | **Vorschlagsquelle**, nicht kanonische Architektur |
| `reviews/designer-assistance-dev-plan-2026-10-20.md` | unverbindlicher Vorschlag | dev-ready Konzept, Verträge, S0–S6 und Gates | **Vorschlagsquelle**, S0 liefert die Autoritätsklärung |

### 2.1 Autoritätsregel für S1

Bis zu einer menschlichen Statusentscheidung gilt:

1. bestätigte, fallbezogene Decision;
2. `AGENTS.md` und zuständige operative Detailquelle;
3. bestätigte Rollen-/Anforderungsquelle;
4. Evaluation als Befund und Historie;
5. Entwurf, Regelkandidat oder Review-Vorschlag.

Eine praktische Referenz erhöht den Status eines Entwurfs nicht. Ein Review-
Artefakt beschreibt eine Option, solange keine Regelsetzung oder Decision
vorliegt.

## 3. Status- und Nutzungsabgleich

| Inhalt | Status heute | Praktische Nutzung | Konflikt | Vorschlag |
|---|---|---|---|---|
| Arbeitskontext vor jeder Aktion | in `AGENTS.md` ausführbar | wird bei jeder neuen Aktion verwendet | keine bestätigte Decision mit gleicher Reichweite | **aktiv anwenden**, ohne neue Duplizierung |
| PROMPT/AUSFÜHREN | D-018/D-030 bestätigt und in `AGENTS.md` operationalisiert | Auftrag und Ausführung werden getrennt | ältere Dokumente können kürzer formulieren | **operative Quelle bleibt AGENTS/Prompting Guide** |
| Nutzungsebene und schlanker Kontextstart | D-025 bestätigt; `docs/README.md` operationalisiert | Systementwicklung/Fachliche Nutzung werden getrennt | Wiki-Detailpfade sind durch Freeze eingeschränkt | **aktiv**, Wiki nur selektiv |
| Rollen/Transparenz/Toolwahl/Evidenz/Delta | D-009–D-016 Entwurf, aber mehrfach referenziert | faktisch als Arbeitslogik benutzt | Status und Nutzung fallen auseinander | **Regelkandidaten sichtbar halten; vor Bestätigung nicht als Decision ausgeben** |
| Leanheit und Proportionalität | D-017 bestätigt | Vor jeder Erweiterung geprüft | keine | **aktiv** |
| Toolfit und Übernahmeart | D-026, D-028, D-031–D-033 bestätigt | Funktionswahl und externe Dienstgrenzen | tatsächliche Konten-/ISMS-Freigabe bleibt fallbezogen | **aktiv als Gate, keine pauschale Toolfreigabe** |
| Komponenten-/Dokumentationsgrenzen | D-034–D-036 bestätigt | Erstellen, Prüfen und Dokumentieren getrennt | historische Figma-Piloten enthalten ältere Zielverschiebungen | **aktiv für Komponentenfälle, nicht als allgemeine Runtime** |
| Wiki-Pflege | D-019 bestätigt, E-071 Pflege pausiert | Routinepflege ausgesetzt | D-019 beschreibt ursprüngliche Pflegepflicht | **E-071 als Arbeitsstatus beachten; Ablösung von D-019 nur per Decision** |
| v0.1/v0.2/v0.3 | Base Template Entwurf | historische Roadmap und Vergleich | spätere Assistenzarchitektur ist weiter | **historisch markieren oder neu bestätigen; nicht als aktuelles Ziel verwenden** |
| Figma read-only | in Tooling/Workflows beschrieben, konkrete Capability setupabhängig | Zielpfad für spätere Validierung | keine konkrete interne Freigabe dokumentiert | **Kandidat für S2, vor Nutzung prüfen** |
| Figma write/Canvas | extern als Beta und freigabepflichtig beschrieben | nicht im aktuellen Pfad | Edit-/Plan-/Daten- und Review-Risiken | **außerhalb S1/S2; separater späterer Pfad** |
| Code Connect/Design-to-Code/Produktionscode | im Tooling als spätere Funktionen vorhanden | aktueller Designer-QA-Scope benötigt sie nicht | fehlende Codebasis | **außerhalb des aktuellen Zielbilds** |
| Southleft/externe MCPs | Vergleichs-/Toolingmaterial | keine tragende aktuelle Evidenz | Freigabe und Nutzen offen | **beobachten, nicht in S1 voraussetzen** |

## 4. Rollen- und Arbeitsteilungsvertrag

| Rolle | Muss leisten | Darf nicht delegieren bzw. voraussetzen |
|---|---|---|
| Designer:in | fachliche Frage, Gegenstand, Bedeutung, Priorität, Qualitätsurteil, Entscheidung und Abnahme | keine MCP-, Node-ID- oder API-Kenntnis als Bedienvoraussetzung |
| Assistenz/Host | Auftrag klären, Scope begrenzen, passende Capability wählen, Evidenz strukturieren, Unsicherheit markieren, Optionen vorbereiten | Bedeutung, Priorität, fachliche Freigabe, neue Regel oder Ausnahme selbst festlegen |
| Figma-Adapter | konkreten read-only Designkontext, Screenshot, Struktur- oder Variablenwerte liefern | Semantik, Accessibility-Abnahme, Librarystatus oder Vollständigkeit behaupten |
| Development | Verträge, Adapter, Validierung und technische Fehlerpfade implementieren | offene Fachentscheidung technisch vorwegnehmen |
| Review | Evidenz, Scope, Befund, Risiken, Praxistauglichkeit und nächsten Schritt prüfen | keine Regelsetzung oder fachliche Abnahme ersetzen |
| Governance | Quellenautorität, Status, Decision-/Evaluation-Rückfluss und Ausnahmen steuern | operative Routine als neue Decision duplizieren |
| Repository | Regeln, Status, Befunde, Entscheidungen und Learnings auffindbar versionieren | Chatkontext oder unklare Vorschläge kanonisieren |

### 4.1 Verbindlicher Ablauf

```text
Designeranliegen
  → Klärung und PROMPT
  → AUSFÜHREN nach menschlicher Bestätigung
  → kleinste Capability und minimale Quelle
  → Evidenz mit Auslassungen
  → Befund und begrenzte Ableitung
  → menschliche Entscheidung
  → Nachweis und genau ein nächster Schritt
```

Ein Stopp ist bei fehlender Quelle, unklarer Bedeutung, unbestätigter
Capability, unvollständiger Evidenz oder fehlender Freigabe verpflichtend.

## 5. Aktive, historische, pausierte und ausgeschlossene Pfade

| Pfad | Status | Nutzen heute | Pflege-/Abhängigkeitskosten | Umgang |
|---|---|---|---|---|
| `AGENTS.md` + operative Quellen | aktiv | Arbeitssteuerung und Quellenrouting | gering, wenn Details nicht dupliziert werden | erhalten und gezielt referenzieren |
| bestätigte Decisions D-017/D-018/D-025/D-026/D-028/D-029/D-031–D-036 | aktiv | Leitplanken für Agent, Tooling und Governance | Statuspflege nötig | als S0/S1-Grenzen verwenden |
| Rolle/User Stories | aktiv mit Validierungslücke | Designer- und Review-Abnahme | praktische Tests offen | als Anforderungsquelle verwenden |
| Evaluation Log und Reviews | aktiv als Nachweis | Historie, Lernen, Status | keine aktuelle kompakte Steuerung | verlinken, nicht als alleinige Policy verwenden |
| read-only Figma-Evidenz | Zielkandidat | konkreter Designzustand für Befunde | Zugriff, Plan, ISMS, Scope | erst in S2 nach Freigabe prüfen |
| v0.1/v0.2/v0.3 | historisch/offen | dokumentiert Aufbaugeschichte | erzeugt Zielbildkonflikte | markieren oder später per Decision ablösen |
| D-009–D-016 | offene Regelkandidaten | enthalten nützliche Schutzlogik | Status-/Doppelpflege | validieren, bestätigen, zusammenführen oder verwerfen |
| Wiki-Routinepflege | pausiert | derzeit kein belegter zusätzlicher Nutzen | hoher Kontext-/Synchronisationsaufwand | nicht reaktivieren |
| Figma-Write/Canvas | ausgeschlossen aus S0/S1 | späterer Sonderfall | Edit, Kosten, Review, Daten | separater freigegebener Pfad |
| Code Connect/Design-to-Code/Handoff | außerhalb | für aktuelle Rolle nicht erforderlich | fehlende Codebasis und zusätzliche Abhängigkeit | nicht in S1–S5 voraussetzen |
| zusätzliche MCP-/SDK-/Multi-Agenten-Runtime | außerhalb | kein belegter Wiederholungsbedarf | hohe Pflege-/Token-/Vendorlast | erst nach S5 als offene Option prüfen |

## 6. Migrations- und Ablöseplan

### M0 – Schutzwirkung sichern

Vor jeder Kürzung wird für den betroffenen Inhalt Zweck, Schutzwirkung,
Zielquelle, Status und Link erfasst. Es wird nichts gelöscht. Alle folgenden
Schritte bleiben Vorschläge.

### M1 – D-009 bis D-016 auflösen

- vorhandene Referenzen und tatsächliche Nutzung je Eintrag erfassen;
- identische Schutzwirkungen mit bestätigten AGENTS-/Operations-Regeln
  abgleichen;
- Ergebnis je Eintrag als `bestätigen`, `zusammenführen`, `Entwurf behalten`,
  `ablösen` oder `verwerfen` vorlegen;
- eine Bestätigung ausschließlich über `REGEL SETZEN` oder Decision-Log-
  Statuswechsel vornehmen.

**Risiko:** Eine pauschale Bestätigung würde Entwurf und Praxis verwechseln.

### M2 – D-019 und E-071 abgleichen

- D-019 bleibt als bestätigte ursprüngliche Wiki-Entscheidung sichtbar;
- E-071 bleibt der aktuelle vorläufige Freeze für Routinepflege;
- die Auflösung, ob E-071 eine Ausnahme, zeitliche Einschränkung oder
  Ablösung von D-019 ist, benötigt eine eigene menschliche Decision;
- bis dahin gelten keine neuen Routinepflegepflichten.

### M3 – Base-Template-Roadmap einordnen

- v0.1/v0.2/v0.3 als historische Entwicklung markieren;
- den dev-ready Plan als Vorschlagsziel separat halten;
- erst nach menschlicher Bewertung entscheiden, ob eine neue Roadmap oder
  eine Ablösung der alten Staffelung nötig ist;
- keine Roadmapstufe als technische Lieferzusage behandeln.

### M4 – Tooling Map entflechten

- aktive Designer-QA-Capabilities von Code-/Write-/Vergleichspfaden trennen;
- je Capability Status, Scope, Datenklasse, Berechtigung und Quelle ergänzen;
- Southleft und weitere externe Pfade nur bei belegtem Nutzen und Freigabe
  weiterführen;
- keine Toolzeile löschen, bevor ihre Funktion historisch oder neu zugeordnet
  ist.

### M5 – Wiki-Freeze erhalten

- Detailseiten nicht löschen oder routinemäßig synchronisieren;
- `wiki/README.md` als sichtbaren Freeze-Status erhalten;
- eine Reaktivierung ausschließlich über ein konkretes Nutzungsszenario,
  Relevanzprüfung und menschliche Entscheidung vornehmen.

## 7. Auswirkungen auf den dev-ready Plan

Der dev-ready Plan bleibt als Vorschlag verwendbar, wird aber in drei Punkten
begrenzt:

1. **S0 ist Voraussetzung:** S1 darf erst nach menschlicher Bewertung der
   Quellen-/Statusmatrix starten.
2. **Verträge sind Kandidaten:** WorkRequest, EvidencePacket, Finding,
   Decision und RunRecord sind noch kein kanonisches Schema.
3. **Figma bleibt Capability-Kandidat:** S2 darf erst nach Setup-, Daten- und
   Integrationsfreigabe eine konkrete Funktion prüfen.

Der Rest des Plans bleibt als Zielbild und Optionsraum bestehen. Insbesondere
S6 (eigene Runtime) bleibt abhängig von einem später belegten Wiederholungs-
nutzen.

## 8. Minimale Voraussetzungen für S1

S1 – strukturierter Arbeits- und Befundvertrag – ist bereit, wenn:

- die Autoritätsmatrix menschlich bestätigt oder mit konkreten Korrekturen
  zurückgegeben wurde;
- D-009–D-016 für den vorgesehenen Arbeitsgang einen sichtbaren Status haben;
- D-019/E-071 nicht widersprüchlich als Routinepflicht interpretiert werden;
- die Nicht-Ziele (Code, Write, Runtime, Wiki-Reaktivierung) bestätigt sind;
- die minimalen Felder für WorkRequest, EvidencePacket, Finding und Decision
  als Kandidat akzeptiert oder begrenzt werden;
- Format und Speicherort des Vertrags entschieden sind;
- ein menschlich verantworteter Validierungsfall benannt ist;
- keine Figma- oder externe Schreibfreigabe stillschweigend angenommen wird.

Wenn eine Voraussetzung fehlt, bleibt S1 `blockiert` oder `offen`; es wird kein
Ersatzumfang erfunden.

## 9. Nicht bewertete Bereiche und Risiken

- praktische Verständlichkeit des Arbeitsvertrags für Designer:innen wurde
  noch nicht an einem echten Fall geprüft;
- die konkrete Figma-Capability, der Account-/Planstatus und die interne
  ISMS-Freigabe sind nicht bewertet;
- die optimale maschinenlesbare Repräsentation ist offen;
- tatsächliche Pflegekosten eines strukturierten Befundmodells sind offen;
- eine eigene Runtime ist weder erforderlich noch ausgeschlossen, aber noch
  nicht durch Wiederholungsbedarf begründet;
- die fachliche Validierung der Rollenquelle ist ausstehend;
- die Auswirkungen eines D-019/E-071-Statuswechsels sind noch nicht als
  Decision dokumentiert.

Diese Punkte sind keine Mängelbehauptungen. Sie sind offene Prüf- oder
Entscheidungsfelder.

## 10. Reconciliation-Ergebnis

| Bereich | S0-Status |
|---|---|
| Arbeitsvertrag und bestätigte Governance | ausreichend als Ausgangspunkt |
| Rollen- und Arbeitsteilung | inhaltlich vorhanden, Status-/Praxisabgleich teilweise offen |
| Quellenautorität | grundsätzlich geordnet, D-009–D-016 und D-019/E-071 offen |
| Figma-Evidenz | Zielrichtung klar, konkrete Capability/Freigabe offen |
| Toolingpfade | zu breit; aktive und spätere Pfade müssen getrennt werden |
| Wiki | Routinepflege pausiert; keine Reaktivierung im S0 |
| Dev-ready Plan | als Vorschlag verwendbar, S1 abhängig von menschlicher Freigabe |
| Umsetzung | noch nicht freigegeben |

## 11. Genau ein nächster menschlicher Entscheid

Soll die vorgeschlagene Autoritäts- und Statusmatrix als Arbeitsgrundlage für
S1 akzeptiert werden, einschließlich der folgenden Grenzen?

- D-009 bis D-016 bleiben bis zur Einzelklärung offen;
- D-019 bleibt sichtbar, E-071 begrenzt die aktuelle Wiki-Routinepflege;
- v0.1/v0.2/v0.3 werden nicht als aktuelle Lieferroadmap behandelt;
- S1 beginnt mit dem strukturierten Vertrag, ohne Runtime oder Figma-Schreiben;
- der konkrete Figma-Read-only-Slice wird erst nach Setup-/ISMS-Prüfung gewählt.

Bis zu dieser Entscheidung bleibt S1 `nicht freigegeben`.
