# Figma als Kontext für Qualitätsarbeit

## Worum es hier geht

Diese Seite wird verwendet, wenn Figma für eine konkrete Qualitätsfrage
relevanten Kontext liefern kann. Sie ist kein Ausgangspunkt des Systems:
Qualitätsstandards und die menschliche Gestaltungsentscheidung stehen im
Vordergrund. Figma und KI machen nur begrenzte, sichtbare Informationen
nutzbar.

## Wenn Figma der passende Kontext ist

| Wenn du gerade wissen musst … | Beginne hier | Ergebnis |
|---|---|---|
| Welche Qualitätsfrage beantwortet der sichtbare Figma-Kontext? | [Qualitätskontext aus Figma](figma-understand.md) | Ein begrenzter, fachlich eingeordneter Kontext. |
| Was braucht Development für eine verlässliche Umsetzung? | [Qualität übergeben und abnehmen](figma-handoff.md) | Eine prüfbare Übergabe mit offenen Punkten und Abnahme. |
| Was lernen wir aus einer Lücke, einem Test oder einem Toolproblem? | [System entwickeln und aus der Praxis lernen](system-development-and-learning.md) | Ein Lernbefund, keine automatische neue Regel. |

## Arbeitsteilung

Design bestimmt Absicht, Wirkung und Priorität. Development prüft
Umsetzbarkeit und macht technische Folgen sichtbar. Review prüft Evidenz,
Grenzen und Abnahme. Der Agent wählt die kleinste passende Funktion, weist
ihren tatsächlichen Scope aus und fragt nur nach, wenn Quelle, Umfang,
zulässige Aktion oder Abnahme sonst nicht sicher bestimmbar sind.

Verbindliche Regeln, Tooling-Scope und Freigaben stehen in `docs/`. Die Wiki
erklärt, welche Bedeutung sie für die nächste menschliche Entscheidung haben.

## Status und Grenze

Der Figma-/Library-Zugriff ist bisher nur als begrenzter read-only Test
bewertet. Sichtbare Informationen sind kein Nachweis für nicht ausgelesene
Strukturen; ein Tooling-Limit ist kein Gestaltungsfehler. Die belastbaren
Testbefunde stehen in [E-009](../docs/governance/evaluation-log.md) und
[E-015](../docs/governance/evaluation-log.md).

**Nächster Schritt:** Von einer konkreten Qualitätsfrage in
[Qualität gestalten – mit KI-Tooling als Unterstützung](quality-and-ai-tooling.md)
starten und Figma nur nutzen, wenn es dafür passenden Kontext liefert.
