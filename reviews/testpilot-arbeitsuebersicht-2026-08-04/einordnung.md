# Einordnung: vom Komponentenbau zum realen Workflow-Piloten

## Status

Diese Einordnung ist ein Vorschlag, keine neue Regel und kein Ausführungsauftrag. Sie verändert weder den dokumentierten V5-Stand noch den Status von Decisions oder Regelkandidaten und autorisiert keine Figma-, Code- oder Toolaktion.

## Warum die Trennung nötig ist

Der Arbeitsname beschreibt einen sinnvollen Zielzustand, aber keine einzelne Testhandlung. „Eine reale Komponente klären, verbessern, dokumentieren und übergeben“ enthält mindestens vier Prüfgegenstände mit unterschiedlicher Evidenz und Abnahme:

| Phase | Gegenstand | Zulässiges Ergebnis | Nicht nachgewiesen durch die Phase |
|---|---|---|---|
| 1. Komponentenbau | Echte Figma-Komponente bzw. Component Set | Prüfgate: Anatomy, Varianten, Properties, Overrides, Sichtbarkeit | Nutzungsqualität, Dokumentation, Accessibility, Code-Parität |
| 2. Komponentenprüfung/Dokumentation | Bestehende oder bestandene Komponente | Nutzungs-, Grenz- und Statusinformation gemäß D-035 | Laufzeitverhalten, technische Implementierung |
| 3. Handoff | Dokumentierte Projektkomponente plus relevanter Codekontext | Technische Rückmeldung von Development | Produktive Code-Parität oder Releasefreigabe |
| 4. Workflowbewertung | Begrenzter, realer Arbeitsablauf | Befund zu Nutzen, Aufwand, Grenzen und Kompetenzbedarf | Allgemeingültigkeit für weitere Projekte |

Die Phasen dürfen verbunden werden, aber nur sequenziell. Jede Phase bleibt zunächst Planung und braucht vor einer Durchführung einen neuen sichtbaren Auftrag, eigenen Scope, Daten-/Toolfreigaben und eine menschliche Abnahme.

## Aktuelle Lage

### Bestätigt

- D-034: Komponentenverträge müssen spätere Erweiterungs- und Migrationsarten unterscheidbar machen.
- D-035: Figma-Komponentendokumentation muss Menschen praktisch unterstützen und verlässlich sein.
- D-036: Erstellen, Prüfen und Dokumentieren sind getrennte Auftragsarten.
- E-070: V5 ist begrenzt verwertbar, aber nicht als bestandene Button-Komponente oder finales Dokumentationstemplate zu verwenden.

### Regelkandidat

- Das Prüfgate für reinen Komponentenbau (E-069) wird erst beim nächsten passenden Test praktisch erprobt.
- Die Trennung von Aufbaustufe und Generation ist noch nicht als bestätigte Decision gesetzt.

### Offen oder nicht nachgewiesen

- konkreter Projektfall und seine fachliche Relevanz;
- Development-Beteiligung, Codezugriff und technische Abnahme;
- Tool-, Daten-, Lizenz- und ISMS-Freigabe für den konkreten Fall;
- tatsächlicher Zeitgewinn, verringerte Rückfragen und Wiederverwendungsnutzen;
- Einsatzfähigkeit eines konkreten externen Sebida-Skills.

## Empfohlenes Zielbild

Der reale Workflow-Pilot bleibt ein mögliches Zielbild, aber kein aktueller Figma-Auftrag. Seine Kernfrage lautet:

> Verbessert ein klar begrenzter, menschlich geführter und agentisch unterstützter Ablauf an einer konkreten Projektkomponente die Sichtbarkeit von Anforderungen und die Vorbereitung der Development-Übergabe mit vertretbarem Aufwand?

Diese Frage kann erst ab Phase 3 oder 4 belastbar beantwortet werden. Phase 1 beantwortet nur: Ist der Komponentenbau als sauber begrenzter Figma-Gegenstand kontrollierbar?

## Minimaler Übergang zwischen den Phasen

| Übergang | Erforderliche Entscheidung |
|---|---|
| Phase 1 → 2 | Ist der Komponentenbau ausreichend belegt, um Dokumentation zu rechtfertigen? |
| Phase 2 → 3 | Sind konkreter Codekontext, Development-Rolle und Daten-/Toolscope freigegeben? |
| Phase 3 → 4 | Sind Vergleichsprozess, Metriken, Abbruchkriterium und menschliche Bewertung festgelegt? |

## Nächster Planungsschritt

Entscheiden, ob ein Pilot überhaupt beauftragt werden soll; erst dann einen einzelnen, begrenzten Auftrag formulieren.
