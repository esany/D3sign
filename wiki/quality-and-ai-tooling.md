# Qualität gestalten – mit KI-Tooling als Unterstützung

## Worum es hier geht

Diese Seite unterstützt Gestalter:innen dabei, die Qualität eines generischen
Bausteins zu beurteilen und KI-Tooling gezielt dafür einzusetzen. Der Maßstab
ist nicht, ob ein Tool viel Kontext ausliest, sondern ob es eine bessere,
begründete Gestaltungs- und Umsetzungsentscheidung ermöglicht.

## Qualitätsarbeit am Baustein

Bei einem generischen Baustein werden nur die für den konkreten Fall
relevanten Qualitätsdimensionen betrachtet:

| Qualitätsdimension | Leitfrage |
|---|---|
| Zweck und Nutzung | Welche Aufgabe und Wirkung soll der Baustein für Menschen erfüllen? |
| Varianten, Zustände und Verhalten | Was verändert sich, wann und wie bleibt es verständlich? |
| Semantik und Konsistenz | Passt die Bedeutung zum System und zu benachbarten Bausteinen? |
| Zugänglichkeit und Responsive-Verhalten | Was muss in unterschiedlichen Nutzungssituationen erhalten bleiben? |
| Übergabe und Abnahme | Was muss Development umsetzen können, woran wird gemeinsam geprüft? |

Nicht sichtbare oder nicht beurteilte Dimensionen bleiben `nicht bewertet`.
Eine vollständige Komponenten- oder Tokenarchitektur wird daraus nicht
abgeleitet.

## Wie KI-Tooling dient

KI und Werkzeuge können begrenzten Figma-Kontext, Varianten, Eigenschaften,
Tokenbezüge, Unterschiede oder Dokumentationslücken sichtbar machen. Sie
können Informationen strukturieren und auf offene Fragen hinweisen. Sie
können weder die gestalterische Absicht erraten noch Qualität freigeben.

| Menschliche Arbeit | Dienende Unterstützung |
|---|---|
| Qualität, Bedeutung, Priorität und akzeptierbare Abweichung beurteilen | sichtbaren Kontext im bestätigten Umfang erfassen und transparent machen |
| entscheiden, welche Frage gerade relevant ist | passende Funktion möglichst klein und tokensparend wählen |
| Übergabe und Abnahme verantworten | Befund, Unsicherheit und offene Punkte strukturieren |

Ein erreichbares Werkzeug ist keine fachliche Evidenz. Nur tatsächlich
sichtbare, passende und zuordenbare Informationen dürfen in eine Bewertung
einfließen.

## Praktische Wege

- [Qualitätskontext aus Figma](figma-understand.md): Was ist sichtbar und was
  bedeutet es für die Qualitätsfrage?
- [Qualität übergeben und abnehmen](figma-handoff.md): Was braucht
  Development für eine prüfbare Umsetzung?
- [Figma als Kontext für Qualitätsarbeit](figma-context-and-handoff.md):
  Einstieg, wenn die Quelle oder der Kontext zuerst geklärt werden muss.

Die verbindlichen generischen Standards liegen im
[Base Template](../docs/governance/base-template.md). Diese Wiki übersetzt
ihre Bedeutung für die Arbeit, sie ersetzt sie nicht.

**Nächster Schritt:** Eine konkrete Qualitätsfrage an einem Baustein benennen
und dafür nur den passenden praktischen Weg öffnen.
