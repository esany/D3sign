# Semantic Model

Status: Entwurf – testbereit in v0.1

Dieses Dokument beschreibt Bedeutungen, Begriffe, Rollen, Zustände,
Beziehungen und Übergänge. Es ist nicht mit einem Pattern- oder
Komponentenkatalog gleichzusetzen.

## Rolle im Grundbaustein

Das Modell ist die Bedeutungsschicht zwischen Design Principles und Tokens
beziehungsweise Komponenten. Es entscheidet nicht über eine Atomic-Design-
Ebene und ersetzt keinen Komponenten- oder Patternkatalog.

## Minimalmodell

| Ebene | Rolle | Projektübergreifend | Projektspezifisch |
|---|---|---|---|
| Foundation | Trägt eine wiederverwendbare semantische oder gestalterische Rolle. | Bedeutung und zulässige Verwendung | konkrete Werte, Brand und Plattformausprägung |
| Komponente | Kapselt eine wiederverwendbare Interaktion oder Information. | Zweck, Verhalten, Zustände und Grenzen | Darstellung, Inhalt und technische Implementierung |
| Pattern | Verbindet Bausteine zu einer wiederkehrenden Aufgabe oder einem Ablauf. | Aufgabe, Reihenfolge und Entscheidungslogik | Produktprozess, Inhalte und fachliche Sonderfälle |
| Projektausprägung | Konkretisiert das System für ein Vorhaben. | übernimmt bestätigte Bedeutungen und Verträge | ergänzt Quellen, Werte und freigegebene Ausnahmen |

Beziehungen:

1. Eine Komponente verwendet Foundations, ohne deren Bedeutung umzudeuten.
2. Ein Pattern kombiniert Komponenten und gegebenenfalls weitere Patterns.
3. Eine Projektausprägung konkretisiert Werte und Inhalte; sie ersetzt keine
   projektübergreifende Bedeutung ohne dokumentierte Ausnahme.
4. Eine wiederkehrende Projektausprägung wird erst nach mehreren belegten
   Fällen Kandidat für das Base Template.

## Rollen und Interaktionen

v0.1 prüft die semantische Entscheidung vor der visuellen Ausprägung.

| Begriff | Bedeutung | Abgrenzung |
|---|---|---|
| Aktion | Löst im aktuellen Kontext eine Operation oder Zustandsänderung aus. | Ist keine Navigation zu einem anderen Ziel. |
| Navigation | Wechselt Ort, Ansicht oder Ziel innerhalb oder außerhalb des Produkts. | Löst nicht primär eine Operation im aktuellen Kontext aus. |
| Priorität | Ordnet eine Handlung relativ zu anderen Handlungen im selben Kontext ein. | Ist keine dauerhaft globale Eigenschaft eines Labels oder Bausteins. |
| Auswahl | Erfasst eine oder mehrere Entscheidungen innerhalb einer vorgegebenen Menge. | Ist keine Ausführung einer Operation. |
| Eingabe | Erfasst oder verändert einen Wert. | Ist keine bloße Darstellung eines Werts. |
| Status | Vermittelt Zustand, Fortschritt, Erfolg, Warnung oder Fehler. | Ist nicht allein durch Farbe verständlich. |
| Inhalt/Struktur | Ordnet Information und ihre Beziehungen. | Ist keine interaktive Handlung ohne weiteres Verhalten. |

Eine Aktion kann beispielsweise durch eine Button-Komponente ausgedrückt
werden, eine Navigation durch einen Link. Die konkrete Komponente wird erst
nach Prüfung von Absicht, Kontext und Plattform gewählt.

Für den Pilot werden nur die Zustände dokumentiert, die für die gewählte
Handlung tatsächlich erforderlich sind. Bei einem interaktiven Baustein sind
Bedienbarkeit, Fokus, zugängliche Benennung und ein nicht ausschließlich
visuell vermittelter Status mindestens zu prüfen.

## Zustandsmodell

Nicht jeder Baustein braucht jeden Zustand. Erforderliche Zustände werden aus
seiner Rolle und Nutzung abgeleitet. Typische Kategorien sind verfügbar,
fokussiert, aktiv/ausgewählt, deaktiviert, geladen, leer, Erfolg, Warnung und
Fehler. Visuelle, semantische und bedienbezogene Rückmeldung werden gemeinsam
betrachtet.

## Offene Validierung

- Reicht die Trennung von Aktion, Navigation und kontextueller Priorität für
  einen ersten realen Anwendungsfall?
- Welche Vertragsfelder fehlen bei der Ableitung in ein Projekt?
- Welche Teile des Ergebnisses sind tatsächlich wiederverwendbar?
