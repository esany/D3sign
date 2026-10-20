# Project Template

Status: Entwurf – Zielbild, nicht Teil des aktuellen v0.1-Ausbauschritts

Dieses Dokument ist die spätere Kopiervorlage für ein neues
Individualsoftware-Projekt.
Es ergänzt das [Base Template](../docs/governance/base-template.md); es ersetzt keine dort
definierten Regeln. Nach dem Kopieren wird daraus ein konkretes Projektkit.

## Verhältnis zum Base Template

| Ebene | Enthält | Darf enthalten |
|---|---|---|
| Base Template | projektübergreifende Regeln, Entscheidungsrechte, Qualitäts- und Lernlogik | keine Brand-, Kunden- oder Produktwerte |
| Project Template | Struktur für projektspezifische Ergänzungen | Platzhalter und Verweise auf die Baseline |
| Projektkit | ausgefüllte Instanz für ein Vorhaben | Quellen, Brand, Produkt, Plattform und freigegebene Ausnahmen |

## Späterer minimaler Projektkit-Pilot

Diese Felder werden für genau eine konkrete Benutzerhandlung ausgefüllt. Nicht
belegte Angaben bleiben offen; sie werden nicht durch Annahmen ersetzt.

| Feld | Projekteingabe |
|---|---|
| Nutzungskontext | Wo und in welcher Situation tritt die Handlung auf? |
| Nutzerziel | Welches Ergebnis möchte die Person erreichen? |
| beabsichtigte Wirkung | Welche Operation, Zustandsänderung oder Navigation soll erfolgen? |
| umgebende Handlungen | Welche anderen Handlungen stehen im selben Kontext zur Wahl? |
| Plattform | Welche Bedien- und Darstellungskonventionen sind relevant? |
| verbindliche Quellen | Welche Produkt-, Brand-, Accessibility- oder Technikvorgaben gelten bereits? |
| Grenzen | Was darf im Pilot nicht verändert oder vorausgesetzt werden? |

### Erwartetes Pilotergebnis

Der Pilot liefert genau einen ausgefüllten
[Bausteinvertrag](../docs/governance/base-template.md#3-wiederverwendung-und-bausteinvertrag)
mit:

- Einordnung als Aktion oder Navigation,
- begründeter kontextueller Priorität,
- den im Nutzungskontext erforderlichen Zuständen,
- klarer Trennung zwischen generischer Bedeutung und Projektausprägung,
- offenen Fragen und erforderlichen Freigaben.

Die Abnahme erfolgt erst bei Aktivierung dieser Ebene mit der dann gültigen
Projektkit-Checkliste; der heutige Vertikalschnitt ist nicht Teil des
generischen Library-Grundbausteins.

## Ausblick: spätere Projektergänzungen

Diese Struktur wird erst konkretisiert, wenn ein realer Projektfall sie
benötigt:

- verbindliche Produkt- und Brandquellen
- Zielgruppe, Plattform und erster Lieferumfang
- vorhandene und zugelassene Tokens, Komponenten, Patterns und Assets
- projektspezifische Accessibility-, Datenschutz- oder Technikvorgaben
- begründete Ausnahmen und ihre Freigabe

Nicht Teil des aktuellen Umfangs sind vollständige Token-Pipelines,
Komponentenbibliotheken, Framework-Vorgaben, CI, Releaseprozesse oder
automatisierte Figma-/Code-Synchronisation.
