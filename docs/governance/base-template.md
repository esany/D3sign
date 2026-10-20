# Base Template

Status: Entwurf – v0.1 testbereit

Das Base Template ist die fachliche, projektübergreifende Baseline für die
Zusammenarbeit von Mensch und Agent bei Individualsoftware. Es enthält
wiederverwendbare Regeln und Strukturen, keine kunden-, marken- oder
produktspezifischen Werte.

## Aktueller Lieferumfang: v0.1

v0.1 ist ein generischer Regelrahmen für einen Design-System-Grundbaustein.
Er prüft, ob sich die Regeln für Bedeutungen, Token, Komponenten, Varianten,
Zustände und Tooling-Tests klar und ohne Projektwerte formulieren lassen.

Der Umfang umfasst:

- [Design Principles](../foundations/design-principles.md),
- [Semantic Model](../foundations/semantic-model.md),
- [Standards](../foundations/standards.md) für Token, Komponenten und Tests,
- den nachfolgenden Bausteinvertrag und die Operations-Checklisten.

Nicht Bestandteil von v0.1 sind eine konkrete Library mit Werten oder
Komponenten, eine verbindliche Figma-Dateistruktur, ein Projektkit,
Entwurfsdateien, technische Implementierung oder Automatisierung. Diese
entstehen erst als abgeleitete, freigegebene Anwendung des Grundbausteins.

## Ausbaustufen und Abgrenzung

| Stufe | Zweck | Ergebnis | Nicht Bestandteil |
|---|---|---|---|
| v0.1 – aktueller Stand | generische Library-Regeln formulieren | Principles, Semantik, Standards und Testkarte als Entwurf | konkrete Library, Figma-Datei, Projektkit |
| v0.2 – nächste Ausbaustufe | KI-/Figma-Lesefähigkeit ergebnisoffen prüfen | read-only Befund über zugängliche Library-Informationen | Schreiben, Synchronisieren oder Standardübernahme |
| v0.3 – optional | begrenztes Vorschlagen oder Schreiben in isoliertem Pilotbereich prüfen | eigener Tooling-Befund mit menschlicher Abnahme | produktive Figma- oder Codeänderung |
| spätere Projektableitung | generischen Baustein auf ein Vorhaben anwenden | Project Template, Projektkit und konkrete Library | Vorwegnahme ohne Projektbedarf |

Reale, historisch gewachsene Projekt-Libraries können in v0.2 als externe
Testfixtures dienen. Sie sind Testmaterial und weder Projektstand noch Quelle
für generische Standards. Ihre Werte, Namen und Strukturen werden nicht in das
Base Template übernommen.

## Testmodus und Systementwicklung

Ein Test prüft eine Fähigkeit oder Annahme; Systementwicklung verändert das
Zielsystem. Ein Testergebnis wird nicht allein dadurch zu einer Regel, dass ein
Tool ein plausibles Artefakt erzeugt.

| Merkmal | Test | Systementwicklung |
|---|---|---|
| Ziel | Erkenntnis über Fähigkeit, Grenze oder Eignung | tragfähige Regel oder wiederverwendbarer Baustein |
| Quelle | begrenzter Testkontext | bestätigte Zielsystem-Quelle und Entscheidungen |
| Artefakt | isoliert, reversibel, vorläufig | im Zielsystem verankert und versioniert |
| Ergebnis | Befund mit Unsicherheit und nächstem Test | überprüfbare Änderung mit Freigabe |
| Übernahme | niemals automatisch | erst nach menschlicher Entscheidung |

Ein Test darf das Zielsystem nur über den dokumentierten Rückfluss verändern:

```text
Test → Befund → menschliche Bewertung → Evaluation → gegebenenfalls Übernahme
```

Die Voraussetzungen und die kompakte Testkarte stehen in den
[Checklists](../operations/checklists.md). Für die laufende Arbeit genügt ein
Eintrag im Evaluation Log; eine zusätzliche Experimentstruktur wird nicht
angelegt, solange kein Nachweisbedarf besteht.

## Transparenz- und Selbstverständnisnachweis

