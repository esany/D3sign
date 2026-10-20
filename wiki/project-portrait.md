# Projektbild

## Worum es geht

Das Projekt entwickelt eine wiederverwendbare fachliche und operative
Grundstruktur für Individualsoftware. Sie soll Agenten klare, prüfbare Regeln
geben und Menschen dabei unterstützen, die Entwicklung gezielt zu steuern und
zu bewerten.

Es entsteht ausdrücklich noch **kein vollständiges Design System**, keine
vorgegebene technische Architektur und keine fertige Komponentenbibliothek.
Diese Dinge werden erst aus realen Projektfällen abgeleitet.

## Warum diese Struktur entsteht

Der Nutzen liegt nicht in möglichst vielen Dokumenten oder Bausteinen. Die
Struktur soll drei konkrete Probleme lösen:

- wiederkehrende fachliche Entscheidungen müssen nicht jedes Mal neu erfunden
  werden;
- KI-Unterstützung soll nachvollziehbar und begrenzt nutzbar sein, ohne
  Gestaltung oder Architektur stillschweigend festzulegen;
- Menschen sollen erkennen können, was bereits belastbar ist, was nur getestet
  wird und wo ihre Entscheidung tatsächlich gebraucht wird.

Rollen wie Design, Development, Review und Governance markieren dabei nur den
jeweiligen Blickwinkel eines Auftrags. Die fachliche Verantwortung bleibt beim
Menschen.

## Transparenz als Grundprinzip

Das System muss für Menschen außerhalb des bisherigen Arbeitsverlaufs
verständlich sein. Deshalb wird bei jedem relevanten Ergebnis sichtbar
getrennt:

- was der Agent aus dokumentierten Regeln automatisch getan hat;
- was unverändert blieb;
- was der Mensch vorgegeben, geprüft oder entschieden hat;
- welche Frage oder Freigabe noch offen ist.

Diese Trennung ist Teil der Systemqualität. Sie verhindert, dass ein plausibles
KI-Ergebnis mit einer bestätigten Regel oder menschlichen Entscheidung
verwechselt wird. Die operative Form steht im
[Transparenznachweis des Base Templates](../docs/governance/base-template.md).

## Was bisher aufgebaut wurde

| Baustein | Bedeutung für Menschen |
|---|---|
| [Base Template](../docs/governance/base-template.md) | Die projektübergreifende fachliche Baseline: Arbeitsaufträge, Quellen, Wiederverwendung, Entscheidungsrechte und Qualitätsnachweise. |
| [Project Template](../templates/project-template.md) | Die spätere Vorlage für ein projektspezifisches Kit; sie ist nicht Teil des aktuellen v0.1-Ausbauschritts. |
| [Decision Log](../docs/governance/decisions.md) | Der nachvollziehbare Ort für wichtige Entscheidungen und Ausnahmen. |
| [Tooling Map](../docs/tooling/tooling-map.md) | Orientierung, welches Figma- oder Beratungswerkzeug zu welcher Quelle, Frage und Evidenzlage passt. |
| [Prompting Guide](../docs/operations/prompting-guide.md) | Eine gemeinsame Sprache, damit Aufträge klar begrenzt und prüfbar sind. |
| Projekt-Wiki | Die Orientierungsebene für Menschen: aktueller Stand, Zusammenhänge und bewertbare Fragen. |
| [Qualität gestalten – mit KI-Tooling als Unterstützung](quality-and-ai-tooling.md) | Menschlicher Einstieg in Qualitätsarbeit an generischen Bausteinen und in die Grenzen dienender KI-Unterstützung. |
| [System entwickeln und aus der Praxis lernen](system-development-and-learning.md) | Praxisbefunde, Tooling-Betriebsfähigkeit und Lessons Learned als kontrollierter Rückfluss in das Werkzeug. |
| Menschenzentrierte Wiki-Standards | Verbindlicher Standard für verständliche Vermittlung ohne Chat- oder Modellvorwissen; geprüft über `WIKI PRÜFEN`. |

## Aktueller Reifegrad

Das [Base Template](../docs/governance/base-template.md) liegt als **v0.1 –
Entwurf, testbereit** vor. Diese Version ist bewusst klein: Sie beschreibt den
generischen Grundbaustein einer Design-System-Library – Design Principles,
semantische Rollen, Token-Ebenen, Komponenten- und Variantenregeln sowie
isolierte Tooling-Tests. Sie enthält keine Markenwerte, keine fertige
Komponentenbibliothek und keine vorgegebene Figma-Dateistruktur.

Neu gesichert ist die Erweiterungsfähigkeit von Komponentenverträgen: Das
Base Template soll keine Projektvarianten vorwegnehmen, muss aber sichtbar
machen, ob eine spätere Änderung nur eine Kontextentscheidung, eine additive
Erweiterung, eine Einschränkung oder eine semantische Korrektur wäre. Dadurch
bleiben spätere Projektkits anschlussfähig, ohne dass v0.1 zu einem starren
Vollsystem wird.

Ebenfalls gesichert ist der Qualitätsvertrag für Figma-
Komponentendokumentation: Eine Fläche ist nicht schon deshalb brauchbar, weil
Objekte, Labels oder Tabellen existieren. Sie muss Vertrauen, Unterstützung und
Verlässlichkeit herstellen, also für Menschen lesbar und entscheidungsfähig
sein und für KI dieselben Informationen robust auffindbar machen.

