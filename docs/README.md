# Operative Projektartefakte

Diese Dokumentation ist die präzise Arbeitsgrundlage für Agenten und für
gezielte fachliche Nachweise. Die menschliche Einordnung steht getrennt in der
vorläufig pausierten [Projekt-Wiki](../wiki/README.md); verbindliche Regeln
stehen ausschließlich in den zuständigen `docs/`- und Governance-Quellen.

## Status der Wiki

Die Wiki bleibt als bestehender Kontext erhalten, wird aber bis zu einer
späteren Relevanzprüfung nicht routinemäßig gepflegt oder vollständig geladen.
Neue Regeln, Statuswerte und Arbeitsabläufe werden ausschließlich in den
zuständigen Quellen unter `docs/` und in `AGENTS.md` geführt.

| Bereich | Zweck | Artefakte |
|---|---|---|
| Governance | Entscheidungsrechte, Rollenanforderungen, Baseline und Evaluation. | [Base Template](governance/base-template.md), [Decisions](governance/decisions.md), [Role Needs and User Stories](governance/role-needs-and-user-stories.md), [Evaluation Framework](governance/evaluation-framework.md), [Evaluation Log](governance/evaluation-log.md) |
| Foundations | Projektübergreifende fachliche Regeln, Begriffe und Standards. | [Design Principles](foundations/design-principles.md), [Semantic Model](foundations/semantic-model.md), [Standards](foundations/standards.md) |
| Operations | Arbeitsabläufe, Prozess-/Governance-/Tooling-Prüfungen und Auftragsformate. | [Workflows](operations/workflows.md), [Checklists](operations/checklists.md), [Prompting Guide](operations/prompting-guide.md) |
| Tooling | Werkzeugauswahl sowie technische Fähigkeiten und Grenzen. | [Tooling Map](tooling/tooling-map.md), [Figma MCP Tooling](tooling/figma-mcp-tooling.md), [Southleft Tooling](tooling/southleft-tooling.md) |
| Templates | Kopiervorlagen für spätere Projektinstanzen. | [Project Template](../templates/project-template.md) |

Die verbindliche Einstiegskarte für Agenten bleibt [AGENTS.md](../AGENTS.md).

## Quellen- und Funktionsmatrix

Die Trennung verhindert, dass fachliche Nutzung mit der Weiterentwicklung des
Regel- und Toolingsystems gleichgesetzt wird.

| Gegenstand | Verbindliche Quelle | Kernfunktion | Abnahme |
|---|---|---|---|
| Fachliche Nutzung | `AGENTS.md` plus gezielt geladene Wiki-Einordnung und referenzierte Foundations/Standards | Zweck, Wirkung, Grenzen und Einordnung im Arbeitsprozess vermitteln. | verständlich, selektiv lesbar und fachlich einordenbar |
| Systementwicklung | Governance, Operations und Tooling | Regeln, Quellen, Tooling und Dokumentationsstrukturen reproduzierbar prüfen oder ändern. | Quelle, Scope, Freigabe, Test und Rückführung prüfbar |
| Arbeitsauftrag | Prompting Guide | Ziel, Gegenstand, Modus, Rolle, Aktion, Grenzen und Abnahme explizit machen. | kein entscheidender Kontext bleibt implizit |
| Qualitätsnachweis | Evaluation Framework und Log | Tooling-, Struktur-, Fach- und Menschenbefund getrennt ausweisen. | Umfang, Evidenz, Lücken und nächster Schritt belastbar |

## Bedarfsorientierter Kontextstart (Pilot)

Dieser Pilot verhindert, dass ein neuer Chat entweder nur den Arbeitsvertrag
liest und Projektkontext verliert oder pauschal alle Quellen lädt. Er ergänzt
`AGENTS.md`, ersetzt aber keine Entscheidung, Quelle oder menschliche
Freigabe.