Jeder relevante Befund und jeder Abschluss beginnt mit einem kurzen Nachweis:

| Feld | Angabe |
|---|---|
| Modus | `Test`, `Vorschlag`, `Pilot` oder `Systementwicklung` |
| Gegenstandsebene | `Fachliche Nutzung` oder `Systementwicklung` |
| Rolle | explizit gesetzt, automatisch abgeleitet oder `neutral` |
| Quellen | verwendete verbindliche oder geprüfte Quellen |
| Aktion | was gelesen, analysiert, vorgeschlagen, geändert oder validiert wurde |
| Automatik | was innerhalb bestätigter Regeln automatisch ausgeführt wurde |
| Mensch | was vorgegeben, geprüft, entschieden oder freigegeben wurde |
| Offen | offene Frage, Risiko oder benötigte Entscheidung |
| Nächster Schritt | genau eine nächste prüfbare Aktion |

Der Nachweis muss für eine dritte Person verständlich sein, ohne Chat-Verlauf
oder implizite Kenntnis. Er dokumentiert auch ausdrücklich, wenn nichts am
Zielsystem verändert wurde.

## 1. Verbindlicher Arbeitskontext

Jeder Arbeitsauftrag enthält mindestens:

| Feld | Regel |
|---|---|
| Ziel | Beschreibt den gewünschten überprüfbaren Zustand. |
| Gegenstand | Benennt das konkrete Artefakt und seine Fundstelle. |
| Übernahmeart | Bei Datei-, System- oder Librarygrenzen: `lokale Kopie`, `verknüpfte Instanz`, `Verschieben` oder `Rekonstruktion` sowie die zu erhaltenden Eigenschaften. |
| Nutzungsebene | Trennt fachliche Nutzung im Entwurf/Projekt von der Weiterentwicklung dieses Regel- und Toolingsystems. |
| Rolle/Perspektive | Legt den fachlichen Prüffokus und den erwarteten Output fest; verleiht keine Entscheidungsbefugnis. |
| Aktion | Ist eindeutig: lesen, analysieren, vorschlagen, Pilot anlegen, umsetzen oder validieren. |
| Umfang | Grenzt betroffene Bereiche und Zustände ab. |
| Grenzen | Benennt Verbote, verbindliche Quellen und nicht betroffene Bereiche. |
| Ergebnis | Benennt das erwartete Artefakt oder den Befund. |
| Abnahme | Legt fest, woran „fertig“ geprüft wird. |

Fehlt eine dieser Angaben, wird nur die kleinste nötige Annahme sichtbar
gemacht oder geklärt. Es wird kein großer Änderungsumfang daraus abgeleitet.
Eine Übernahmeart wird nie aus Begriffen wie „kopieren“, „duplizieren“ oder
„übertragen“ abgeleitet.

### Nutzungsebene nicht vermischen

`Fachliche Nutzung` bewertet, ob ein bestehendes oder vorgeschlagenes Muster
im Gestaltungs- und Entwicklungsalltag brauchbar ist. `Systementwicklung`
bewertet, ob Regeln, Quellen, Tooling oder Dokumentationsstrukturen das System
dauerhaft verbessern. Ein Befund darf beide Ebenen verbinden, muss Evidenz,
Abnahme und offene Entscheidung aber getrennt ausweisen.

## 2. Quellen, Regeln und Entscheidungen

Bei Widerspruch gilt diese Reihenfolge:

1. bestätigte, für den Fall gültige Entscheidung im Entscheidungslog
2. freigegebene projektspezifische Quelle
3. bestätigter projektübergreifender Standard
4. Entwurf oder Vorschlag

Bestehender Code, Figma-Bausteine und dokumentierte Entscheidungen gehen vor
neu erfundenen Lösungen. Unklare, widersprüchliche oder fehlende Vorgaben
werden als offene Frage oder Entscheidungsoption dokumentiert – nicht
stillschweigend ersetzt. Folgenreiche Entscheidungen und Ausnahmen erhalten
einen Eintrag in `docs/governance/decisions.md` mit Begründung und
Geltungsbereich.

## 3. Wiederverwendung und Bausteinvertrag

