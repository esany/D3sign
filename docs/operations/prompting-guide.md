# Prompting Guide für Figma- und Design-System-Aufgaben

Status: Entwurf

Die [Tooling Map](../tooling/tooling-map.md) beantwortet: **Welches Werkzeug passt?**
Dieses Dokument beantwortet: **Wie formuliere ich den Auftrag so, dass Mensch
und Agent dasselbe tun?**

## Die acht Pflichtangaben

| Feld | Konkret bedeutet das | Beispiel |
|---|---|---|
| **Ziel** | gewünschter Endzustand, nicht die ganze Vorgeschichte | „Inkonsistenzen in der Detailansicht sichtbar machen“ |
| **Gegenstand** | konkretes Arbeitsobjekt mit Fundstelle | „Figma-File X, Seite Y, Frame Z, Node-Link …“ |
| **Nutzungsebene** | fachliche Nutzung eines Projekts oder Weiterentwicklung des Repros | „Fachliche Nutzung“ oder „Systementwicklung“ |
| **Rolle/Perspektive** | fachlicher Prüffokus des Auftrags | „Design“, „Development“, „Review“ oder „Governance“ |
| **Aktion** | gewünschte Tätigkeit; siehe Aktionsrepertoire unten | „analysieren“, „Pilot anlegen“, „Code umsetzen“ |
| **Umfang** | klare Begrenzung des Arbeitsbereichs | „nur dieser Frame, drei Zustände, keine Library“ |
| **Grenzen** | Was darf nicht passieren? Welche Quellen sind verbindlich? | „nichts überschreiben; vorhandene Tokens verwenden“ |
| **Ergebnis** | Form des Outputs | „Figma-Pilotseite plus Entscheidungsnotiz“ |
| **Abnahme** | prüfbares Kriterium für „fertig“ | „jede Variante ist sichtbar und per Screenshot geprüft“ |

Die Rolle legt fest, worauf der Agent schaut und welches Ergebnis er liefert.
Sie überträgt keine Entscheidungsbefugnis. Ohne Rollenangabe gilt eine
neutrale Analyseperspektive. Bei Routineaufträgen darf der Agent die Rolle aus
Gegenstand und Aktion ableiten; bei gemischten oder folgenreichen Aufträgen
weist er die Annahme aus oder bittet um Klärung.

### Gegenstand richtig benennen

Der Gegenstand ist kein großer Fließtext, sondern eine auffindbare Referenz.
Benenne möglichst:

```text
Gegenstand:
- Figma-Datei: „Analyse-Portal“
- Seite: „03 – Detailansicht“
- Frame/Node: „Messstelle – Tagesansicht“
- Node-Link: https://www.figma.com/design/…?node-id=123-456
- Betroffen: Filterleiste und Detailpanel
- Nicht betroffen: globale Navigation und Token-Bibliothek
```

Bei Dokumentationsarbeit ist der Gegenstand das Zielartefakt:

```text
Gegenstand:
- Quelle: freigegebener Arbeitsbefund oder verlinkte Datei
- Ziel: `docs/operations/workflows.md`, Abschnitt „Design-Review“
- Referenzen: bestehender Projektworkflow und offene Entscheidung D-003
```

Bei Komponentenarbeit wird zusätzlich die Auftragsart getrennt.
`Komponente erstellen`, `Komponente prüfen` und `Komponente dokumentieren`
sind verschiedene Schritte. Sie können kombiniert werden, aber nur mit
sichtbarer Reihenfolge und Abnahme:

```text
Auftragsart:
- zuerst Komponente erstellen: echtes Figma-Component Set „Button / Pilot“
- danach genau diese Komponente dokumentieren
- nicht: nur eine Dokumentationsfläche über einen Button anlegen
```

Wenn kein echter Komponenten-Gegenstand benannt oder zu erzeugen ist, behandelt
der Agent den Auftrag nicht als Komponentenpilot, sondern als
Dokumentationsentwurf oder fragt gezielt nach.

## Aktionsrepertoire und Werkzeugrepertoire