| Anliegen | Minimaler Kontext | Danach nur bei Bedarf | Bewusst nicht lesen |
|---|---|---|---|
| Konkrete Qualitäts- oder Komponentenfrage | `AGENTS.md` → [Wiki-README](../wiki/README.md) nur zur Einordnung → passender Qualitätsweg | Foundations, Figma-/Tooling-Quelle, konkrete Evaluation | Wiki-Detailseiten, übrige Logs und fachfremde Tooling-Details |
| Systementwicklung, Regel oder Tooling | `AGENTS.md` → diese Übersicht → passende Decision oder Evaluation | Checklists, Prompting Guide, Tooling-Detailquelle | Wiki- und Foundations-Details ohne Bezug |
| Fortsetzung eines folgenreichen Strangs | `AGENTS.md` → letzter relevanter Befund → zugehörige Decision | gezielte Detailquelle; Wiki-Detailseiten nur bei ausdrücklicher Relevanz | vollständige Historie ohne Bezug |
| Verbundenes Anliegen | `AGENTS.md` → Wiki-README nur zur Einordnung und diese Übersicht | je Ebene passende Qualitätsquelle sowie Decision/Evaluation | Vermischung der Evidenz, Abnahme oder Entscheidung beider Ebenen |
| Neues oder unklares Anliegen | `AGENTS.md` → [Wiki-README](../wiki/README.md) nur zur Einordnung und diese Übersicht | nach Einordnung nur passende Quellen | Volllektüre von Wiki, `docs/` oder Logs |

Der Agent sucht nach Gegenstand, Decision, Evaluation oder Stichwort und
liest erst dann die Fundstelle. Bei einer folgenreichen Fortsetzung dient der
Anschlusskern als Kurzprüfung: Absicht, belastbare Erkenntnis, Geltung oder
Grenze, offene Frage und nächster Schritt. Der Pilot erzeugt keine neue
Handover-Datei und keine automatische Kontextsammlung.

`START CHAT` ist die optionale Kurzform, um diesen Pfad ausdrücklich
anzufordern. Der Agent übernimmt den erkennbaren Arbeitsstand selbst; nur bei
fehlendem Anhaltspunkt liest er beide Einstiegskarten und weist die Einordnung
als vorläufig aus. Für das erst durch die konkrete Aufgabe benötigte Werkzeug wird
dessen Einsatzbereitschaft geprüft: Verfügbarkeit, tatsächlicher Scope,
Zugriff oder Laufzeit sowie belastbare Alternative. Nicht benötigte Tools
werden weder geladen noch getestet; eine konfigurierte Verbindung zählt nicht
als Funktionsnachweis.

### Detailmigration ohne Funktionsverlust

| Inhalt | Zielquelle | Erhaltene Funktion |
|---|---|---|
| Projektartefakte, Base-/Project-Template und Wiki-Zweck | diese Übersicht, [Base Template](governance/base-template.md) und Wiki | Orientierung und Abgrenzung |
| Testmodus, Evidenz und Entscheidungslogik | [Base Template](governance/base-template.md) | Moduswahl, Rückfluss und Freigabe |
| Rollen, Auftragsformat sowie `PROMPT`/`AUSFÜHREN` | [Prompting Guide](operations/prompting-guide.md) und Governance | verständliche Aufträge ohne impliziten Kontext |
| Evaluation, `Status sichern` und `WIKI PRÜFEN` | [Evaluation Framework](governance/evaluation-framework.md), [Checklists](operations/checklists.md) und Evaluation Log | Prüfung, Nachweis und Rückführung |
| Figma-/Southleft-Abgrenzung und Funktionswahl | [Tooling Map](tooling/tooling-map.md) und Tooling-Detailquellen | passgenaue, nicht simulierte Toolauswahl |
| fachliche Standards und operative Detailregeln | [Foundations](foundations/design-principles.md) und [Operations](operations/workflows.md) | fachliche Wiederverwendung und ausführbare Prüfung |

Bei einer Strukturänderung wird zuerst geprüft, welche Zeilen und Funktionen
betroffen sind. Eine Quelle wird erst verkürzt oder entfernt, wenn die
betroffene Funktion in der Zielquelle auffindbar dokumentiert und verlinkt ist.
