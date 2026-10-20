# Projekt-Wiki

> **Status: Pflege pausiert.** Diese Wiki bleibt als bestehender Kontext
> erhalten, ist derzeit aber keine verbindliche Quelle und wird nicht bei
> Routineänderungen fortgeschrieben. Verbindliche Regeln stehen in
> [`AGENTS.md`](../AGENTS.md) und [`docs/`](../docs/README.md). Detailseiten
> werden nur bei ausdrücklichem Wiki-Auftrag oder einer gezielten
> Relevanzprüfung gelesen.

Diese Wiki ist der Einstieg für Menschen. Sie erklärt, **warum** das Projekt
so aufgebaut ist, **wo es steht** und **was bei Entscheidungen zu bewerten
ist**. Sie ist keine zweite Fassung der operativen Regeln unter `docs/`.

Für neue Beteiligte ist die wichtigste Orientierung: Die Wiki trennt sichtbar,
was der Agent regelgeleitet ausführt, was ein Mensch steuert oder freigibt und
welche Fragen noch offen sind. Kein Ergebnis setzt Wissen aus früheren Chats
voraus.

## Start ohne Vorwissen

Wähle zuerst die Frage, die du gerade beantworten willst. Das Wiki trennt die
fachliche Qualitätsarbeit bewusst von der Entwicklung des Werkzeugs selbst.

1. **Ich möchte einen Baustein qualitativ gestalten, prüfen oder mit KI
   unterstützen.** Beginne bei [Qualität gestalten – mit KI-Tooling als
   Unterstützung](quality-and-ai-tooling.md).
2. **Ich möchte verstehen, wie Regeln, Tooling und Praxiswissen das System
   verbessern.** Beginne bei [System entwickeln und aus der Praxis
   lernen](system-development-and-learning.md).
3. **Ich möchte den Projektstand oder eine Steuerungsentscheidung einordnen.**
   Lies [Projektbild](project-portrait.md), [Arbeitsmodell](working-model.md)
   oder [Steuerung und Quellen](governance-and-sources.md).

## Menschenschicht und Maschinenschicht

Die Wiki ist die **Menschenschicht**. Sie erklärt Bedeutung, Auswirkungen,
Status und nächste Entscheidungen. Sie setzt weder Kenntnis der
Repository-Struktur noch ein internes Arbeitsmodell voraus.

`AGENTS.md` und `docs/` bilden die **Maschinenschicht**. Dort stehen
ausführbare Regeln, Quellen und Steuerungslogik. Die Wiki verweist darauf,
statt diese Inhalte vollständig zu wiederholen.

Eine Wiki-Seite ist erst verständlich, wenn eine dritte Person ohne Chat-Verlauf
erkennen kann: **Worum geht es? Warum ist es relevant? Was macht das System?
Was muss ich prüfen oder entscheiden? Was ist der nächste Schritt?**

## Die zwei Bereiche

### Qualität in der Gestaltung

- [Qualität gestalten – mit KI-Tooling als Unterstützung](quality-and-ai-tooling.md)
  – Qualitätsdimensionen, Arbeitsteilung und passende KI-Unterstützung.
- [Qualitätskontext aus Figma](figma-understand.md) – Figma nur als begrenzte
  Evidenzquelle für eine Qualitätsfrage nutzen.
- [Qualität übergeben und abnehmen](figma-handoff.md) – Umsetzung gemeinsam
  prüfbar machen.

### System entwickeln und lernen

- [System entwickeln und aus der Praxis lernen](system-development-and-learning.md)
  – Lessons Learned, Tooling-Betriebsfähigkeit und leaner Rückfluss.
- [Projektbild](project-portrait.md) – Ziel, Gegenstand und aktueller Stand.
- [Arbeitsmodell](working-model.md) – Ebenen, Arbeitsteilung und der
  Unterschied zwischen Test und Systementwicklung.
- [Evaluation und Review](evaluation-and-review.md) – Qualität,
  Verständlichkeit und Entwicklungsfortschritt prüfen.
- [Steuerung und Quellen](governance-and-sources.md) – verbindliche Quelle
  für eine Regel, Entscheidung oder Tooling-Frage finden.
- [Schnellsteuerung für Menschen](quick-controls.md) – Arbeitsdimension
  einordnen und danach den passenden, klar begrenzten Befehl wählen.
- [SharePoint-Wissen zum Design Review: Einordnung](sharepoint-design-review-einordnung.md)
  – erhobene Vergleichsquelle, Relevanz und bewusst nicht übernommene
  organisationsspezifische Abläufe.

## Leseregel

Die Wiki folgt menschlichen Fragen wie „Worum geht es?“, „Wo stehen wir?“ und
„Was kann ich bewerten?“. Sie muss deshalb nicht die Ordner- oder
Dateistruktur unter `docs/` spiegeln. Wer eine Regel, Quelle oder Entscheidung
nachvollziehen möchte, folgt von dort gezielt in das verlinkte Fachartefakt.
Dadurch bleibt die operative Dokumentation präzise und die menschliche
Orientierung verständlich.

## Pflege

Die Wiki wird im selben Arbeitsschritt aktualisiert, wenn sich Projektzweck,
Strukturverständnis, Entwicklungsstand, Steuerungslogik oder eine für Menschen
relevante Entscheidung ändert. Sie erläutert und verlinkt; verbindliche
Detailregeln bleiben unter `docs/`.

| Änderung | Wiki-Pflege im selben Arbeitsschritt |
|---|---|
| Neue oder verschobene Steuerungsdatei | [Steuerung und Quellen](governance-and-sources.md) und alle betroffenen Links prüfen. |
| Neuer Entwicklungsstand, bestätigte Regel oder relevante offene Frage | [Projektbild](project-portrait.md) aktualisieren. |
| Änderung der Arbeits-, Freigabe- oder Prüfungslogik | [Arbeitsmodell](working-model.md) und Steuerungslandkarte aktualisieren. |
| Folgenreiche Entscheidung oder Ausnahme | Menschliche Auswirkung im Projektbild einordnen und auf das Decision Log verweisen. |
| Routinemäßige Prüfung des Wiki-Schnitts | [Evaluation und Review](evaluation-and-review.md) über den aktiven Steuerbefehl `WIKI PRÜFEN`. |

Nach strukturellen Änderungen werden alle Markdown-Links der Wiki gegen die
neuen Zielpfade geprüft. Wenn eine Änderung keine verständliche Auswirkung
hat, wird die Wiki nicht künstlich erweitert.
