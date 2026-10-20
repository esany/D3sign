# Project Agent Rules

Diese Datei ist die kurze, unmittelbar ausführungsrelevante Einstiegskarte für
Agenten. Sie enthält Sicherheits-, Routing- und Transparenzregeln. Fachliche
Standards, ausführliche Abläufe und menschliche Vermittlung liegen in den
verlinkten Quellen.

## Verbindliche Quellen

- [Operative Dokumentation](docs/README.md) – Quellen- und Funktionsmatrix
- [Base Template](docs/governance/base-template.md) – Governance, Modi und
  Mensch–Maschine-Arbeitsteilung
- [Decisions](docs/governance/decisions.md) – bestätigte Entscheidungen,
  Ausnahmen und Ablösungen
- [Evaluation Framework](docs/governance/evaluation-framework.md) und
  [Evaluation Log](docs/governance/evaluation-log.md) – Qualitätsnachweis
- [Prompting Guide](docs/operations/prompting-guide.md) – Auftragsformat und
  `PROMPT`/`AUSFÜHREN`
- [Checklists](docs/operations/checklists.md) – operative Prüfungen
- [Tooling Map](docs/tooling/tooling-map.md) – Auswahl passender Funktionen
- [Projekt-Wiki](wiki/README.md) – menschenorientierte Einordnung

Jede Regel hat genau eine verbindliche Detailquelle. Eine Kürzung oder
Verschiebung ist nur zulässig, wenn die Funktion in der Zielquelle auffindbar
ist und die Verknüpfung geprüft wurde. Inhalte und Schutzwirkungen dürfen
nicht verloren gehen.

## Arbeitskontext vor jeder Aktion

Vor Lesen, Schreiben oder Bewertung sind sichtbar zu bestimmen:

- **Ziel** und **Gegenstand** (konkretes Artefakt mit Fundstelle)
- **Nutzungsebene:** `Fachliche Nutzung` oder `Systementwicklung`
- **Modus:** `Lesen`, `Vorschlag`, `Pilot` oder `Umsetzen`
- **Rolle:** `Design`, `Development`, `Review`, `Governance` oder `neutral`
- **Aktion**, **Umfang**, **Grenzen**, **Ergebnis** und **Abnahme**

`Fachliche Nutzung` bewertet die Brauchbarkeit im Entwurfs- und
Entwicklungsalltag. `Systementwicklung` bewertet Regeln, Quellen, Tooling und
Dokumentationsstrukturen. Ein verbundener Befund weist beide Ebenen getrennt
aus. Fehlt eine entscheidende Angabe, wird gezielt rückgefragt oder nur die
kleinste sichtbare Annahme getroffen.

## Änderungs- und Entscheidungsrechte

- Lesen verändert nichts.
- Ein Vorschlag bleibt außerhalb des Zielsystems unverbindlich.
- Ein Pilot ist klein, isoliert, reversibel und ausdrücklich begrenzt.
- Umsetzen erfolgt nur innerhalb bestätigter Regeln und des freigegebenen
  Umfangs.
- Neue Regeln, neue Tokens/Patterns, große Änderungen, Überschreiben, Löschen,
  Veröffentlichung und projektspezifische Ausnahmen benötigen menschliche
  Freigabe.
- Bei unklarer oder widersprüchlicher Quelle legt der Agent Befund, Optionen,
  Auswirkungen und die benötigte Entscheidung vor; er ersetzt sie nicht
  stillschweigend.
- Technische Schreibfähigkeit verleiht keine fachliche Entscheidungsbefugnis.
- Folgenreiche Entscheidungen, Ausnahmen und Ablösungen werden im
  [Decision Log](docs/governance/decisions.md) dokumentiert. Routineanwendung
  bestätigter Regeln wird nicht einzeln geloggt.

## Test und Systementwicklung

Ein `Test` prüft eine begrenzte Fähigkeit oder Annahme; er verändert keine
kanonische Quelle. `Systementwicklung` erstellt oder ändert eine bestätigte
Regel, einen Baustein oder eine Zielstruktur. Der zulässige Rückfluss lautet:

```text
Test → Befund → menschliche Bewertung → Evaluation → gegebenenfalls Übernahme
```

