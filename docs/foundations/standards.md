# Standards

Status: Entwurf – Grundregeln für eine Design-System-Library

Diese Standards operationalisieren die [Design Principles](design-principles.md).
Sie sind generisch: konkrete Werte, Komponentenlisten, Frameworks und
Figma-Dateistrukturen entstehen erst in einer abgeleiteten Library.

## Token-Ebenen

| Ebene | Zweck | Darf enthalten | Darf nicht enthalten |
|---|---|---|---|
| Primitiv | Rohwerte zentral verwalten | Skalen, Farben, Maße, Schriftwerte | Nutzungs- oder Komponentenzweck |
| Semantisch | wiederkehrende UI-Rollen ausdrücken | etwa Text, Fläche, Fokus, Aktion, Status | Marken- oder Komponentenname als einzige Bedeutung |
| Komponente | stabilen, eigenen Bedarf einer Komponente bündeln | etwa `button/primary/background` | allgemeine Rollen, die mehrere Komponenten nutzen |

Ein höherer Token verweist bevorzugt auf die darunterliegende Ebene. Ein
komponentenspezifischer Token wird nur angelegt, wenn seine Bedeutung nicht als
allgemeine semantische Rolle tragfähig ist.

## Komponenten und Varianten

- Jede Komponente besitzt den Bausteinvertrag aus dem Base Template.
- Komponenten-Erstellung, Komponenten-Prüfung und Komponenten-Dokumentation
  sind unterschiedliche Auftragsarten. Sie dürfen kombiniert werden, müssen
  dann aber in ihrer Reihenfolge und Abnahme explizit benannt werden.
- Für einen reinen Figma-Komponentenbau wird vor Dokumentationsarbeit geprüft,
  ob Auftragstyp, echter Komponenten-Gegenstand, Anatomy, Variantenlogik,
  Component-API, Override-Stabilität, Scope und Sichtbarkeit erfüllt sind. Die
  ausführbare Fassung steht als Regelkandidat in den
  [Checklists](../operations/checklists.md#prufgate-fur-reinen-figma-komponentenbau).
- Ein Figma-Komponentenpilot braucht als Mindestgegenstand eine echte
  Figma-Komponente, ein Component Set oder einen ausdrücklich benannten
  bestehenden Komponenten-Gegenstand. Eine reine Dokumentationsfläche ist ein
  Dokumentationspilot, kein Komponentenpilot.
- Variantenachsen benennen eine einzelne Dimension; Zustand, Größe, Inhalt,
  Position und fachlicher Scope werden nicht unnötig in einer Achse vermischt.
- Nur tatsächlich notwendige Kombinationen werden bereitgestellt. Nicht jede
  denkbare Kombination ist eine unterstützte Variante.
- Komplexität wird über Zweck, Verhalten und Komposition beschrieben, nicht
  über eine verpflichtende Einordnung als Atom, Molekül oder Organismus.
- Komponentenverträge unterscheiden stabile Invarianten, aktuelle
  Ausprägungen, zulässige Kontextentscheidungen und migrationsrelevante
  Änderungen. Eine Projektableitung darf den Vertrag additiv erweitern, aber
  Rolle, Verhalten oder Accessibility nicht stillschweigend umdeuten.

## Benennung und Dokumentation

- Namen beschreiben Zweck und Rolle, nicht ausschließlich das aktuelle
  Aussehen.
- Jede veröffentlichte Library-Änderung benennt Status, Quelle, Nutzung,
  Grenzen und gegebenenfalls Ablösepfad.
- Lokale Entwurfs- oder Testbausteine werden als solche gekennzeichnet und
  nicht mit bestätigten Library-Bausteinen verwechselt.
- Sichtbare Library-Dokumentation wird im aktuellen Base-Template-Kontext auf
  Deutsch geführt. Anderssprachige oder maschinenorientierte Zusatzhinweise
  brauchen einen bestätigten Zweck und dürfen die menschliche Lesbarkeit nicht
  dominieren.
- `Aufbaustufe` und `Generation` werden getrennt: Die Aufbaustufe beschreibt
  den fachlichen Umfang und die Reife des Tests; die Generation bezeichnet den
  konkreten Figma-Versuch. Eine fehlerhafte Generation ändert nicht
  automatisch das Komponentenbeschreibung-Template.

## Figma-Komponentendokumentation

Figma-Dokumentation einer Komponente ist eine gemeinsame Arbeitsfläche für
Gestaltung, Review und spätere Übergabe. Sie gilt nur als erfüllt, wenn sie
Vertrauen, Unterstützung und Verlässlichkeit praktisch herstellt.

- **Vertrauen:** Zweck, Status, Geltung, Quelle, Beispiele und offene Punkte
  sind sichtbar unterscheidbar. Keine Fläche darf durch Formularstruktur,
  leere Platzhalter oder scheinbar vollständige Tabellen mehr Reife behaupten,
  als fachlich belegt ist.
- **Unterstützung:** Die Fläche reduziert kognitive Last. Menschen können die
  Komponente visuell scannen, bewerten und entscheiden; Agenten finden die
  gleichen Informationen über explizite Textlabels, Frame-Namen und
  nachvollziehbare Gliederung.
- **Verlässlichkeit:** Sichtbarer Inhalt, Struktur und Abnahme passen zusammen.
  Texte sind lesbar, Tabellen funktionieren als Vergleichsform, Beispiele
  wirken nicht wie Standards und Pilot- oder Governance-Hinweise bleiben
  sekundär.

Für einen Figma-Pilot oder eine Figma-Komponentendokumentation gilt:

- Dokumentation unterstützt eine vorhandene oder neu erstellte Komponente; sie
  ersetzt die Komponente nicht.
- Menschliche Lesbarkeit ist das primäre Abnahmekriterium; Maschinenlesbarkeit
  ist eine robuste Eigenschaft derselben Struktur, keine eigene sichtbare
  Hauptlogik.
- Regel, Beispiel, offene Information, Quelle und Pilotkontext werden
  unterscheidbar, aber nicht dekorativ oder störend ausgezeichnet.
- Figma zeigt komponentennahe Arbeitsinformation; längere Governance,
  Tooling-Fehler, historische Chatkontexte oder vollständige Regeltexte
  bleiben in den zuständigen Repository-Quellen.
- Token-, Code- oder Variantenthemen werden nur aufgenommen, wenn sie zum
  bestätigten Scope gehören. Andernfalls bleibt die Fläche für diese Themen
  neutral.
- Vor Abschluss einer Figma-Dokumentationsänderung ist ein visueller Review
  erforderlich. Struktur- oder Node-Evidenz allein genügt nicht.

## Accessibility und Zustände

Für interaktive oder statusvermittelnde Komponenten dokumentiert die Library
mindestens die erforderlichen Zustände, Fokusverhalten, zugängliche Benennung
und Rückmeldung. Die konkrete technische Umsetzung bleibt Aufgabe der
abgeleiteten Code- oder Projektquelle.

## Tooling-Tests

Ein KI- oder Figma-Test prüft nur die vorher festgelegte Fähigkeit. Sein
Artefakt, etwa ein ausgelesener Node, eine Variablenanalyse oder ein
Vorschlag, ist kein neuer Library-Standard. Übernahme erfolgt nur über den
dokumentierten Entscheidungs- und Evaluationsweg.
