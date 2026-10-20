# Rollen und User Stories

Status: bestätigt durch D-021 und D-022; praktische Validierung ausstehend

## Zweck

Dieses Governance-Artefakt beschreibt die dokumentierten Arbeitsrollen und die
Bedürfnisse, die ihre Zusammenarbeit mit Agent, Figma, Repository, Code und
Wiki erfüllen muss. Es ist keine Persona-Sammlung und erfindet kein späteres
Projektteam.

Die User Stories sind aus `AGENTS.md`, Base Template, Evaluation Framework,
Tooling-Regeln und den bestehenden Wiki-Arbeitsabläufen abgeleitet. Nicht
praktisch geprüfte Anforderungen sind als offene Validierung markiert.

## Gemeinsame Voraussetzung: Mensch ohne Vorwissen

> Als neue oder nur teilweise kontextualisierte Person möchte ich Zweck,
> aktuellen Status, Arbeitsteilung, offene Entscheidung und nächsten Schritt
> erkennen, damit ich einen Befund einordnen kann, ohne implizites
> Projektwissen zu erraten.

**Anforderung:** Die Wiki muss diese Orientierung vermitteln; die verbindliche
Rollen- und Qualitätsdefinition bleibt hier in der Governance.

## Design

> Als Designer:in möchte ich zuerst verstehen, was das System, seine
> Figma-Anbindung und die Wiki leisten können, wo ihre Grenzen liegen und wann
> ich sie verwenden oder nicht verwenden sollte. Danach möchte ich verstehen,
> welche Bedeutung ein Befund oder eine Regel für Nutzung, Zustände, visuelle
> Systemlogik und Accessibility hat.

**Erforderliche Informationen:**

- Werkzeugfamilien und jeweilige Aufgabe;
- Fähigkeiten und Grenzen: lesen, bewerten, vorschlagen, schreiben;
- konkrete Does & Don’ts und Beispiele für geeignete Aufträge;
- Design-Rationale für Regeln, Tokens, Annotationen und Prüfschritte;
- Auswirkung auf den gestalterischen Arbeitsprozess;
- Trennung von Testfixture, Vorschlag und bestätigter Regel;
- sichtbare Figma-Grenzen und nächster prüfbarer Design-Schritt.

## Development

> Als Developer:in möchte ich erkennen, welche Figma- oder Design-Aussage
> ausführbar, vorgeschlagen oder nicht ausreichend belegt ist, damit ich keinen
> nicht bestätigten Entwurf in Code oder technische Konvention übersetze.

**Erforderliche Informationen:**

- verbindliche Quelle für Regeln und Entscheidungen;
- Grenze zwischen auslesbarem Figma-Kontext und ausführbarer Implementierung;
- Komponenten-, Property-, Zustands-, Token- und Handoff-Kontext;
- fehlende Codebasis oder nicht bewertete Absicht;
- Design-Rationale, wenn sie Umsetzung oder Mapping beeinflusst;
- genau eine offene technische Anschlussprüfung.

## Review

> Als Reviewer:in möchte ich Umfang, Evidenz, Grenzen, fachliche Ableitung und
> Abnahme in dieser Reihenfolge nachvollziehen, damit ich ein Ergebnis ohne
> Rekonstruktion des Arbeitschats prüfen kann.

**Erforderliche Informationen:**

- Evidenz- und Toolingstatus vor fachlichen Aussagen;
- Statuswerte und Trennung von Befund, Vorschlag und Entscheidung;
- Abnahmekriterien und genau ein nächster Schritt;
- Quellen- und Linkstruktur;
- Kennzeichnung von `nicht bewertet` oder `eingeschränkt bewertet`;
- Begründung der Relevanz für die konkrete Entscheidung.

### Technisch, agentisch und informationell versierter Review-Fokus

Der Review-Fokus umfasst zusätzlich:

