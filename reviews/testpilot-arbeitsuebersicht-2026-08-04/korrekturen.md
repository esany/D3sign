# Korrigierte Neufassung: Testpilot für eine reale Projektkomponente

## 1. Zweck und Arbeitsname

**Arbeitsname:** „Eine reale Projektkomponente schrittweise mit KI-Unterstützung prüfen“

Der Gesamtpilot untersucht nicht, ob KI „Komponenten kann“. Er beschreibt als **Planungsvorhaben**, wie ein menschlich geführter Ablauf an einem realen, begrenzten Komponentenfall Anforderungen, Struktur, Dokumentation und spätere Development-Übergabe nachvollziehbarer prüfen könnte.

Die Komponente ist der mögliche konkrete Gegenstand. Der Workflow zwischen Gestaltung, Agent, Figma und Development ist der spätere Prüfgegenstand. Beide werden nicht im selben Testschritt gleichgesetzt. Dieses Dokument beauftragt keine dieser Tätigkeiten.

## 2. Ziel und Grenzen

### Ziel

Für eine mögliche spätere Durchführung an einer konkreten Projektkomponente schrittweise festlegen,

- ob die Komponente als Figma-Gegenstand sauber aufgebaut oder geprüft werden kann,
- welche fachlichen Fragen und Grenzen dabei sichtbar werden,
- ob eine nachgelagerte Dokumentation und Übergabe für Menschen nachvollziehbar vorbereitet werden kann,
- und ob ein späterer Workflow-Pilot begründet ist.

### Nicht Ziel

- keine vollständige Basisbibliothek;
- keine produktive Design-to-Code-Pipeline;
- keine automatische Design-, Accessibility- oder Codefreigabe;
- keine Tool- oder Skill-Einführung;
- keine Generalisierung eines Projektfalls zum Standard;
- keine Code-, Token- oder Library-Entscheidung außerhalb eines ausdrücklich bestätigten Scopes.

## 3. Statusbasis

| Aussage | Status |
|---|---|
| Komponentenvertrag bleibt erweiterbar und trennt Projektkontext von generischer Regel. | bestätigt (D-034) |
| Figma-Komponentendokumentation muss praktisch vertrauensfähig sein. | bestätigt (D-035) |
| Komponentenbau, -prüfung und -dokumentation sind getrennte Auftragsarten. | bestätigt (D-036) |
| Das V6-Prüfgate für reinen Komponentenbau wird beim nächsten Test erprobt. | Regelkandidat (E-069) |
| V5 ist begrenzt verwertbar, aber kein bestandenes Komponenten- oder Dokumentationsergebnis. | dokumentierter Befund (E-070) |
| Zeitersparnis, bessere Übergabe und Wiederverwendbarkeit im Projektalltag. | Hypothesen, noch nicht nachgewiesen |

## 4. Phasenmodell

### Phase 1 – möglicher V6-Test: reiner Komponentenbau

**Mögliches Ziel:** Eine echte Figma-Komponente oder ein Component Set als begrenzten Gegenstand erstellen oder prüfen.

**Auftrag enthält:** Aufbaustufe, Generation `V6`, konkreten Node oder klaren Erstellbereich, Rolle, Scope, Abnahme und Abbruchkriterium.

**Prüfgate:** Auftragstyp, Komponenten-Gegenstand, Anatomy, Varianten, Properties, Overrides, Scope und Sichtbarkeit.

**Mögliches Ergebnis:** `Komponentenbau bestanden`, `nacharbeiten`, `nicht bestanden` oder Umklassifizierung. Keine Dokumentationsframes, Tokenentscheidung, Code-Anbindung oder Accessibility-Freigabe.

### Phase 2 – Komponentenprüfung und Dokumentation

**Voraussetzung für eine spätere Durchführung:** Phase 1 ist abgeschlossen und ein konkreter Dokumentationsauftrag wird neu freigegeben.

**Ziel:** Zweck, Verwendung, Grenzen, Varianten/Zustände, Status, Quellen und offene Punkte für Menschen verständlich dokumentieren.

**Abnahme:** D-035 — Vertrauen, Unterstützung und Verlässlichkeit; visueller Review ist erforderlich.

### Phase 3 – begrenzter Handoff mit Development

**Voraussetzung für eine spätere Durchführung:** Konkreter Projektfall, zuständige Development-Person, zugelassener Codekontext sowie Daten- und Toolfreigabe.

**Ziel:** Technische Semantik, Machbarkeit, Laufzeit-, Accessibility- und Codebezug als getrennte Rückmeldung erfassen.

**Grenze:** Eine technische Rückmeldung ist keine produktive Implementierungs- oder Releasefreigabe.

### Phase 4 – Workflowbewertung

**Voraussetzung für eine spätere Durchführung:** Vorher festgelegter Vergleichsprozess, Aufwandserfassung, Abbruchkriterium und menschliche Bewertung.

**Ziel:** Nutzen, Aufwand, Grenzen, Rückfragen, notwendige Kompetenz und mögliche Wiederverwendung auswerten.

**Mögliche Konsequenz:** weiterführen, mit Anpassungen testen, auf eine Teilfunktion begrenzen oder nicht weiterführen.

## 5. Voraussetzungen vor einem realen Projektfall

- Ein konkretes Problem, eine Komponente und ein eng begrenzter Projektbereich sind benannt.
- Gestaltung benennt Zweck, Nutzungskontext, bekannte Anforderungen und bewusst offene Fragen.
- Der Figma- und gegebenenfalls Code-Scope ist eindeutig; bei Übernahmen ist die Übernahmeart geklärt.
- Tool, Datenklasse, Datenfluss, Lizenz-/Planstatus und schreibender Zugriff sind für den Einzelfall freigegeben oder als offen ausgewiesen.
- Rollen und Abnahme sind benannt: Gestaltung entscheidet fachlich, Development prüft technische Fragen, Review prüft Evidenz und Grenzen.
- Externe Angaben zu Sebida, `neocx`, Timelog und Tickets sind vor Verwendung gegen ihre Primärquelle zu bestätigen.

## 6. Evidenz- und Ergebnislogik

Jeder Schritt unterscheidet sichtbar: `sichtbar`, `abgeleitet`, `getestet`, `fehlgeschlagen`, `nicht getestet`, `nicht nachgewiesen` und `blockiert`.

Ein Figma-Befund kann Struktur, Varianten, Properties oder Variablenbindungen zeigen. Er beweist nicht automatisch fachliche Semantik, zulässige Nutzung, Accessibility, Laufzeitverhalten oder Code-Parität.

## 7. Kompakte Fassung für die Präsentation

> Wir prüfen schrittweise an einer realen Projektkomponente, ob unser menschlich geführter und agentisch unterstützter Ablauf praktisch trägt. Zuerst wird ausschließlich der Komponentenbau als klar begrenzter Figma-Gegenstand geprüft. Erst danach entscheiden wir separat über Dokumentation, Development-Handoff und eine Bewertung von Nutzen und Aufwand. Der Pilot führt weder eine vollständige Library noch eine automatische Freigabe ein. Er macht sichtbar, welche Fragen der Workflow tatsächlich beantwortet, welche menschliche Entscheidung benötigt wird und ob ein weiterer Schritt begründet ist.

## Nächster Planungsschritt

Menschlich entscheiden, ob und in welchem Umfang aus diesem Planungsvorhaben ein Pilotauftrag entstehen soll. Ohne diesen separaten Auftrag wird nichts in Figma, Code oder externen Tools ausgeführt.