Tests haben eine Prüffrage, eine begrenzte Quelle, ein Abbruchkriterium,
benanntes Tooling und eine menschliche Prüfung. Ergebnisse sind zunächst
Befunde, keine Standards. Die Testtiefe bleibt dem Risiko proportional; die
Regelbindung und Auswahl stehen in den [Checklists](docs/operations/checklists.md).

## Transparenzpflicht

Jeder relevante Befund oder Abschluss nennt kompakt:

- Modus, Nutzungsebene und Rolle (explizit, abgeleitet oder `neutral`)
- Quellen, gewählte Funktion und tatsächlichen Scope
- automatisch ausgeführt, nicht verändert und menschlich geprüft/entschieden
- Tooling-Grenzen, offene Fragen/Freigaben und genau einen nächsten Schritt

Nicht sichtbare Aspekte gelten als `nicht bewertet` oder `eingeschränkt
bewertet`, nie als fachlicher Mangel. In Evaluationen stehen Evidenz- und
Toolingstatus vor fachlichen Ableitungen.

## PROMPT, AUSFÜHREN und Regelkandidaten

Bei unstrukturierten oder kontextabhängigen Aufträgen erzeugt `PROMPT` zuerst
eine verständliche Bestätigung mit Ziel, Gegenstand, Nutzungsebene, Scope,
Nicht-Scope, Modus, Rolle, gewählter Funktion, Grenzen, offenen Fragen und
Abnahme. Erst `AUSFÜHREN` startet die bestätigte Aktion. Die technische
Funktionswahl liegt beim Agenten; Ziel, Umfang und Abnahme dürfen dabei nicht
stillschweigend verändert werden. Bei verbleibender Unsicherheit wird
gezielt rückgefragt.

Eine alleinstehende Nutzernachricht `AUSFÜHREN` ist der Ausführungscode: Der
Agent führt den unmittelbar vorher bestätigten, noch nicht ausgeführten
`PROMPT` in dessen festgelegtem Umfang aus. Fehlt ein solcher Prompt oder ist
er bereits ausgeführt, erklärt der Agent die Grenze statt eine neue Aktion zu
erraten.

Jeder ausführungsbereite `PROMPT` endet sichtbar mit: „Mit `AUSFÜHREN` führe
ich [konkret bestätigte Aktion] im Modus [Modus] aus.“ Die Zeile macht die
bestehende menschliche Freigabe und Handlungsgrenze erkennbar; sie erweitert
weder Scope noch Entscheidungsrecht.

## Kontextstart und Wiederaufnahme (Pilot)

`AGENTS.md` ist der Arbeitsvertrag, nicht das Projektarchiv. Vor einer neuen
oder wiederaufgenommenen Arbeit übernimmt und bestimmt der Agent den
erkennbaren Anliegen- und Arbeitsstand samt Nutzungsebene selbst: bei
`Fachliche Nutzung` liest er zunächst `wiki/README.md` nur zur Einordnung; die
Wiki-Detailseiten werden wegen der pausierten Pflege nur bei ausdrücklichem
Wiki-Auftrag oder begründeter Relevanz geladen. Bei
`Systementwicklung` zuerst `docs/README.md`, bei verbundenem Anliegen beide
Ebenen getrennt. Ist kein Anliegen ableitbar, liest er automatisch beide
Einstiegskarten und kennzeichnet die Einordnung als vorläufig, statt eine
Auswahl abzufragen. Danach sucht und liest er nur die für Gegenstand,
Decision, Evaluation oder Stichwort zuständigen Quellen. Bei folgenreicher
Fortsetzung liest er zusätzlich den letzten relevanten Befund mit seinem
Anschlusskern. Volllektüre von Wiki, `docs/` oder Logs erfolgt nur bei
begründetem Bedarf. Die Detailmatrix und Pilotgrenze stehen in `docs/README.md`.
`START CHAT` ist der optionale, im Prompting Guide definierte Auslöser dieses
Piloten; er fügt keine pauschale Toolprüfung hinzu.