Die **Aktion** ist das, was getan werden soll. Das **Werkzeugrepertoire** ist,
was ein Skill oder MCP technisch leisten kann. Beides nicht vermischen.

| Aktion | Typische Figma-/Southleft-Funktion | Schreibend? |
|---|---|---|
| lesen | Node-Kontext, Metadaten, Variablen, Assets, Screenshot abrufen | nein |
| analysieren | Struktur, Varianten, Zustände oder Inkonsistenzen auswerten | nein |
| beraten | Design-System-, Accessibility- oder Token-Empfehlung geben | nein |
| vorschlagen | Entwurf als Text, Checkliste, Workflow oder Entscheidungsoption | nein |
| Pilot anlegen | begrenzten Figma-Bereich oder kleines Artefakt erzeugen | ja, begrenzt |
| umsetzen | freigegebene Figma- oder Code-Änderung durchführen | ja |
| verbinden | Code Connect zwischen Node und Code-Komponente anlegen | ja |
| übertragen | Code/Webseite als editierbare Figma-Darstellung erzeugen | ja |
| validieren | visuellen, funktionalen oder strukturellen Abgleich durchführen | meist nein |

Eine Aktion kann mehrere technische Funktionen nutzen. Beispiel: „Screen als
Code umsetzen“ nutzt Design-Kontext, Screenshot, Assets und Validierung – der
Auftrag bleibt trotzdem eine einzige Aktion: **umsetzen**.

### Agenteninterne Tool- und Promptoptimierung

Die Auswahl der konkreten Funktion und die Formulierung des internen
Systemprompts übernimmt der Agent. Er wählt die kleinste Funktion, die den
benötigten Kontext vollständig abdeckt, und optimiert innerhalb des
vereinbarten Umfangs für Token- und Iterationsökonomie.

Eine Optimierung darf Ziel, Scope oder Abnahme nicht stillschweigend
verändern. Wenn eine Funktion nur einen engeren Ausschnitt liefert oder die
Anfrage wegen Tool-, Kontext- oder Tokenlimits nicht vollständig ausführbar
ist, weist der Agent die Einschränkung und ihre Auswirkung aus. Bei einer
folgenschweren Einschränkung fragt er gezielt nach; er ersetzt die Anfrage
nicht eigenmächtig durch eine vermeintlich passende Handlung.

### Übernahme zwischen Systemen oder Dateien

Bei `kopieren`, `duplizieren`, `übertragen`, `importieren`, `verschieben` oder
`synchronisieren` reicht das gewünschte Ergebnis nicht als Aktion. Der Agent
klärt vor der Toolwahl Übernahmeart (`lokale Kopie`, `verknüpfte Instanz`,
`Verschieben` oder `Rekonstruktion`), Erhaltungsziel und Funktionsklasse.
Danach prüft er den dokumentierten Scope der kleinsten konkreten Funktion.
Deckt sie die bestätigte Übernahmeart nicht direkt ab, stoppt er vor jeder
Änderung; Import oder Rekonstruktion ist keine zulässige Ersatzhandlung ohne
eine neue sichtbare Auswahl.

Die Zuordnung der Aktion zu tatsächlich implementierten Skills und MCP-
Funktionen steht getrennt in [Figma MCP Tooling](../tooling/figma-mcp-tooling.md) und
[Southleft Tooling](../tooling/southleft-tooling.md). Im Auftrag sollten diese Ebenen –
wenn relevant – getrennt benannt werden:

```text
Aktion: umsetzen
Werkzeugfamilie: Figma-eigenes MCP
Skill/Workflow: figma-design-to-code
Technische Funktionen: Design-Kontext, Screenshot, Assets, Validierung
```

Bei Southleft Console entsprechend:

```text
Aktion: Variablen gesammelt aktualisieren
Werkzeugfamilie: Southleft Figma Console MCP
Technische Funktion: Batch-Variablenfunktion über verbundene Desktop-Bridge
```

## Schreibmodus

### Zweistufiger Ablauf: `PROMPT` und `AUSFÜHREN`