- ausführbares Verhalten, Schnittstellen und technische Grenzen;
- agentische Arbeitsweisen, Mensch–Maschine-Arbeitsteilung und sichere
  Trennung von Lesen, Bewerten, Vorschlagen, Schreiben und Freigeben;
- Auswahl passender Tool-Familien und Zugriffsebenen sowie Prompt- und
  Kontextpassung;
- Token-, Zeit- und Iterationsökonomie;
- Tooling-Grenzen, Fehlinterpretations- und Halluzinationsrisiken;
- Informationsdesign, Informationsarchitektur und Wissensvermittlung;
- progressive Offenlegung, selektives Lesen und semantische Typografie;
- Erkennen von Doppelungen, falschem Seitenschnitt und Kontextbrüchen;
- Design-Rationale und Einordnung in den tatsächlichen Entwurfsprozess;
- state-of-the-art Empfehlungen nur mit belastbarer Quelle oder begrenztem
  Test.

Der Fokus prüft Zielpassung, Zeitpunkt, Machbarkeit, Aufwand, Pflegekosten und
Praxistauglichkeit. Er verleiht keine Freigabe- oder
Standardisierungsbefugnis.

## Governance

> Als Governance-Verantwortliche:r möchte ich sehen, welche Quelle gilt,
> welche Entscheidung getroffen wurde, welchen Status sie hat und welche
> Artefakte betroffen sind, damit Regeln kontrolliert geändert und nicht
> versehentlich vervielfacht werden.

**Erforderliche Informationen:**

- Quellenhierarchie und Zuständigkeit je Artefakt;
- Decision Log mit Status, Begründung und Geltungsbereich;
- Regelkandidaten und explizite Regelsetzung;
- Rückführung von Evaluationsergebnissen;
- Rationale für Regel, Ausnahme oder Ablösung;
- Nachweis, dass Wiki-Einordnung keine operative Regel dupliziert.

## Anforderungen an die menschliche Vermittlung

Die Rollenanforderungen werden in der Wiki durch progressive Offenlegung
vermittelt:

1. **Orientierung:** Zweck, Hauptaussage, Relevanz und Status.
2. **Auswahl:** Rollenbezogene Lesepfade, Entscheidungspunkte und nächste
   Handlung.
3. **Detail:** Begründungen, Beispiele, Evidenz und Quellen.
4. **Vertiefung:** Verbindliche Regeln, Checklisten und Evaluationseinträge.

Typografische Auszeichnung ist semantisch zu verwenden: Überschriften zeigen
die Wissenshierarchie, Statuslabels markieren `Befund`, `Regel`, `Vorschlag`
und `Offen`, Tabellen dienen echten Vergleichen, `Code` technischen Befehlen
und Links werden beschreibend benannt. Dekorative Formatierung ohne
Orientierungsfunktion wird vermieden.

## Anforderungen an neue Inhalte

Vor einer neuen Regel, Wiki-Einordnung oder User Story wird geprüft:

1. Welche Rolle oder Vorwissenslücke braucht den Inhalt?
2. Welche konkrete Entscheidung oder Handlung unterstützt er?
3. Welche Quelle ist verbindlich?
4. Welcher Status gilt?
5. Woran wird Verständlichkeit und ausreichende Tiefe geprüft?

Ohne konkrete Nutzungssituation und prüfbares Ergebnis wird kein neuer
Abschnitt angelegt; der Inhalt bleibt offene Frage oder wird einer bestehenden
Quelle zugeordnet.

## Offene Validierung

Noch nicht praktisch geprüft ist, ob:

- Designer:innen Werkzeuggrenzen und Design-Rationale ohne Zusatzwissen
  verstehen;
- Developer:innen Befund und Codevorgabe sicher unterscheiden;
- Reviewer:innen die Evidenzreihenfolge ohne Chat-Verlauf anwenden;
- Governance-Verantwortliche Änderungen ohne doppelte Regelpflege rückführen.

Der nächste Validierungsschritt ist ein einzelner neuer Wiki-Inhalt, der aus
allen vier Perspektiven gelesen und bewertet wird.