Vor jedem neuen Token, Pattern, jeder Komponente oder technischen Abstraktion:

1. Bestehende Bausteine prüfen.
2. Wiederverwenden, wenn Zweck und Grenzen passen.
3. Variieren, wenn der Unterschied begrenzt und nachvollziehbar ist.
4. Neu anlegen nur bei belegtem Bedarf; Zweck, Grenzen und Wiederverwendung
   dokumentieren.

Ein wiederverwendbarer Baustein besitzt mindestens diesen Vertrag:

| Vertragsfeld | Bedeutung |
|---|---|
| Zweck | Welches wiederkehrende Problem löst der Baustein? |
| Verwendung | Wann wird er eingesetzt? |
| Grenzen | Wann darf er nicht verwendet werden? |
| Varianten/Zustände | Welche zulässigen Unterschiede gibt es? |
| Verhalten | Welche Wirkung und Zustandsübergänge sind erforderlich? |
| Accessibility | Welche semantischen und bedienbezogenen Anforderungen gelten? |
| Abhängigkeiten | Welche Foundations, Bausteine oder Projektquellen werden benötigt? |
| Quelle | Wo liegen Design, Code oder die maßgebliche Dokumentation? |
| Status | `Entwurf`, `im Pilot`, `bestätigt`, `überarbeiten`, `verworfen` oder `abgelöst` |

Eine projektspezifische Ausnahme ist kein Reifegrad. Sie wird zusätzlich zum
Status gekennzeichnet und benötigt die in Abschnitt 4 beschriebene Freigabe.

### Erweiterungs- und Kompatibilitätsregel

Das Base Template standardisiert keine projektspezifischen Varianten,
Zustände, Werte oder Patterns im Voraus. Ein Bausteinvertrag muss aber sichtbar
machen, auf welchen Entscheidungsebenen spätere Projekte den Baustein
erweitern oder einschränken können.

Dabei werden mindestens vier Änderungsarten unterschieden:

| Änderungsart | Bedeutung | Folge |
|---|---|---|
| Kontextentscheidung | Ein Projekt oder Pattern wählt innerhalb des bestehenden Vertrags eine passende Nutzung. | Kein neuer Standard; Entscheidung im Projektkontext dokumentieren. |
| Additive Erweiterung | Eine neue Ausprägung ergänzt den Vertrag, ohne bisherige Bedeutung zu verändern. | Bestehende Ableitungen bleiben gültig; neue Nutzung braucht Freigabe. |
| Restriktive Änderung | Eine bisher mögliche Kombination wird eingeschränkt oder nicht mehr unterstützt. | Betroffene Ableitungen prüfen; Migrations- oder Ablösepfad benennen. |
| Semantische Korrektur | Die Rolle, das Verhalten oder die Accessibility-Anforderung ändert sich rückwirkend. | Migrationspflichtig; Entscheidung und Geltungsbereich dokumentieren. |

Eine Erweiterung darf bestehende Ableitungen nur stillschweigend ergänzen, wenn
sie additiv ist und Zweck, Rolle, Verhalten und Accessibility des Bausteins
unverändert bleiben. Alle anderen Änderungen werden als Entscheidung,
Ausnahme, Migration oder Ablösung behandelt.

### Vertrauensfähige Figma-Komponentendokumentation

Wenn ein Baustein in Figma dokumentiert wird, gilt die Dokumentation nur als
erfüllt, wenn sie nicht nur Inhalte enthält, sondern verlässlich nutzbar ist:
Menschen müssen Zweck, Status, Geltung, Beispiele, offene Punkte und Quellen
praktisch lesen und prüfen können; Agenten müssen dieselben Informationen über
sichtbare Textanker und Struktur auffinden können, ohne Bedeutung aus Layout,
Farbe oder Nähe zu erraten.

