# Review: Testpilot – belastbare Arbeitsübersicht

## Transparenznachweis

| Feld | Einordnung |
|---|---|
| Modus | Vorschlag |
| Nutzungsebene | Verbunden: fachliche Nutzung und Systementwicklung, getrennt bewertet |
| Rolle | Review mit Design-Ops- und Governance-Perspektive |
| Gegenstand | Eingereichte Arbeitsübersicht „Eine reale Komponente mit KI-Unterstützung klären, verbessern, dokumentieren und übergeben“ |
| Verbindliche Vergleichsquellen | Base Template, Standards, D-034 bis D-036, E-067 bis E-070, Prüfgate für reinen Figma-Komponentenbau |
| Automatisch ausgeführt | Quellenabgleich und redaktionelle Korrektur dieses Vorschlags |
| Nicht verändert | Figma, kanonische Projektquellen, Decisions, Regeln und externe Systeme |
| Menschlich zu prüfen | konkreter Projektfall, Daten-/Toolfreigabe, beteiligte Personen, Nutzen und Aufwand |

## Gesamturteil

Die Übersicht ist als Begründung für einen späteren, realen Workflow-Piloten gut geeignet: Sie beschreibt Nutzenhypothesen, Grenzen und die notwendige menschliche Arbeitsteilung nachvollziehbar. Sie ist **kein Ausführungsauftrag** und autorisiert weder einen Figma-Schreibversuch noch eine Tool-, Code- oder Projektänderung.

Der aktuell dokumentierte nächste Schritt ist **V6 – reiner Komponentenbau**. Er darf ausschließlich ein Component Set beziehungsweise einen bestehenden Komponenten-Gegenstand bauen oder prüfen. Dokumentation, Handoff und Development-Abnahme sind dafür ausdrücklich nicht Teil des Scopes. Das folgt aus D-036, E-069, E-070 und dem noch zu erprobenden Prüfgate.

## Was belastbar anschließt

| Aussage der Übersicht | Bewertung | Grund |
|---|---|---|
| Ein Pilot soll nicht Rollout, vollständige Library oder automatische Freigabe vorwegnehmen. | Bestätigt | Entspricht Base Template und Test-/Systementwicklungsgrenze. |
| Semantik, Anforderungen und menschliche Entscheidung bleiben vor Toolausführung relevant. | Bestätigt | Entspricht Bausteinvertrag und Evidenzprinzip. |
| Figma-Struktur ersetzt weder Accessibility-, Laufzeit- noch Code-Paritätsnachweis. | Bestätigt | Durch die bisherigen Figma-Befunde begrenzt belegt. |
| Toolverfügbarkeit ist kein Nutzennachweis. | Bestätigt | Entspricht D-028, D-031 bis D-033 und den Fundstückbefunden. |
| Ein realer Projektfall kann Nutzen, Aufwand und Übergabequalität prüfen. | Hypothese mit sinnvoller Prüffrage | Für das Projekt bisher noch nicht praktisch nachgewiesen. |

## Korrekturbedarf

### 1. Den Pilot nicht als einen einzigen Durchlauf behandeln

Die Formulierung „klären, verbessern, dokumentieren und übergeben“ kombiniert Komponentenbau, Komponentenprüfung, Dokumentation, Review und Handoff. D-036 erlaubt eine Kombination nur mit sichtbarer Reihenfolge und jeweils eigener Abnahme. Ohne diese Trennung droht dieselbe Zielverschiebung wie bei V5.

**Korrektur:** Den Gesamtpiloten ausschließlich als mögliches Phasenmodell führen. Eine einzelne Phase wird erst durch einen späteren, eigenständigen und freigegebenen Auftrag zur Durchführung.

### 2. V6 nicht mit Dokumentation oder Handoff belasten

E-070 verlangt für V6: Component Set, Anatomy, Properties, Varianten, Override-Stabilität und Sichttest; keine Dokumentationsframes. Die Arbeitsübersicht nennt dagegen Dokumentation, Design-Review und Development-Übergabe als erwartete Ergebnisse desselben Piloten.

**Korrektur:** Dokumentation und Handoff nur als mögliche, separat freizugebende Folgephasen vorsehen.

### 3. Projekt- und Fremdquellen klarer markieren

Angaben zu `neocx`, Sebida-Skills, Timelog, Tickets und dem Verlauf 2024–2026 stammen aus der eingereichten Übersicht oder aus nicht zugänglichen `sandbox:`-Verweisen. Sie wurden hier nicht unabhängig geprüft.

**Korrektur:** Diese Angaben als „externe Eingabe, vor Pilotstart zu bestätigen“ markieren; sie nicht als bereits belegten Projektfakt ausgeben.

### 4. Entscheidungsstatus präzisieren

Nicht alle beschriebenen Arbeitsprinzipien sind bestätigte Decisions. Insbesondere die Trennung von Aufbaustufe und Generation sowie das Prüfgate für reinen Komponentenbau sind Regelkandidaten. D-036 ist bestätigt; D-034 und D-035 ebenfalls.

**Korrektur:** In der Neufassung konsequent `bestätigt`, `Regelkandidat`, `Hypothese`, `offen` und `nicht nachgewiesen` unterscheiden.

### 5. Messung vor dem realen Workflow-Pilot festlegen

„Zeit sparen“, „Rückfragen reduzieren“ und „wirtschaftlicher“ sind sinnvolle Ziele, aber noch keine Abnahmekriterien. Ohne Ausgangsvergleich, Messzeitraum, Abbruchkriterium und menschliche Prüfinstanz wären sie nachträglich interpretierbar.

**Korrektur:** Erst bei einer separat freigegebenen Handoff-Phase einen kleinen Messplan mit Vergleichsprozess, Aufwandserfassung und Abbruchkriterium festlegen.

## Empfohlene Reihenfolge

1. **V6 – reiner Komponentenbau:** das E-069-Gate an einem eindeutig benannten Komponenten-Gegenstand anwenden.
2. **Komponentenprüfung und Dokumentation:** nur nach neuer Freigabe; D-035 als Abnahmegrundlage nutzen.
3. **Projektworkflow-/Handoff-Pilot:** nur bei konkretem Projektfall, geklärter Development-Beteiligung, Daten-/Toolfreigabe und Messplan.

## Nächster Planungsschritt

Menschlich entscheiden, ob aus dieser Planung überhaupt ein konkreter Pilotauftrag abgeleitet werden soll; bis dahin erfolgt keine Ausführung.
