# Steuerung und Quellen

Diese Seite erklärt nicht jede Regel im Detail. Sie zeigt, **welche Art von
Frage** in welchem Steuerungsartefakt verbindlich beantwortet wird.

## Orientierungslandkarte

| Wenn Sie wissen oder bewerten wollen … | Lesen Sie zuerst | Verbindliche Quelle |
|---|---|---|
| Wozu dient das Projekt, und wo steht es? | [Projektbild](project-portrait.md) | [Projektbild](project-portrait.md); Details in den verlinkten Quellen |
| Wie greifen Base Template, Project Template und Projektkit ineinander? | [Arbeitsmodell](working-model.md) | [Base Template](../docs/governance/base-template.md) |
| Welche übergreifende Regel gilt für eine Arbeit? | [Arbeitsmodell](working-model.md) | [Base Template](../docs/governance/base-template.md) |
| Was dürfen Agenten entscheiden oder ändern? | [Arbeitsmodell](working-model.md) | [Mensch–Maschine-Arbeitsteilung in AGENTS.md](../AGENTS.md) und [Base Template](../docs/governance/base-template.md) |
| Warum wurde etwas entschieden oder freigegeben? | [Projektbild](project-portrait.md) und [Steuerung und Quellen](governance-and-sources.md) | [Decision Log](../docs/governance/decisions.md) |
| Wie wird ein Auftrag verständlich formuliert? | [Arbeitsmodell](working-model.md) | [Prompting Guide](../docs/operations/prompting-guide.md) |
| Welches Werkzeug passt zu einer Figma- oder Design-System-Aufgabe? | [Arbeitsmodell](working-model.md) | [Tooling Map](../docs/tooling/tooling-map.md); externe Wissenswerkzeuge nur bei nachweislich passenden Treffern verwenden |
| Darf ein KI-gestützter externer Dienst für den Gestaltungsauftrag eingesetzt werden? | [Tooling Map](../docs/tooling/tooling-map.md#verbindliche-einsatzgrenze-fur-ki-gestutzte-externe-dienste) | [Tooling Map](../docs/tooling/tooling-map.md#verbindliche-einsatzgrenze-fur-ki-gestutzte-externe-dienste) und [Decision Log](../docs/governance/decisions.md#d-031--ki-gestutzte-externe-dienste-im-gestaltungskontext) |
| Wie wird der Arbeits- und Steuerungsprozess vor einer Änderung geprüft? | [Arbeitsmodell](working-model.md) | [Checklists](../docs/operations/checklists.md) – Prozess-, Governance-, Tooling- und Transparenzqualität; keine Design-QA |
| Welche Funktion haben die Checklists? | [Steuerung und Quellen](governance-and-sources.md) | [Checklists](../docs/operations/checklists.md) – operative Prüfungen für Agenten und Freigaben, keine fachliche Design- oder visuelle Qualitätssicherung |
| Wo gehört erklärender oder operativer Inhalt hin? | [Steuerung und Quellen](governance-and-sources.md) | [AGENTS.md](../AGENTS.md) und [Evaluation Framework](../docs/governance/evaluation-framework.md) – Zielgruppen- und Schichtpassung |
| Wie bewerten wir Steuerung, Verständlichkeit und Fortschritt? | [Evaluation und Review](evaluation-and-review.md) | [Evaluation Framework](../docs/governance/evaluation-framework.md) und [Evaluation Log](../docs/governance/evaluation-log.md) |
| Ist die Wiki selbst verständlich und sinnvoll geschnitten? | [Evaluation und Review](evaluation-and-review.md) | Aktiver Steuerbefehl `WIKI PRÜFEN`; Kriterien im [Evaluation Framework](../docs/governance/evaluation-framework.md) und in den [Checklists](../docs/operations/checklists.md) |
| Welche Bedürfnisse haben die Arbeitsrollen an die Wiki? | [Rollen und User Stories](../docs/governance/role-needs-and-user-stories.md) | Rollen und Entscheidungsrechte in [AGENTS.md](../AGENTS.md); Vermittlung in der Wiki |
| Wie beurteile ich Qualität eines generischen Bausteins und nutze KI passend? | [Qualität gestalten – mit KI-Tooling als Unterstützung](quality-and-ai-tooling.md) | [Base Template](../docs/governance/base-template.md), [Tooling Map](../docs/tooling/tooling-map.md) und [Evaluation Framework](../docs/governance/evaluation-framework.md) |
| Wie verbessern Praxisbefunde Regeln und Tooling? | [System entwickeln und aus der Praxis lernen](system-development-and-learning.md) | [Evaluation Log](../docs/governance/evaluation-log.md), [Decision Log](../docs/governance/decisions.md) und [Tooling Map](../docs/tooling/tooling-map.md) |
| Wie bewerte ich ein neues Fundstück, ohne es automatisch aufzunehmen? | [System entwickeln und aus der Praxis lernen](system-development-and-learning.md#neue-fundstucke-einordnen) | [Workflow für neue Fundstücke](../docs/operations/workflows.md#neue-fundstucke-bewerten-und-integrieren) und [D-032](../docs/governance/decisions.md#d-032--bewertung-und-integrationsgrad-neuer-fundstucke) |
| Welcher Kontext gehört in Figma, Repository, Code oder Wiki? | [Figma als Kontext für Qualitätsarbeit](figma-context-and-handoff.md) | [Tooling Map](../docs/tooling/tooling-map.md), [Figma MCP Tooling](../docs/tooling/figma-mcp-tooling.md) und [Base Template](../docs/governance/base-template.md) |

## Wie Steuerung lesbar bleibt

Die Steuerungsdateien sind absichtlich nach ihrem operativen Zweck getrennt.
Die Wiki verbindet sie für Menschen entlang von Verständnis- und
Bewertungsfragen. Sie darf Zusammenhänge erklären und den Entwicklungsstand
zusammenfassen, aber keine abweichenden Regelversionen erzeugen.

## Menschliche Einordnung und operative Prüfung

| Wenn der Inhalt ... | gehört er primär nach ... |
|---|---|
| erklärt, motiviert, Begriffe vermittelt oder Zusammenhänge einordnet | Wiki |
| eine ausführbare Regel, Checkliste, Statuslogik oder einen Prüfschritt enthält | `docs/` |

Vor einer Änderung wird geprüft, ob Zielgruppe, Zweck, Inhaltstyp und Detailtiefe
zum Artefakt passen. Eine operative Datei wird nicht mit Vermittlungstexten
angereichert; eine Wiki-Seite wird nicht zur zweiten Regelquelle.

## Lebendige Pflege

Bei jeder folgenreichen Entwicklungsänderung wird geprüft und bei Bedarf im
selben Arbeitsschritt ergänzt:

- Was hat sich im Gesamtbild verändert?
- Welche Steuerungsdatei ist neu oder anders einzuordnen?
- Welche Entscheidung ist für Menschen relevant?
- Welche offene Frage, Grenze oder nächste Prüfung ist nun sichtbar?

So kann die Wiki als laufende Transparenz- und Verständnisschicht mit der
Entwicklung wachsen, ohne zur zweiten operativen Dokumentation zu werden.