Formale Vollständigkeit, leere Gerüste, verdeckte Texte, kaputte Tabellen oder
prominente Pilot-/Governance-Blöcke gelten nicht als erfüllte
Komponentendokumentation. Die ausführbaren Anforderungen stehen in den
[Standards](../foundations/standards.md#figma-komponentendokumentation).

Komponenten-Erstellung, Komponenten-Prüfung und Komponenten-Dokumentation sind
getrennte Auftragsarten. Ein Komponentenpilot muss eine reale Komponente, ein
Component Set oder einen ausdrücklich benannten bestehenden
Komponenten-Gegenstand im Scope haben. Dokumentation darf den Baustein
erklären und prüfbar machen, ersetzt ihn aber nicht. Die bestätigte
Auftragsregel steht in [D-036](decisions.md#d-036--trennung-von-komponenten-erstellung--prufung-und--dokumentation).

## 4. Änderungsmodus und Entscheidungsrechte

Alle Änderungen erfolgen in einem expliziten Modus:

| Modus | Regel |
|---|---|
| Lesen | Nur Befund, keine Änderung. |
| Vorschlag | Entwurf außerhalb des Zielsystems; noch nicht verbindlich. |
| Pilot | Kleiner, abgegrenzter, prüfbarer Änderungsbereich. |
| Umsetzen | Freigegebene Änderung mit anschließender Validierung. |

Vor einer schreibenden oder standardverändernden Aktion werden Quellenklarheit,
Neuheit, Reichweite und Reversibilität eingeordnet.

| Fall | Agent | Mensch |
|---|---|---|
| Bestätigte Regel im freigegebenen Umfang anwenden | ausführen und Ergebnis dokumentieren | prüft bei Bedarf |
| Quelle ist unklar oder widersprüchlich | Befund und Optionen erstellen | entscheidet |
| Neuer Token, neue Komponente, neues Pattern oder neue Regel | Vorschlag mit Begründung erstellen | gibt frei |
| Große Reichweite, Überschreiben, Löschen oder externe Veröffentlichung | nicht ausführen | gibt vorher explizit frei |
| Projektspezifische Ausnahme | Ausnahme und Auswirkung dokumentieren | gibt frei |

Eine technische Schreibmöglichkeit überträgt keine Entscheidungsbefugnis.

### Eskalation und Nachweis

Ist eine menschliche Entscheidung erforderlich, erstellt der Agent keinen
verdeckten Ersatzentscheid, sondern legt einen kompakten Entscheidungsbefund
vor:

- Situation und betroffene Quellen
- zulässige Optionen einschließlich „nicht ändern“
- Auswirkung, Reichweite und Reversibilität je Option
- eigene Empfehlung als Vorschlag, nicht als Freigabe
- konkret benötigte menschliche Entscheidung

Nach Freigabe dokumentiert der Agent die folgenreiche Entscheidung oder
Ausnahme im Entscheidungslog. Routineanwendungen bestätigter Regeln werden
nicht einzeln geloggt.

## 5. Mindestnachweis für Qualität

Vor Abschluss muss sichtbar sein:

- Ziel, Umfang, Grenzen und Ergebnis stimmen überein.
- Wiederverwendung oder Neuanlage wurde begründet.
- Relevante Zustände und der reale Nutzungskontext wurden geprüft.
- Abweichungen, offene Fragen und nötige Freigaben sind benannt.
- Bei interaktiven Code-Artefakten: native Semantik zuerst; erforderliche
  Bedienbarkeit, Fokus und zugängliche Beschriftung geprüft.
- Bei konkreter Figma-zu-Code-Umsetzung: Design-Kontext, Screenshot, Assets
  und Vergleich gemäß `AGENTS.md` geprüft.

## 6. Lernschleife und Patternbibliothek

| Beobachtung | Konsequenz |
|---|---|
| Einzelfall oder projektspezifische Ausnahme | Nur im Projektkit dokumentieren. |
| Wiederkehrendes, bestätigtes Muster | Als Kandidat für das Base Template markieren. |
| Nach Review projektübergreifend tragfähig | Als Regel, Checkliste oder Baustein übernehmen. |
| Nicht tragfähig | Ablehnung oder Einschränkung im Entscheidungslog festhalten. |

So entsteht eine Patternbibliothek aus bestätigten Wiederholungen – nicht aus
frühzeitigem Vollständigkeitsanspruch.
