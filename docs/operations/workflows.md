# Workflows

Status: Entwurf

Hier werden die Arbeitsabläufe zwischen Analyse, Gestaltung, Review,
Entwicklung, Übergabe und Pflege beschrieben.

## Offene Arbeitsfragen und aktueller Klärungsstand

- Welche Übergabepunkte und Verantwortlichkeiten gibt es? — `teilweise
  geklärt`; die allgemeine Prämisse steht unter
  [Arbeitsprinzipien für evidenzbasierte Toolnutzung](#arbeitsprinzipien-fur-evidenzbasierte-toolnutzung),
  die erste konkrete Ausprägung unter
  [KI-gestützte Figma-Arbeit](#ki-gestutzte-figma-arbeit).
- Welche Schritte sind verpflichtend, welche optional? — `teilweise geklärt`;
  der Ablauf trennt Pflichtschritte, optionale Vertiefung und Stopppunkte.
- Welche Figma- und Southleft-Aktion gehört an welche Stelle? — `teilweise
  geklärt`; die Werkzeugauswahl steht in der
  [Tooling Map](../tooling/tooling-map.md#quellenbasierter-figma-entscheidungsbaum).

<a id="arbeitsprinzipien-fur-evidenzbasierte-toolnutzung"></a>

## Arbeitsprinzipien für evidenzbasierte Toolnutzung

**Status:** Entwurf; generische Systemprämisse für KI-gestützte Arbeit mit
externen oder dateibezogenen Werkzeugen. Figma ist der erste praktisch
getestete Anwendungsbereich, aber nicht der Geltungsbereich der Prinzipien.

**Zentrale Prämisse:** Vor jedem Toolaufruf muss klar sein, welche fachliche
Frage beantwortet werden soll, welche Quelle dafür minimal erforderlich ist
und welchen Evidenzstatus das Ergebnis später haben kann.

Diese Prämisse verhindert, dass ein Toolaufruf eine fachliche Klärung ersetzt
oder aus einem einzelnen Testlauf eine allgemeine Produktgrenze abgeleitet
wird. Sie gilt sinngemäß auch für Repositories, Datenbanken,
Dokumentensammlungen, APIs und andere MCP- oder Plugin-Integrationen.

### Grundprinzipien

- **Quelle vor Tool:** Zuerst das kleinste belastbare Arbeitsobjekt bestimmen:
  Datei, Node, Dokument, Tabelle, Datensatz, Endpoint oder konkrete Auswahl.
- **Minimal ausreichender Kontext:** Nur den Kontext lesen, der die fachliche
  Frage beantwortet; breite Abrufe brauchen einen begründeten Nutzen.
- **Tool-Fit als begründeter Vorschlag:** Der Mensch benennt Ziel, fachliche
  Frage und bekannte Quellen. Die KI schlägt den Tool-Fit vor, begründet ihn
  und fordert fehlende Quellen oder Freigaben gezielt an.
- **Evidenzstatus vor Ableitung:** Toolausgaben werden als `sichtbar`,
  `abgeleitet`, `getestet`, `fehlgeschlagen`, `nicht getestet`,
  `nicht nachgewiesen` oder `blockiert` gekennzeichnet, bevor fachliche
  Schlussfolgerungen folgen.
- **Arbeitsobjekt statt Containerbegriff:** Nicht von „Datei“, „Repo“,
  „Datenbank“ oder „API“ sprechen, wenn die eigentliche Frage einen konkreten
  Node, Pfad, Datensatz, Endpoint, Abschnitt oder Commit betrifft.
- **Stoppen statt simulieren:** Wenn Quelle, Zugriff oder Funktion nicht zur
  bestätigten Frage passen, wird gestoppt und die Lücke benannt; ein
  Ersatzweg braucht eine sichtbare neue Auswahl.

### Kompakte Lesebrille für Toolwahl und Systemlernen

Diese Orientierung fasst bestehende Regeln zusammen; sie schafft keine
zusätzliche Governance-Schicht und ersetzt keine Detailquelle:

1. **Kleinster bestätigter Kontext zuerst.** Direkte, bekannte Arbeitsobjekte
   gehen vor breiterer Erschließung; Inventarisierung dient nur einer
   ausdrücklich beauftragten Übersicht oder fehlendem direktem Kontext.
2. **Bedeutung vor Ausprägung.** Rolle, Zweck und Verhalten gehen vor Werten,
   Stil oder Figma-Darstellung; die verbindliche Ausprägung steht in den
   [Design Principles](../foundations/design-principles.md).
3. **Direkte Evidenz vor Interpretation.** Sichtbare Toolausgabe und
   menschlich bestätigter Kontext werden vor abgeleiteten Aussagen
   ausgewiesen.
4. **Neue Struktur nur bei wiederkehrendem Nutzen.** Einzelfälle bleiben
   Projekt- oder Testkontext; erst ein belegtes, wiederkehrendes Muster wird
   Regelkandidat.
5. **Nach ausreichender Evidenz stoppen.** Kontext, Toolaufrufe und
   Dokumentation werden nur erweitert, solange eine bestätigte Frage oder
   notwendige Validierung offen ist.

Die Inventarisierungslogik ist eine Anwendung von Punkt 1, 3 und 5. Sie ist
keine Standardphase und keine Ersatzhandlung bei unklarem Auftrag.

### Generischer Ablauf

1. Fachliche Frage und gewünschte Entscheidung benennen.
2. Bekannte Quellen und fehlende Quellen trennen.
3. Kleinste belastbare Zugriffsebene bestimmen.
4. Passende Toolfunktion vorschlagen und tatsächlichen Scope ausweisen.
5. Ergebnis mit Evidenzstatus lesen und begrenzen.
6. Fachliche Ableitung, menschliche Entscheidung und technischen Nachweis
   getrennt halten.
7. Nur bei bestätigtem Nutzen weitere Quellen oder Schreibaktionen nutzen.
8. Wiederverwendbares Learning als Befund sichern; Regeln erst nach
   Freigabe setzen.

<a id="ki-gestutzte-figma-arbeit"></a>

## KI-gestützte Figma-Arbeit

**Status:** Entwurf; abgeleitet aus den Figma-/Button-Pilotbefunden,
insbesondere E-058, E-059 und dem Tooling-Test zur Adressierungslogik. Der
Button war Testsonde; dieser Ablauf ist die Figma-spezifische Ausprägung der
[Arbeitsprinzipien für evidenzbasierte Toolnutzung](#arbeitsprinzipien-fur-evidenzbasierte-toolnutzung).

**Zweck:** Figma-Tooling fachlich korrekt, lean, evidenzbewusst und
tokeneffizient einsetzen. Der Mensch soll fachliche Absicht und Entscheidung
tragen, nicht Toolsyntax, Node-IDs oder Funktionsgrenzen erraten müssen.

**Geltung:** Dieser Ablauf betrifft Figma-bezogene Analyse, Review, Pilot- und
Handoff-Arbeit. Er ersetzt keine Sicherheitsfreigabe, keine Code-Connect-
Einrichtung, keine Accessibility-Abnahme und keine menschliche
Gestaltungsentscheidung. Aussagen gelten nur für den tatsächlich geprüften
Scope.

### Arbeitsvertrag

| Ebene | Mensch | KI | Figma-/Tooling-Evidenz |
|---|---|---|---|
| Ziel | benennt Arbeitsabsicht, fachliche Frage und gewünschte Entscheidung | übersetzt das Anliegen in einen prüfbaren Scope | – |
| Quelle | liefert bekannte Datei-, Page-, Section-, Frame-, Component- oder Node-Bezüge, soweit vorhanden | prüft, ob die Quelle für die Frage ausreichend präzise ist, und fordert fehlende Quellen gezielt an | stellt adressierbare Artefakte bereit |
| Tool-Fit | trägt die fachliche Frage und bekannte Quellen bei | schlägt die kleinste passende Funktion vor, begründet sie und benennt Grenzen | liefert Kontext, Screenshot, Suche, Variablen oder Assets |
| Evidenz | bewertet Relevanz und entscheidet Freigaben | trennt `sichtbar`, `abgeleitet`, `getestet`, `fehlgeschlagen`, `nicht getestet`, `nicht nachgewiesen` und `blockiert` | zeigt nur den jeweils zugänglichen Stand |
| Fachlichkeit | entscheidet Zweck, Semantik, Priorität, Nutzung und Übernahme | bereitet Varianten, Lücken, Optionen und QS-Fragen vor | beweist keine Bedeutung, Nutzerwirkung oder Codequalität |
| Umsetzung | gibt Schreibumfang und Rückfallebene frei | schreibt nur klein, reversibel und validiert | speichert oder zeigt das Artefakt |
| Rückfluss | entscheidet `bewahren`, `Pilot/Kandidat`, `verwerfen` oder Regelsetzung | dokumentiert Delta, Evidenzstatus und nächsten Schritt | bleibt Quelle oder Testfixture |

### Pflichtablauf

1. **Arbeitsabsicht klären.** Vor dem Toolaufruf bestimmen, ob Struktur,
   visuelle Qualität, Komponentenverwendung, Handoff, Library-Nutzung,
   Tooling-Test oder Regelkandidat geprüft wird.
2. **Quelle und Scope getrennt adressieren.** Nicht von „Datei“ sprechen,
   wenn eigentlich Page, Section, Frame, Component, Instance oder Node
   gemeint ist. Ein Share-Link mit Node-ID liefert technische Anker, bestimmt
   aber nicht automatisch den Analyse-Scope. Bei unklarer Absicht wird
   Datei-, Page- oder Node-Scope gezielt geklärt. Ein File-Link reicht für
   filebezogene Funktionen; tiefe Designanalyse braucht eine belastbare
   Zielstruktur.
3. **Kleinste Zugriffsebene wählen.** Zuerst den kleinsten Node, die kleinste
   Section oder die kleinste Suche nutzen, die die Frage beantworten kann.
   Breite Abrufe brauchen einen konkreten Nutzen.
4. **Tool-Fit ausweisen.** Die KI schlägt die Funktion vor und begründet
   benötigte Quelle, erwartete Rückgabe, tatsächlichen Scope und nicht
   abgedeckte Aspekte. Bei unzureichender Quelle stoppt sie und fordert
   gezielt nach.
5. **Evidenz lesen.** Für Strukturfragen Design-Kontext oder Metadaten lesen;
   für visuelle Bewertungen ist ein Screenshot desselben Nodes die bevorzugte
   Evidenzquelle; für vorhandene Bausteine Libraries und Design-System-Suche
   nutzen; für Variablen nur den geprüften Node bewerten.
6. **Fachliche Ableitung begrenzen.** Aus Figma sichtbare Struktur, Layout,
   Texte, Zustände, Komponenten und Variablen werden von Zweck, Semantik,
   Nutzerwirkung, Accessibility, Codequalität und Regelübernahme getrennt.
7. **Optional schreiben.** Schreibende Figma-Aktionen erfolgen nur nach
   bestätigtem Modus, Zielseite, kleinem Scope, Rückfallebene und
   Reversibilitätsprüfung. Jeder Schreibschritt gibt betroffene Node-IDs
   zurück.
8. **Validieren und rückführen.** Nach visuellen oder strukturellen Änderungen
   folgt ein Screenshot- oder Strukturcheck. Systemlernen wird als Befund
   gesichert; eine Regel entsteht erst nach menschlicher Freigabe.

**Ergänzung für Dateiübersichten (Testbefund):** Wird ausdrücklich der
Dateiaufbau verlangt, kann ein read-only Root-Inventar die sichtbaren
Page-IDs liefern. Es ist nicht durch einen beliebigen Metadatenabruf zu
ersetzen, solange deren Abdeckungsgrad nicht im konkreten Setup verglichen
wurde. Die Funktion bleibt eine technische Evidenzquelle; sie beantwortet
weder die fachliche Frage noch legitimiert sie einen breiteren Scope als
bestätigt.

### KI-orientierte Inventarisierung

Eine Inventarisierung ist kein Workflow-Schritt. Sie ist eine
bedarfsorientierte Scope-Klärung, wenn der direkte Arbeitskontext die
bestätigte Frage nicht trägt oder wenn die Übersicht selbst beauftragt ist.
Ein bekannter Node oder Bereich mit konkreter Frage wird direkt gelesen;
unbekannte Datei, mehrere Pages, Review-, Handoff- oder
Wiederverwendungsanliegen lösen allein kein Inventar aus.

Erst bei einem belegten Inventar-Trigger führt die KI kein Vollverzeichnis auf
Verdacht, sondern trennt Struktur-, System- und Arbeitsinventar:

1. **Strukturinventar:** sichtbare Pages, Bereiche und technische IDs als
   adressierbare Arbeitsobjekte erfassen.
2. **Systeminventar:** Arbeitsobjekt-Typ, sichtbaren Library-/Tokenbezug,
   Vertragsrelevanz und Systemstatus als `nur sichtbar`, `möglicher Kandidat`,
   `menschlich bestätigt` oder `bewusst ausgeschlossen` ausweisen.
3. **Arbeitsinventar:** begründeten Dokumentations-, Review- oder
   Änderungsbedarf sowie genau eine nächste Aktion benennen.

Eine Page benötigt dafür einen belegbaren Arbeitszweck, keinen
Bausteinvertrag. Ein Bausteinvertrag bleibt einer wiederverwendbaren
Komponente vorbehalten. Die KI darf aus sichtbarer Struktur keine
Systemzugehörigkeit, Standardisierung oder fachliche Bedeutung ableiten;
diese bleiben Kandidat, offene Frage oder menschlich bestätigter Kontext.

Der Evidenztyp (`E0` bis `E4`) wird pro Inventarzeile ausgewiesen und als
Kontextart, nicht als Qualitätsrang gelesen. Bei fehlender Bedeutung,
Entscheidung oder Abnahme stoppt die KI vor Vertragsableitung oder
Änderung und fragt gezielt nach.

### Optionale Vertiefung

- Library- und Komponentenvergleich, wenn Wiederverwendung oder Neubau
  entschieden werden soll.
- Variablen-/Tokenprüfung, wenn ein konkreter Node oder eine konkrete
  Komponente Tokenbindung belegen soll.
- Asset-Export, wenn Bilder, Icons oder SVGs für Umsetzung oder Handoff
  relevant sind.
- Code Connect, wenn Plan, Seat, Codebasis und Komponentengrenze belegt sind.
- Southleft Design Systems MCP nur als allgemeine Beratungsquelle mit
  passenden, quellenzuordenbaren Treffern.
- Southleft Console nur bei verfügbarer und freigegebener Bridge für lokale
  Auswahl, Canvas-Audit oder Batch-Aktion.

### Stopppunkte

Abbrechen und gezielt nach Quelle, Freigabe oder Entscheidung fragen, wenn:

- nur ein File-Link vorliegt, aber eine tiefe Seiten-, Frame- oder
  Komponentenbewertung verlangt wird;
- ein Toolzugriff `fehlgeschlagen`, `blockiert` oder nur `nicht nachgewiesen`
  ist und keine gleichwertige belastbare Funktion verfügbar ist;
- eine Suchfunktion nur Kandidaten liefert, aber als bestätigte
  Komponentenverwendung behandelt werden soll;
- ein Screenshot als Semantik-, Accessibility- oder Codebeweis gelesen würde;
- eine schreibende Aktion ohne bestätigten Scope, Zielbereich oder
  Rückfallebene entstehen würde;
- aus einem einzelnen Testlauf eine allgemeine Produktgrenze abgeleitet
  werden müsste.

### Token- und Iterationsökonomie

- File-Kontext nur lesen, wenn filebezogene Fragen gestellt sind.
- Node-Kontext für Struktur und Handoff nutzen; Screenshot für visuelle
  Lesbarkeit und Validierung.
- Große Nodes nur lesen, wenn ihre Größe selbst Gegenstand der Prüfung ist;
  sonst auf Section, Frame oder Component eingrenzen.
- Zweite Nodes nur abrufen, wenn die erste Evidenz eine konkrete Lücke,
  Vergleichsfrage oder Entscheidung auslöst.
- Southleft oder externe Best-Practice-Abfragen nicht als Ersatz für konkrete
  Figma-Evidenz verwenden.
- Status- und Systemrückfluss erst sichern, wenn ein wiederverwendbares
  Learning oder eine Entscheidung entstanden ist.

## Neue Fundstücke bewerten und integrieren

**Status:** bestätigt durch [D-032](../governance/decisions.md#d-032--bewertung-und-integrationsgrad-neuer-fundstucke)
und [D-033](../governance/decisions.md#d-033--ubernahme-von-wissen-aus-externen-skills)

**Zweck:** Externe Tools, MCP-Server, Plugins, APIs, Open-Source-Projekte,
Methoden, Patterns oder Dokumentationsansätze nachvollziehbar bewerten. Ein
Fundstück darf auch dann geprüft werden, wenn es einen bestehenden Ansatz
scheinbar wiederholt: Es kann Kontext- oder Tokenaufwand verringern,
Unabhängigkeit von Plan, Paywall oder Plattform erhöhen oder ein übertragbares
Prinzip enthalten.

**Geltung:** Dieser Ablauf betrifft Systementwicklung. Bei Auswirkungen auf
Gestaltung oder Entwicklung werden deren Nutzen, Evidenz und Abnahme getrennt
ausgewiesen. Er ersetzt weder die KI-Tooling-Testkarte noch die Freigabe- und
Sicherheitsgrenzen aus der Tooling Map.

### Ablauf

1. **Fundstück und Anlass erfassen.** Quelle, behauptetes Problem,
   Wirkprinzip, betroffene Rolle und Anlass benennen. Produktversprechen,
   Primärquelle und tatsächlicher Testbefund getrennt halten.
2. **Bestand vergleichen.** Bestehendes Tooling, Regeln, Projektstand und
   Dokumentation gegen Funktion, Kontextmodell, Ausgabeform, Kosten,
   Abhängigkeiten und Rückfallebene abgrenzen. Funktionsähnlichkeit beendet
   die Prüfung nicht; sie verschiebt den Fokus auf Kontext-/Tokenökonomie,
   Unabhängigkeit und übertragbares Wissen. Je Bereich wird zusätzlich
   bewertet, ob das Fundstück den bestehenden Weg aktuell ergänzt, künftig
   ersetzen oder bei Plan-, Paywall-, Anbieter- oder Wartungsänderung als
   Rückfallebene absichern könnte.
3. **Mehrwert und Grenzen bewerten.** Zielbeitrag, evidenzierbaren Nutzen,
   Betriebs- und Pflegeaufwand, Datenfluss, Berechtigungen, Telemetrie,
   Lizenz-/Planstatus, Rückbaubarkeit und Nichtstun-Folge sichtbar bewerten.
   Für KI-gestützte externe Dienste gelten zusätzlich die Grenzen aus
   [Tooling Map](../tooling/tooling-map.md#verbindliche-einsatzgrenze-fur-ki-gestutzte-externe-dienste).
4. **Integrationsgrad bestimmen.** Nicht jedes Fundstück wird technisch
   getestet oder aufgenommen; die Entscheidung hält den kleinsten sinnvollen
   Rückfluss fest.
5. **Wissen selektiv zurückführen.** Wenn ein Fundstück einen nützlichen
   Ablauf zeigt, wird sein Prinzip vom Fremdartefakt getrennt dokumentiert:
   Ziel, Voraussetzungen, Lesescope, Schreibgrenze, Ergebnis und Prüfung
   danach. Datenabruf, regelbasierte Auswertung, KI-Vorschlag und menschliche
   Entscheidung bleiben unterscheidbar. Plugin-API-/OAuth- und
   REST-/persönlicher-Token-Wege sind getrennte Datenfluss- und
   Freigabepfade. Lint, Score oder Audit bleiben Vorprüfung; sie dürfen weder
   eine Qualitäts- noch eine Änderungsfreigabe erzeugen.
6. **Dokumentieren und zurückführen.** Der Befund verweist auf genau eine
   operative Zielquelle. Eine Wiki-Seite entsteht nur bei menschlichem
   Orientierungs-, Wiederverwendungs- oder Entscheidungswert; sie erklärt
   Wirkung und Entscheidung, ohne die operative Regel zu duplizieren.

### Vergleichsmatrix

Der Fundstückbefund wird nicht isoliert als Funktionsliste formuliert. Sein
zentrales Vergleichsartefakt ist je betroffener Fähigkeit:

| Bereich | Bestehender Ansatz | Fundstück | Einordnung | Mehrwert gegenüber diesem Bestand | Risiko gegenüber diesem Bestand |
|---|---|---|---|---|---|

- **Bestehender Ansatz** beschreibt vorhandene Fähigkeiten, maßgebliche
  Quellen und Grenzen; ein Toolname genügt nicht.
- **Fundstück** trennt nachweisbare Fähigkeit, Produktbehauptung und nicht
  geprüfte Wirkung.
- **Einordnung** benennt Überlappung, verbleibende Lücke und die Grenze der
  Aussage.
- **Mehrwert** und **Risiko** beziehen sich auf genau diese Zeile. Sie prüfen
  bei Bedarf Ersatz-, Ergänzungs- oder Rückfallebene, Plan-/Paywall- und
  Anbieterabhängigkeit, Open-Source-Wartbarkeit, Betrieb und Exit-Weg.

Der Integrationsgrad wird aus dieser Matrix abgeleitet. Kontext- und
Tokenökonomie ist keine pauschale Nebenbedingung, sondern gehört nur in die
Zeilen, deren bestehender Ansatz oder Fundstück tatsächlich Kontext oder
KI-Übergabe betrifft.

### Übernommenes Wissen aus externen Skills

Ein Fundstück kann ein **Arbeitsprinzip** liefern, ohne dass seine Skills,
Skripte, Rechte oder Aktivierungslogik übernommen werden. Ein solches Prinzip
ist nur ausreichend beschrieben, wenn es beantwortet:

- Was ist das Ziel und welches Ergebnis ist erwartbar?
- Welche Voraussetzungen und welcher kleinste Lesescope gelten?
- Kann es schreiben; wenn ja, wo liegt die bestätigte Schreibgrenze?
- Welcher Weg wird genutzt: Plugin-API/OAuth oder REST/persönlicher Token?
- Was wird regelbasiert abgeleitet, was ist gegebenenfalls KI-Vorschlag und
  was muss ein Mensch entscheiden?
- Wie wird das Ergebnis anschließend geprüft?

Bei umfangreichen Abfragen werden zusätzlich Tiefe, Umfang und Ausgabegrenze
festgelegt. Deterministische Exporte oder Dokumente sind als Ableitung der
sichtbaren Eingabedaten kenntlich zu machen. Lint-, Audit- und Scoreergebnisse
sind Hinweise zur Triage, nie ein Freigabeersatz.

### Status und Integrationsgrad

Jedes gesicherte Fundstück hat genau einen **Status**. Er beschreibt seinen
aktuellen Steuerungszustand und nicht seinen möglichen Lernwert:

| Status | Bedeutung |
|---|---|
| `beobachten` | Befund bleibt als potenziell relevanter Vergleichsfall sichtbar; keine operative Nutzung oder Freigabe. |
| `Pilot/Kandidat` | Ein begrenzter Test ist begründet, aber erst innerhalb der erforderlichen Freigaben zulässig. |
| `integriert` | Das Fundstück oder ein daraus abgeleiteter Baustein ist nach menschlicher Entscheidung im bestätigten Umfang übernommen. |
| `bewusst bewahren` | Der bestehende Ansatz bleibt die gewählte Lösung; das Fundstück erzeugt keine weitere Aktion. |
| `verwerfen/ablösen` | Das Fundstück ist ungeeignet oder durch einen anderen Ansatz ersetzt. |

Der **Integrationsgrad** kann dagegen mehrere parallele Rückflüsse zeigen,
zum Beispiel `Erkenntnis übernehmen` und `referenzieren`. Er erklärt nicht,
ob ein Tool im Einsatz, freigegeben oder im Pilot ist. Übersicht und
Detailbefund weisen deshalb beides getrennt aus.

### Integrationsgrade

| Grad | Bedeutung | Zulässiger Rückfluss |
|---|---|---|
| `0 – beobachten` | Bedarf oder Evidenz reicht noch nicht. | Kurzbefund im Evaluation Log oder zentrale Übersicht. |
| `1 – Erkenntnis übernehmen` | Ein Prinzip oder eine Prüffrage verbessert den Bestand. | Regelkandidat in genau einer zuständigen `docs/`-Quelle. |
| `2 – Arbeitsmuster übernehmen` | Prompt, Checkliste oder Ablauf ist wiederverwendbar. | Vorschlag für die zuständige Operations-/Governance-Quelle. |
| `3 – begrenzter Pilot` | Eine konkrete Fähigkeit muss technisch geprüft werden. | Isolierter, reversibler Test nach der KI-Tooling-Testkarte. |
| `4 – integrieren` | Nutzen, Betriebsfähigkeit und Freigaben sind belegt. | Menschlich freigegebene Tooling-, Regel- oder Bausteinänderung. |
| `5 – referenzieren` | Als Vergleichsfall verständlich oder später nützlich, aber nicht operativ nötig. | Wiki-Seite oder verlinkter Befund. |

Mehrere Grade können zugleich gelten. Ein Fundstück kann beispielsweise als
Referenz sichtbar bleiben und zugleich nur sein Kontextprinzip als
Regelkandidat in den Bestand einbringen.

### Fundstückkarte

```text
Fundstück und Fundstelle:
Art: Tool | Methode | Pattern | Artikel | Workflow | Referenz
Anlass und betroffene Rolle:
Behauptetes Problem und Wirkprinzip:
Bestehender Ansatz, Überlappung und verbleibende Lücke:
Mehrwert: Fachlichkeit | Kontext-/Tokenökonomie | Unabhängigkeit | Lernwert
Grenzen: Daten/Zugriff/Telemetrie | Lizenz/Plan | Betrieb/Pflege | Rückbau
Evidenz: Quelle | Testbefund | nicht sichtbar/nicht bewertet
Integrationsgrad und Begründung:
Status:
Rückfluss und Dokumentationsort:
Menschliche Entscheidung:
Genau ein nächster Schritt:
```

Ein Befund mit Integrationsgrad und Wiederprüfkriterium wird im Evaluation Log
gesichert und in dessen zentraler Übersicht der Fundstückbewertungen verlinkt.
Die Übersicht nennt Fundstück und Lizenz, Mehrwert, Risiko, entscheidende
Kriterien, aktuellen Integrationsrand und Wiederprüfauslöser; sie ersetzt nicht
die vollständige Vergleichsmatrix. Eine Wiki-Seite ist nur zusätzlich
erforderlich, wenn der Vergleichsfall eine menschliche Entscheidung, eine
wiederverwendbare Orientierung oder eine für Gestaltung relevante Toolgrenze
erklärt.

**Abbruch:** Die Prüfung endet als `bewusst bewahren`, `derzeit nicht
relevant` oder `verwerfen/ablösen`, wenn keine konkrete Lücke, keine
zusätzliche Evidenz oder kein vertretbarer Nutzen gegenüber Aufwand und Risiko
vorliegt. Ein fehlender Daten-, Zugriffs- oder Freigabenachweis autorisiert
keinen Ersatztest mit Projektinhalten.
