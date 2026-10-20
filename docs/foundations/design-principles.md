# Design Principles

Status: Entwurf – als generischer Library-Grundbaustein prüfen

Diese Prinzipien steuern den Aufbau und die Weiterentwicklung einer
Design-System-Library. Sie enthalten keine Markenwerte, keine technische
Zielarchitektur und keine Vorgabe für konkrete Entwurfsdateien.

## Prinzipien

### Bedeutung vor Ausprägung

Wenn ein neuer Baustein oder Token entsteht, dann wird zuerst seine Rolle,
sein Nutzungskontext und sein Verhalten beschrieben. Konkrete Farbe, Größe,
Framework oder Figma-Umsetzung folgen daraus; sie begründen die Rolle nicht.

**Prüfen:** Ist erkennbar, ob es sich etwa um Aktion, Navigation, Status,
Eingabe oder Inhalt handelt, bevor ein visueller Name vergeben wird?

### Wiederverwendung mit klaren Grenzen

Wenn ein bestehender Baustein den Zweck erfüllt, dann wird er verwendet oder
innerhalb seines Vertrags variiert. Ein neuer Baustein braucht einen
nachweisbaren, wiederkehrenden Bedarf und eine dokumentierte Grenze.

**Prüfen:** Wurde vor der Neuanlage nach einem passenden Token, einer
Komponente oder einem Pattern gesucht?

### Wenige unabhängige Variantenachsen

Wenn eine Komponente Varianten hat, dann beschreibt jede Eigenschaft genau
eine unabhängige fachliche oder bedienbezogene Dimension, etwa Größe, Zustand
oder Ausrichtung. Kombinierte Sammelwerte wie `primary-large-hover` werden
nicht als einzelne Achse modelliert.

**Prüfen:** Lassen sich die Varianten verständlich kombinieren, ohne einen
unbegründeten Variantenraum zu erzeugen?

### Zustände und Accessibility gehören zum Vertrag

Wenn ein Baustein interaktiv oder statusvermittelnd ist, dann werden seine
erforderlichen Zustände, Fokus, Bedienbarkeit, zugängliche Benennung und
nicht-visuelle Rückmeldung gemeinsam beschrieben.

**Prüfen:** Fehlt eine notwendige Zustands- oder Accessibility-Entscheidung
nicht nur in Figma, sondern auch im Bausteinvertrag?

### Token drücken Rollen aus, nicht nur Werte

Wenn eine Designentscheidung wiederverwendet wird, dann wird sie auf der
kleinstmöglichen passenden Ebene abgelegt: als primitiver Wert, semantische
Rolle oder komponentenspezifischer Token. Direkte Werte in Komponenten sind
eine begründete Ausnahme.

**Prüfen:** Kann sich ein Marken- oder Rohwert ändern, ohne die Bedeutung oder
den Vertrag der nutzenden Komponente umzubenennen?

### Evolution statt Big-Bang-Refactoring

Wenn eine gewachsene Library verbessert wird, dann erfolgen Änderungen in
kleinen, rückverfolgbaren Schritten. Bestehende Nutzung, Migration,
Abhängigkeiten und Ablösung werden sichtbar gemacht.

**Prüfen:** Ist klar, was weiter gültig bleibt, was migriert werden muss und
wann ein alter Baustein abgelöst werden kann?

## Grenzen des Grundbausteins

Das Template schreibt keine Atomic-Design-Taxonomie, keine Figma-Seitenstruktur
und keine konkrete Aufteilung von Entwurfsdateien vor. Es regelt die Qualität
von Entscheidungen; spätere Projektkits konkretisieren ihre eigene
Informationsarchitektur.