Bei unstrukturierten Aufträgen wird zuerst `PROMPT` verwendet. Der Agent klärt
den Auftrag in verständlicher Sprache und weist mindestens aus:

- Ziel und Quelle
- „Ich prüfe“ und „Ich prüfe nicht“
- Arbeitsmodus und Rolle
- gewählte Tool-Funktion und kurze Begründung
- Grenzen, offene Fragen und Abnahme

Erst mit `AUSFÜHREN` wird die bestätigte Aktion gestartet. Der Mensch muss den
strukturierten Auftrag nicht kopieren. Technische Kennungen wie File-Key,
Node-ID oder Set-Key werden nur als Nachweis angezeigt, sofern sie für die
Nachvollziehbarkeit relevant sind.

Der alleinstehende Text `AUSFÜHREN` ist dabei der Ausführungscode, nicht bloß
eine Formulierung in der Abschlusszeile: Er führt genau den unmittelbar vorher
bestätigten und noch nicht ausgeführten Prompt aus. Gibt es keinen solchen
Prompt oder ist er bereits erledigt, führt der Agent nichts Neues aus und
benennt den fehlenden Bezug.

Jeder ausführungsbereite `PROMPT` endet mit einer sichtbaren Abschlusszeile:

```text
Mit `AUSFÜHREN` führe ich [konkret bestätigte Aktion] im Modus [Modus] aus.
```

Sie macht die Freigabeschwelle, erwartete Handlung und Grenze zwischen Planung
und Ausführung wiedererkennbar. Sie ergänzt keine Aktion und verändert weder
Scope noch Entscheidungsrecht.

### `START CHAT` – bedarfsorientierter Einstieg (Pilot)

`START CHAT` ist ein optionaler Kurzbefehl für eine neue oder bewusst
wiederaufgenommene Arbeit. Er aktiviert den Kontextstart-Piloten, übernimmt
den erkennbaren Arbeitsstand selbst und ersetzt weder eine Entscheidung noch
eine Freigabe.

```text
START CHAT

Lies AGENTS.md. Übernimm den erkennbaren Gesprächs- oder Arbeitsstand und
leite Nutzungsebene, Rolle, Quellen und Toolbedarf selbst ab. Lies dann nur
den passenden Einstieg: Fachliche Nutzung → wiki/README.md;
Systementwicklung → docs/README.md; verbunden → beide, mit getrennten
Befunden und Abnahmen. Ist kein Anliegen ableitbar, lies beide Einstiegskarten
und kennzeichne die Einordnung als vorläufig; frage nicht nach einer Auswahl.
Suche anschließend nur die für Gegenstand, Decision, Evaluation oder Stichwort
zuständigen Quellen.

Prüfe für ein erst durch die Aufgabe benötigtes Werkzeug: Verfügbarkeit,
tatsächlichen Scope, Zugriff oder Laufzeit und belastbare Alternative.
Teste und lade keine nicht benötigten Tools. Eine konfigurierte Verbindung ist
kein Funktionsnachweis; externe Wissens-MCPs zählen erst mit passenden,
quellenzuordenbaren Treffern als Evidenz.

Nenne vor der Arbeit den abgeleiteten oder vorläufigen Arbeitsstand: Ziel,
Gegenstand, Nutzungsebene, Modus, Rolle, tatsächlich gelesene Quellen,
benötigtes Tooling mit Status (einsatzbereit/eingeschränkt/nicht verfügbar),
bewusst nicht Gelesenes sowie offene Entscheidungen.
```

Bei einer folgenreichen Wiederaufnahme ergänzt der Agent den Anschlusskern des
letzten relevanten Befunds: Absicht, Erkenntnis, Geltung oder Grenze,
Offenheit und nächster Schritt. Der Kurzbefehl ist kein Volltest des gesamten
Toolings; „einsatzbereit“ bedeutet immer: für diese Aufgabe verfügbar und
passend. Details zum Kontextpfad stehen in der [operativen
Dokumentation](../README.md), zur Toolwahl in der [Tooling
Map](../tooling/tooling-map.md).

