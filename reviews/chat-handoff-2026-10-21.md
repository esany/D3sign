# Chat-Handoff: Repo-first Fortsetzung

**Stand:** 2026-10-21  
**Status:** Übergabebefund  
**Autorität:** Anschlussbefund; verbindliche Regeln bleiben in den verlinkten `docs/`-Quellen.

## Zweck

Der bisherige Chat ist zu lang geworden und darf kein Wissensmonopol bleiben.
Dieser Befund überführt den belastbaren Anschlusskern in das Repository, damit
ein neuer Chat ohne vollständige Transkriptlektüre weiterarbeiten kann.

## Aktuelles Zielbild

Das Repository unterstützt Designer:innen bei fachlich konkreten
Qualitätsfragen. Es ist keine autonome Designmaschine, kein generischer
Agentenruntime und kein Design-to-Code-System.

Der verbindliche Arbeitsweg lautet:

```text
Designerfrage
  → Gegenstand, Scope und Abnahme
  → kleinste passende Quelle und Capability
  → Evidenz mit sichtbaren Grenzen
  → fachlich verständlicher Befund
  → menschliche Bewertung und Decision
  → Repository-Nachweis
```

Der Designer verantwortet Zweck, Bedeutung, Priorität, Qualität, Zustände,
Accessibility und Abnahme. Die Assistenz klärt, strukturiert, prüft Quellen,
markiert Unsicherheit und bereitet Entscheidungen vor. Sie ersetzt keine
fachliche Entscheidung und setzt keine Regel stillschweigend.

## Verbindliche Anschlussquellen

- [`AGENTS.md`](../AGENTS.md) – Arbeitsvertrag, Grenzen und Transparenz
- [`docs/README.md`](../docs/README.md) – Quellen- und Funktionsrouting
- [`docs/governance/decisions.md`](../docs/governance/decisions.md) – Status und Entscheidungen
- [`docs/governance/evaluation-log.md`](../docs/governance/evaluation-log.md) – Nachweis und Rückfluss
- [`docs/operations/prompting-guide.md`](../docs/operations/prompting-guide.md) – Auftragsformat und `PROMPT`/`AUSFÜHREN`
- [`reviews/repo-deep-audit-and-operationalization-2026-10-20.md`](repo-deep-audit-and-operationalization-2026-10-20.md) – Systembefund, Anforderungen und Gates

## Überführte Chat-Erkenntnisse

| Inhalt | Repo-Ziel | Ergebnis |
|---|---|---|
| Designerrolle, Pain Points und Unterstützungsbedarf | `AGENTS.md`, Governance, Role Needs, Deep Audit | gesichert und verlinkt |
| Mensch–Maschine-Arbeitsteilung | `AGENTS.md`, Base Template, Deep Audit | gesichert |
| Gate-basierter Arbeitsweg | D-037, Deep Audit | bestätigt und aktuelle Grundlage |
| D-009 Rollen | `AGENTS.md`, Role Needs | `abgelöst` |
| D-010 Transparenz | `AGENTS.md`, Base Template, Checklists, Evaluation | `abgelöst` |
| D-013 Toolwahl | `AGENTS.md`, Prompting Guide, Tooling Map | `abgelöst` |
| D-014 Evidenz vor Ableitung | `AGENTS.md`, Evaluation Framework, Workflows | `abgelöst` |
| D-015 Regelkandidaten / `REGEL SETZEN` | `AGENTS.md`, Decision Log | `abgelöst` |
| D-016 Delta-Nachweis | `AGENTS.md`, Evaluation Log | `abgelöst` |
| D-011 generischer Foundation-Baustein | Decision Log und Foundations | bleibt `Entwurf` |
| D-012 Ausbaustufen | Decision Log und historische Reviews | bleibt `Entwurf`, historische Roadmap |
| D-019 Wiki | Decision Log | bleibt `bestätigt` |
| E-071 Wiki-Freeze | Evaluation Log | bleibt aktiv |

## Historisch oder nicht aktuell

- S0-, S2- und Dev-ready-Dokumente bleiben als Nachweis erhalten, sind aber
  keine aktuelle Ausführungsroadmap.
- Die Toggle-Reviews bleiben historische Evidenz und kein allgemeines
  Auditformat.
- Der gemergte PR und der öffentliche Issue-Abgleich liefern Kontext, erzeugen
  aber keine neue Issue-Struktur.

## Bewusst nicht übernommen

- keine Figma-, Token- oder Komponentenänderung;
- keine Wiki-Aktualisierung oder Wiki-Reaktivierung;
- keine neue Runtime, kein Code Connect und keine neue MCP-Abhängigkeit;
- keine generische Audit- oder Agentenplattform;
- keine fachliche Pass-/Fail- oder Accessibility-Aussage ohne konkreten
  Gegenstand und menschliche Bewertung.

## Verbleibende offene Punkte

1. D-011 benötigt eine gesonderte Foundation-Bewertung.
2. D-012 bleibt historische Roadmap, bis eine neue Ausbaustufenentscheidung
   ausdrücklich getroffen wird.
3. D-019 und E-071 bleiben getrennt sichtbar; der Wiki-Freeze gilt weiter.

## Nächster Schritt

Im neuen Chat einen konkreten, begrenzten Designerfall nach dem Gate-Vertrag
starten. Zuerst Frage, Gegenstand, Nutzungsebene, Rolle, Scope und Abnahme
festlegen; danach nur die kleinste passende Quelle und Capability verwenden.

## Übergaberegel für den neuen Chat

Dieser Befund ist kein Ersatz für die verbindlichen Quellen. Der neue Chat
liest zuerst `AGENTS.md`, `docs/README.md` und diesen Handoff, übernimmt den
Anschlusskern und prüft jede operative Aussage gegen ihre Zielquelle. Der alte
Chat wird nicht als zusätzliche Regelquelle rekonstruiert.

## Handoff-Prompt

```text
START CHAT

Arbeite repo-first. Lies zuerst AGENTS.md, docs/README.md und
reviews/chat-handoff-2026-10-21.md. Lies danach nur die dort verlinkten
Entscheidungs-, Evaluations- und Review-Quellen, die für den konkreten Auftrag
benötigt werden.

Übernimm das aktuelle Zielbild, die Designerrolle, die Arbeitsteilung, den
Gate-Vertrag, die Statuslage und den einen nächsten Schritt aus dem Handoff.
Behandle den Handoff als Anschlussbefund, nicht als neue Regelquelle. Prüfe
jede operative Aussage gegen ihre verbindliche Zielquelle. Lies den alten Chat
nicht erneut und rekonstruiere keine verworfenen Ansätze.

Beginne mit Ziel, Gegenstand, Nutzungsebene, Modus, Rolle, Scope, Nicht-Scope,
Quellen, Toolbedarf und Abnahme. Stoppe vor Änderungen, wenn eine Quelle,
Entscheidung oder menschliche Freigabe fehlt.
```