Der aktuelle Button-/Figma-Strang wurde als Systembefund zurückgeführt: V3 war
ein leeres, strukturell falsches Dokumentationsgerüst; die anschließende
V4-Arbeit verschob den Grundauftrag zunächst erneut Richtung Dokumentation.
Für den nächsten Versuch gilt deshalb als Arbeitsstand: Ein Komponentenpilot
braucht zuerst eine echte Figma-Komponente oder ein Component Set als
Prüfgegenstand. Die Dokumentation unterstützt diesen Baustein, ersetzt ihn
aber nicht.

Diese Trennung ist inzwischen als D-036 bestätigt: Komponenten erstellen,
Komponenten prüfen und Komponenten dokumentieren sind für KI-gestützte
Figma-Arbeit unterschiedliche Auftragsarten. Wenn sie kombiniert werden, muss
die Reihenfolge sichtbar sein. Der wichtigste Schutz ist schlicht, aber
wirksam: Erst den Baustein bestimmen oder erzeugen, dann genau diesen Baustein
dokumentieren.

Neu geschärft ist dabei die Trennung zwischen `Aufbaustufe` und `Generation`:
Die Aufbaustufe beschreibt, wie viel fachlicher Umfang im nächsten Test
überhaupt geprüft werden soll. Die Generation bezeichnet nur den konkreten
Figma-Versuch. Dadurch kann ein neuer Versuch klein bleiben, ohne das
Komponentenmodell zu verkürzen. Ebenso gilt für den aktuellen Base-Template-
Kontext: Die sichtbare Library-Dokumentation wird auf Deutsch geführt; KI-
Lesbarkeit entsteht über klare Labels, Namen, Status und Quellen, nicht über
eine zweite dominante Maschinenzone.

Aus dem V5-Review ist inzwischen ein konkretes Prüfgate für den nächsten
reinen Komponentenbau entstanden. Es prüft Auftragstyp, echten
Komponenten-Gegenstand, Anatomy, Varianten, Properties, Overrides, Scope und
Sichtbarkeit. Damit ist der nächste Lernschritt nicht „mehr Dokumentation“,
sondern ein sauberer Komponentenbau-Test ohne nicht beauftragte Doku-Flächen.
Das Gate ist arbeitsfähig, aber noch Regelkandidat.

Der anschließende Standabgleich bestätigt diese Richtung: V5 ist kein leeres
Gerüst, weil ein echtes lokales Component Set `Button / Pilot V5` vorhanden
ist. Als reiner Komponentenbau und als normale Library-Komponentendokumentation
ist V5 trotzdem nicht bestanden. Die Fläche erklärt noch zu stark den Pilot-
und Governance-Kontext und beantwortet für Gestalter noch nicht ausreichend
operativ, wann der Button genutzt wird, welche Varianten wirklich unterstützt
sind, was überschrieben werden darf und welche Teile stabiler Vertrag statt
Beispiel sind. V5 bleibt deshalb Befundträger; der nächste Versuch soll als
V6 zuerst nur die Komponente bauen.

Die ersten rein lesenden Figma-Tests an realen Komponenten liegen vor. Der
Teaser- und Button-Befund zeigen, dass Figma-Kontext, Properties, Varianten,
Zustände und Variablen als Evidenz nutzbar sind, aber keine semantische
Entscheidung, Accessibility-Abnahme oder Code-Parity ersetzen. Die Ergebnisse
bleiben Befunde und Regelkandidaten, bis ein Mensch sie bewertet.

Der Button bleibt der wichtigste fachliche Prüfstand: Er verbindet konkrete
Figma-Evidenz mit den Foundations, dem Bausteinvertrag, Rollenbedürfnissen und
Tooling-Grenzen. Offen sind vor allem die semantische Rolle einzelner
Button-Ausprägungen, die Bedeutung von Zuständen wie `selected` und `active`,
unterstützte Property-Kombinationen, Benennungskonsistenz und der spätere
Accessibility- und Code-Nachweis.

Der wichtigere jüngere Systemrückfluss ist jedoch allgemeiner: Aus dem Figma-/
Button-Piloten wurde ein Arbeitsprinzip für evidenzbasierte Toolnutzung
abgeleitet. Vor einem Toolaufruf müssen fachliche Frage, minimal erforderliche
Quelle und möglicher Evidenzstatus geklärt sein. Figma ist damit die erste
sichtbare Ausprägung einer generischen Mensch–KI–Tooling-Arbeitsteilung, nicht
der alleinige Anwendungsfall.

Für Figma ist die Kontext- und Übergabelogik inzwischen beschrieben. Die
bereitgestellten historisch gewachsenen Libraries werden ausschließlich als
externe Testfixtures gelesen. Sie sind weder dokumentierter Projektstand noch
Quelle für generische Standards. Ein Projektkit mit projektspezifischer
Library und Entwurfsdateien ist weiterhin Zielbild, nicht Teil von v0.1.

Die vollständige Staffelung steht im
[Base Template](../docs/governance/base-template.md).

## Wie die Entwicklung fortschreitet

Jede Iteration bearbeitet eine begrenzte Annahme, liefert einen verwendbaren
Baustein und endet mit einem sichtbaren Prüfergebnis. Neue Strukturen werden
nicht vorsorglich ergänzt. Auf diese Weise wächst das Base Template aus
belegten Anwendungsfällen statt aus einem vorab entworfenen Vollsystem.

## Was bewusst offen bleibt

- konkrete Marken- und Produktvorgaben
- Framework, Architektur und Dateistruktur einer Anwendung
- vollständige Tokens, Komponenten und Patterns
- Automatisierungs-, Release- und CI-Prozesse

Diese Offenheit ist kein Defizit: Sie verhindert, dass allgemeine Regeln vor
dem ersten belastbaren Anwendungsfall zu Scheingenauigkeit werden.