Die wiederholbare Abnahme des Shortcuts steht als [Testkarte für
Kontext-Shortcuts](checklists.md#testkarte-für-kontext-shortcuts) in den
Checklists. Sie prüft vier reale Startarten, ohne einen eigenen Testprozess zu
erzeugen.

Immer einen Modus nennen:

- **Lesen:** keine Änderungen, nur Befund
- **Vorschlag:** Entwurf außerhalb von Figma oder Code
- **Pilot:** begrenzte Änderung zur Prüfung
- **Umsetzen:** freigegebene Änderung mit anschließender Validierung

## Entscheidungsmodus

Der Schreibmodus beschreibt, **wie** gearbeitet wird. Der Entscheidungsmodus
beschreibt, **wer** die fachliche Entscheidung trägt:

- **innerhalb bestätigter Regeln ausführen:** Agent darf im beschriebenen
  Umfang handeln und dokumentiert das Ergebnis.
- **Vorschlag zur Freigabe:** Agent bereitet Optionen und Empfehlung vor;
  keine Entscheidung oder Änderung wird vorweggenommen.
- **nur lesen:** Agent erstellt ausschließlich einen Befund.

Fehlt die Angabe, gilt die Einordnung aus dem
[Base Template](../governance/base-template.md). Bei Unklarheit oder einer neuen Regel ist
„Vorschlag zur Freigabe“ der Standard.

## Kurzvorlage

```text
Ziel: …
Gegenstand: …
Übernahmeart / Erhaltungsziel: … (bei Datei-, System- oder Librarygrenzen)
Nutzungsebene: Fachliche Nutzung | Systementwicklung
Rolle/Perspektive: Design | Development | Review | Governance
Aktion: lesen | analysieren | beraten | vorschlagen | Pilot | umsetzen | verbinden | übertragen | validieren
Umfang: …
Entscheidungsmodus: innerhalb bestätigter Regeln ausführen | Vorschlag zur Freigabe | nur lesen
Werkzeug: Figma-eigenes MCP | Southleft Figma Console | Southleft Design Systems | offen
Grenzen: …
Ergebnis: …
Abnahme: …
Abschluss: Mit `AUSFÜHREN` führe ich [konkret bestätigte Aktion] im Modus [Modus] aus.
```

## Beispielprompts passend zur Tooling Map

### 1. Figma-Datei, Seite oder Node verstehen

```text
Ziel: Die Struktur und Zustände dieses Screens verstehen.
Gegenstand: Figma-File <URL>, Seite „Dashboard“, Frame „Detailansicht“, Node-Link <URL>
Aktion: lesen und analysieren
Umfang: sichtbare Bereiche, Komponenten, Varianten und Variablen dieses Frames
Werkzeug: Figma-eigenes MCP
Grenzen: nichts ändern; keine fachlichen Annahmen ergänzen
Ergebnis: strukturierter Befund mit offenen Fragen
Abnahme: Jeder Bereich ist einem konkreten Node oder einer sichtbaren Beziehung zugeordnet.
```

### 2. Konkreten Figma-Screen als Code umsetzen

```text
Ziel: Den Screen als React-Komponente umsetzen.
Gegenstand: Frame „Messstelle – Tagesansicht“, Node-Link <URL>
Aktion: umsetzen
Umfang: Desktop-Ansicht sowie Loading-, Empty- und Error-Zustand
Werkzeug: Figma-eigenes MCP plus `figma-design-to-code`
Grenzen: vorhandene Komponenten und Tokens verwenden; keine neue Icon-Bibliothek
Ergebnis: Code, verwendete Assets und Liste verbleibender Abweichungen
Abnahme: Design-Kontext und Screenshot abgerufen; visueller und funktionaler Vergleich durchgeführt.
```

### 3. Code Connect anlegen

```text
Ziel: Die Figma-Komponente mit der bestehenden Code-Komponente verbinden.
Gegenstand: Figma-Komponente „StatusBadge“, Node-Link <URL>; Code `src/components/StatusBadge.tsx`
Aktion: verbinden
Umfang: nur diese Komponente und ihre dokumentierten Varianten
Werkzeug: Figma `figma-code-connect-components`
Grenzen: keine Komponente im Code ändern; keinen Node erraten
Ergebnis: Code-Connect-Zuordnung und Prüfhinweis
Abnahme: Mapping zeigt exakt auf Node und reale Quelldatei.
```

### 4. Neue Figma-Datei anlegen

```text
Ziel: Eine neue Datei als Arbeitsraum für den Design-System-Piloten anlegen.
Gegenstand: neue Datei, Name „Design System Pilot“
Aktion: erzeugen
Umfang: leere Design-Datei im vorgesehenen Team/Projekt
Werkzeug: Figma `figma-create-new-file`
Grenzen: noch keine Komponenten oder Seiteninhalte erzeugen
Ergebnis: Figma-URL und File-Key
Abnahme: Datei ist erreichbar und editierbar.
```

### 5. Komponentenbibliothek oder Tokens erzeugen

```text
Ziel: Eine kleine Foundations- und Komponentenbibliothek als Pilot erzeugen.
Gegenstand: Figma-Datei <URL>, Seite „Foundations“, vorhandene Tokens <Referenz>
Aktion: Pilot anlegen
Umfang: Farbrollen, Typografie, Spacing und eine Status-Komponente
Werkzeug: Figma `figma-generate-library`
Grenzen: keine vollständige Library; bestehende Tokens nicht überschreiben
Ergebnis: editierbarer Pilot mit Benennung und offenen Entscheidungen
Abnahme: Pilot ist visuell geprüft und jede Variable hat eine dokumentierte Rolle.
```

### 6. Code oder Website nach Figma übertragen

```text
Ziel: Die lokale Web-Seite als editierbare visuelle Referenz nach Figma übertragen.
Gegenstand: lokale URL `http://localhost:3000/detail`, Ziel-File <URL>
Aktion: übertragen
Umfang: Route `/detail`, Desktop-Breakpoint
Werkzeug: Figma `figma-generate-design`
Grenzen: bestehende Zielseite nicht überschreiben; Ergebnis als Referenz markieren
Ergebnis: neue editierbare Figma-Seite
Abnahme: Route wurde vollständig erfasst und die Zielseite ist auffindbar.
```

### 7. FigJam-Diagramm erzeugen

```text
Ziel: Den Design-Review-Workflow als verständliches Ablaufdiagramm darstellen.
Gegenstand: neues oder bestehendes FigJam-Board <URL>
Aktion: erzeugen
Umfang: maximal 7 Schritte, Rollen und zwei Entscheidungspunkte
Werkzeug: Figma `figma-generate-diagram`
Grenzen: keine zusätzlichen Prozesse erfinden; Texte kurz halten
Ergebnis: editierbares FigJam-Diagramm
Abnahme: Start, Ende, Verantwortlichkeiten und Entscheidungspfade sind eindeutig.
```

### 8. FigJam-Inhalt bearbeiten

```text
Ziel: Die bestehende Workshop-Struktur aufräumen und drei Bereiche benennen.
Gegenstand: FigJam-Board <URL>, Bereich „Workshop 01"
Aktion: umsetzen
Umfang: nur dieser Bereich
Werkzeug: Figma `figma-use-figjam`
Grenzen: keine Notizen löschen; bestehende Inhalte nur verschieben oder gruppieren
Ergebnis: geordneter Bereich mit klaren Überschriften
Abnahme: Alle ursprünglichen Notizen sind weiterhin auffindbar.
```

### 9. Figma-Slides bearbeiten

```text
Ziel: Die Review-Präsentation um eine Entscheidungsfolie ergänzen.
Gegenstand: Figma-Slides-Datei <URL>, Abschnitt „Review"
Aktion: Pilot anlegen
Umfang: eine neue Folie mit Problem, Optionen und Entscheidung
Werkzeug: Figma `figma-use-slides`
Grenzen: bestehendes Layout und Typografie verwenden
Ergebnis: editierbare Folie
Abnahme: Folie ist in der bestehenden Reihenfolge und als Entwurf markiert.
```

### 10. Motion oder Animation ableiten

```text
Ziel: Das Übergangsverhalten zwischen Listen- und Detailansicht definieren.
Gegenstand: Figma-Prototype <URL>, Übergang „Liste → Detail"
Aktion: beraten und vorschlagen
Umfang: Dauer, Auslöser, Richtung und Easing für einen Übergang
Werkzeug: Figma `figma-use-motion` oder `figma-implement-motion`
Grenzen: keine neuen visuellen Komponenten; reduzierte Bewegung berücksichtigen
Ergebnis: dokumentierte Motion-Spezifikation
Abnahme: Verhalten, Fallback und Accessibility-Hinweis sind benannt.
```

### 11. SwiftUI-/iOS-Umsetzung

```text
Ziel: Den Screen als SwiftUI-View strukturieren.
Gegenstand: Figma-Frame „Detailansicht“, Node-Link <URL>
Aktion: umsetzen
Umfang: iPhone-Layout und relevante Zustände
Werkzeug: Figma `figma-swiftui`
Grenzen: native iOS-Konventionen beachten; keine Web-Komponenten annehmen
Ergebnis: SwiftUI-Struktur mit Mapping der Figma-Komponenten
Abnahme: Layout, Zustände und Bedienbarkeit auf kleiner Breite geprüft.
```

### 12. Allgemeine Design-System-Beratung

```text
Ziel: Prüfen, ob die vorgeschlagene Status-Komponentenstruktur sinnvoll ist.
Gegenstand: Beschreibung und Screenshots im Dokument `docs/foundations/standards.md`
Aktion: beraten
Umfang: Rollen, Varianten, Zustände, Benennung und Accessibility
Werkzeug: Southleft Design Systems
Grenzen: keine Figma-Datei ändern; keine projektspezifische Entscheidung vorwegnehmen; nur passende, quellenzuordenbare Treffer als externe Evidenz verwenden
Ergebnis: Empfehlungen mit Begründung und offenen Fragen
Abnahme: Jede Empfehlung ist als Empfehlung, nicht als verbindlicher Standard markiert; bei fehlenden passenden Treffern ist die Tooling-Grenze sichtbar und eine Primärquelle als Rückfallebene benannt.
```

### 13. Figma Console-/Bridge-Aktion

```text
Ziel: Die bestehende Figma-Seite visuell prüfen und drei gleichartige Variablen gesammelt aktualisieren.
Gegenstand: geöffnete Figma-Datei, Seite „Foundations", Variablen <Namen>
Aktion: validieren und umsetzen
Umfang: nur diese Variablen und die zugehörige Seite
Werkzeug: Southleft Figma Console MCP
Grenzen: Bridge-Zustand zuerst prüfen; keine anderen Variablen ändern
Ergebnis: aktualisierte Variablen plus Screenshot und Änderungsbericht
Abnahme: Screenshot geprüft; alle Änderungen sind im Bericht aufgelistet.
```

### 14. Projektbezogene Agentenregeln erzeugen

```text
Ziel: Projektregeln für Figma-zu-Code-Aufgaben erzeugen.
Gegenstand: Repository <Pfad>, vorhandene Codebasis und Konventionen
Aktion: analysieren und erzeugen
Umfang: Komponentenstruktur, Styling, Tokens, Assets und Figma-MCP-Ablauf
Werkzeug: Figma `figma-create-design-system-rules`
Grenzen: keine fachlichen Designstandards erfinden; bestehende Regeln erhalten
Ergebnis: ergänzte `AGENTS.md` mit projektbezogenen, überprüfbaren Regeln
Abnahme: Regeln sind aus der Codebasis belegbar und bleiben technologie-/team-portabel.
```

## Agentenregel

Fehlen Ziel, Gegenstand oder Aktion, nicht mehrere Tools auf Verdacht aufrufen.
Zuerst die kleinste notwendige Klärung einholen oder die getroffene Annahme
sichtbar machen. Große Schreibaktionen in Figma immer in einen prüfbaren Pilot
und eine anschließende Erweiterung teilen.