Bei einer Übernahme zwischen Dateien, Systemen, Libraries oder Accounts
klärt der Agent vor der Toolwahl die Übernahmeart: `lokale Kopie`,
`verknüpfte Instanz`, `Verschieben` oder `Rekonstruktion`, einschließlich der
zu erhaltenden Eigenschaften. Er bestimmt zuerst die Funktionsklasse und
prüft dann den tatsächlichen Scope der konkreten Funktion. Deckt sie die
bestätigte Übernahmeart nicht ab, stoppt er; Import, Rekonstruktion oder ein
anderer Ersatzweg benötigen eine neue sichtbare Auswahl.

Erkennt der Agent eine mögliche wiederverwendbare Regel, kennzeichnet er sie
als `Regelkandidat`. Erst `REGEL SETZEN` überführt sie in die zuständigen
Steuerungsquellen und das Decision Log.

`Status sichern` überträgt eindeutig zuordenbare, bestätigte Inhalte in die
passende `docs/`-Quelle. Unklare Aussagen bleiben als Entwurf, offene Frage
oder Entscheidungsoption markiert. Der Abschluss nennt immer das konkrete
Delta: neu gesichert, geändert, bewusst nicht übernommen und weiterhin offen.

## Wiki und Dokumentationsgrenzen

Die Wiki vermittelt Menschen Zweck, Kontext, Status, Wirkung, Rollen,
Entscheidungen und nächste Schritte; sie folgt menschlichen Fragen und
verweist auf verbindliche Detailquellen. `docs/` enthält ausführbare Regeln,
Prüfschritte und maschinenlesbare Statuswerte. Keine operative Regel wird in
der Wiki dupliziert. Die Wiki-Pflege ist vorläufig pausiert: Routineänderungen
lösen keine Wiki-Aktualisierung aus. Eine Wiki-Änderung erfolgt nur bei einem
ausdrücklichen Wiki-Auftrag oder nach einer gezielten Relevanzprüfung.

Bei Wiki- oder Strukturänderungen gilt `WIKI PRÜFEN`: Zweck, Zielgruppe,
selektives Lesen, Status, Rollenpassung, semantische Auszeichnung,
Quellenpassung sowie technische, strukturelle und semantische Linkebene
prüfen. Der Testumfang (Dateien, Links, Tabellenzeilen, Pflichtfelder,
Fehler, nicht geprüft) wird ausgewiesen.

## Lean- und Erhaltungsprüfung

Vor jeder Struktur- oder Regeländerung wird geprüft, ob sie dem Ziel dient,
kleinste ausreichende Umsetzung ist, keinen doppelten Prozess/keine unnötige
Datei erzeugt und Pflege-, Token- und Iterationsaufwand rechtfertigt. Vor dem
Verschieben oder Kürzen wird eine Quellen-/Funktionszuordnung erstellt; erst
danach wird die alte Darstellung entfernt. Bestehende Funktionen und
Schutzwirkungen für Lesen, Pilot und Standardänderung müssen nachvollziehbar
erhalten bleiben.

## Tooling und Figma

Für konkrete Figma-Dateien oder -Nodes wird die kleinste tatsächlich passende
Figma-Funktion gewählt; allgemeine Design-System-Beratung kann Southleft
nutzen. Diese Werkzeugfamilien werden nicht stillschweigend ersetzt oder
simuliert. Nichtverfügbarkeit, tatsächlicher Scope und verbleibende Lücken
werden offengelegt. Die jeweiligen Skill-Anweisungen sind vor der Aktion zu
laden.

Bei Figma-zu-Code gilt zusätzlich: exakten Node-Kontext abrufen, Screenshot
des Node abrufen, erst danach Assets/Code erzeugen und anschließend visuell
und funktional validieren. Keine Framework- oder Styling-Annahme ohne
vorhandene Codebasis.

## Allgemeine Leitplanken

- Bestehende Quellen und Bausteine vor Neuerstellung prüfen.
- Keine Framework-, Build- oder Stylingannahme treffen, solange keine
  entsprechende Codebasis vorhanden ist.
- Keine impliziten Annahmen als Fakten oder Standards ausgeben.
- Änderungen klein, nachvollziehbar und reversibel halten.
- Rollen steuern Perspektive und Output, nicht Freigaberechte.
- Bei Unsicherheit über eine folgenschwere Regel gezielt fragen.
