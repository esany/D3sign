# Testpilot – Gesamtübersicht und Standabgleich

## Transparenznachweis

| Feld | Angabe |
|---|---|
| Modus | Vorschlag / lesende Analyse |
| Nutzungsebene | Verbunden: fachliche Nutzung und Systementwicklung werden getrennt dargestellt |
| Rolle | Review, Governance und Design Ops |
| Gegenstand | Testpilot dieses Projekts: ein später möglicher, realer Komponenten- und Workflowfall |
| Quellen | Eingereichte Arbeitsübersicht; Base Template; Standards; Workflows; Tooling Map; Evaluation Framework und Log; Decisions; Projekt-Wiki; Rollenanforderungen |
| Automatisch ausgeführt | Quellenabgleich und diese Einordnung |
| Nicht verändert | Figma, Code, Tools, Decisions, kanonische Projektquellen und Projektartefakte |
| Externe Eingaben | Angaben zu `neocx`, Sebida, Timelog, Ticketexport und historischen Projektverläufen wurden nicht gegen ihre Primärquellen geprüft |
| Menschlich zu entscheiden | Ob, wann und mit welchem realen Projektfall ein Testpilot beauftragt wird |

## Kurzfassung

Der Testpilot ist ein **geplantes Erkenntnisvorhaben für dieses Projekt**. Er soll an einem realen, begrenzten Komponentenfall herausfinden, ob die bisherigen Regeln, Figma-/KI-Arbeitsweisen und Review-Prinzipien im Arbeitsalltag nützlich, kontrollierbar und verständlich sind. Er ist weder ein Auftrag zur sofortigen Figma-Änderung noch die Einführung eines neuen Tools oder einer vollständigen Library.

Der bislang entstandene Bestand ist für einen solchen Pilot gut vorbereitet: Er enthält einen generischen Komponentenvertrag, Evidenz- und Toolingregeln, Figma-Lesebefunde, begrenzte Schreibbefunde, Reviewlogik und dokumentierte Grenzen. Noch nicht nachgewiesen sind der Nutzen im realen Projekt, die gemeinsame Development-Rückkopplung, eine belastbare Aufwand-Nutzen-Aussage und die Einsatzfähigkeit konkreter externer Skills.

## 1. Was der Testpilot ist

Der Testpilot überführt keine fertige Methode in die Breite. Er prüft an einem einzelnen realen Fall, ob ein menschlich gesteuerter, agentisch unterstützter Ablauf belastbare Erkenntnisse erzeugt.

Der konkrete Gegenstand wäre eine vorhandene oder aktuell benötigte Projektkomponente. Das eigentliche Prüfinteresse liegt darüber hinaus im Arbeitsweg:

```text
fachliche Frage → abgegrenzter Kontext → sichtbare Evidenz →
menschliche Bewertung → begrenzte Handlung oder bewusster Stopp →
Review, Rückkopplung und Learning
```

Der Pilot prüft damit nicht nur eine Figma-Funktion. Er prüft die Zusammenarbeit von Gestaltung, Agent, Figma, gegebenenfalls Development und Projektsteuerung.

### Nicht Gegenstand

- kein Aufbau einer vollständigen Basisbibliothek;
- keine automatische Qualitäts-, Accessibility- oder Codefreigabe;
- keine produktive Design-to-Code-Pipeline oder Token-Synchronisation;
- keine pauschale Einführung eines neuen Tools, Plugins oder Skills;
- keine Übernahme eines einzelnen Projektfalls als projektübergreifender Standard;
- keine Durchführung ohne gesonderten, konkret freigegebenen Auftrag.

## 2. Wofür der Testfall gebraucht wird

Das Projekt hat bereits Regeln und isolierte Toolingbefunde entwickelt. Diese beantworten vor allem Fragen zu Sichtbarkeit, Funktionsscope und sicheren Grenzen. Ein realer Testfall wird erst dann nötig, wenn entschieden werden soll, ob daraus ein praxistauglicher Arbeitsweg entstehen kann.

Er kann insbesondere klären:

| Erkenntnisinteresse | Zu prüfende Frage |
|---|---|
| Direkter Nutzen | Macht der Ablauf einen konkreten Arbeitsschritt klarer, schneller oder nachvollziehbarer? |
| Qualität | Werden fehlende Anforderungen, Zustände, Inkonsistenzen oder Übergaberisiken früher sichtbar? |
| Arbeitsteilung | Was bereitet der Agent vor, was entscheidet Gestaltung, was prüft Development? |
| Kompetenz | Welches Kontext- und Toolverständnis benötigen Gestalter:innen tatsächlich? |
| Wiederverwendung | Was bleibt ein Einzelfall, was wird ein belastbarer Befund und was könnte später Regelkandidat werden? |

Diese Fragen sind **Wirkungshypothesen**, keine bereits gemessenen Ergebnisse.

## 3. Übergeordnete Zielstellung

> Prüfen, ob ein klar begrenzter, menschlich geführter und agentisch unterstützter Komponentenworkflow Anforderungen, Gestaltung und spätere Development-Übergabe mit vertretbarem Aufwand nachvollziehbarer vorbereiten kann.

Die Zielstellung bleibt zweigeteilt:

- **Fachliche Nutzung:** Ist der Ablauf für eine konkrete Gestaltungs- und Übergabeaufgabe brauchbar?
- **Systementwicklung:** Welche Regeln, Quellen, Toolgrenzen oder Dokumentationsformen tragen praktisch und welche bleiben Hypothese oder Regelkandidat?

Ein positiver Einzelbefund bestätigt keine allgemeine Methode. Der zulässige Rückfluss bleibt: Test → Befund → menschliche Bewertung → Evaluation → gegebenenfalls Übernahme.

## 4. Rahmenbedingungen

### Fachlich und organisatorisch

- Das Base Template ist v0.1, ein generischer und testbereiter Regelrahmen, keine produktive Library oder Projektspezifikation.
- Rollen für Gestaltung, Development, Review und Governance sind beschrieben; ihre praktische Zusammenarbeit ist noch nicht an einem realen Fall validiert.
- Ein realer Pilot muss klein bleiben, weil Nutzen, Aufwand, Pflege und Beteiligung noch keine gemessenen Erfahrungswerte haben.
- Eine Figma-Komponente benötigt einen geklärten Zweck, Nutzungskontext, Grenzen, Varianten/Zustände, Verhalten, Accessibility, Abhängigkeiten, Quellen und Status. Nicht bekannte Felder werden als offen ausgewiesen.

### Tooling und Sicherheit

- Figma-Kontext kann, im tatsächlich zugänglichen Scope, Strukturen, Komponenten, Varianten, Properties, Variablenbezüge und Screenshots liefern.
- Diese Sichtbarkeit beweist keine fachliche Semantik, Nutzerwirkung, Accessibility-Abnahme, Laufzeitinteraktion oder Code-Parität.
- Schreiben ist nur in einem bestätigten, kleinen, reversiblen und validierten Scope zulässig.
- Externe KI-Dienste benötigen pro Tool, Integrationsweg, Datenklasse und Zielbereich eine konkrete Freigabe. Eine vorhandene Verbindung oder Installation ist kein Funktions- oder Freigabenachweis.
- Figmalint und Figma Console sind im Bestand Beobachtungs-/Bewertungsfälle, keine praktisch freigegebenen Pilotwerkzeuge.

### Projekt- und externe Eingaben

Die eingereichte Übersicht nennt Team-Auslastung, `neocx`, Timelog, Tickets und Sebida-Use-Cases. Diese Informationen sind für die Pilotplanung plausibel relevant, aber in diesem Repository nicht als Primärevidenz geprüft. Vor einer Durchführung müssen sie als konkrete Voraussetzungen bestätigt werden.

## 5. Offene Punkte vor einer Beauftragung

| Bereich | Offene Entscheidung oder Nachweis |
|---|---|
| Testfall | Welches aktuelle Problem, welche Komponente, welcher Projekt- und Figma-Scope? |
| Fachlichkeit | Zweck, Nutzerhandlung, bekannte Anforderungen, Varianten, Zustände, Verhalten und bewusst offene Fragen? |
| Technik | Gibt es einen relevanten Codekontext; wer prüft Machbarkeit, Laufzeit und technische Semantik? |
| Freigabe | Sind Figma-Zugriff, Schreibumfang, Datenklasse, Datenfluss, Lizenz-/Planstatus und externe Dienste für genau diesen Fall zulässig? |
| Rollen | Wer entscheidet fachlich, wer prüft Design, wer gibt technische Rückmeldung und wer bewertet den Befund? |
| Messung | Was ist der heutige Vergleichsprozess; wie werden Aufwand, Rückfragen, Nacharbeit und Nutzen erfasst? |
| Abbruch | Wann endet der Pilot ohne weitere Iteration? |

## 6. Bereits analysierte Ebenen und Grundlagen

| Ebene | Vorliegender Stand | Noch nicht nachgewiesen |
|---|---|---|
| Governance | Quellenhierarchie, Entscheidungsrechte, Statuslogik, Test-/Übernahmerückfluss | Praktische Tragfähigkeit aller Regeln im Projektfall |
| Komponentenmodell | Bausteinvertrag, Varianten- und Zustandslogik, Trennung von stabiler Invariante und Projektkontext | Vollständig bestätigter Vertrag einer realen Projektkomponente |
| Tokens | Primitive, semantische und komponentenspezifische Ebenen sind unterschieden | Projektwerte, vollständige Tokenarchitektur oder Synchronisation |
| Figma-Lesen | Read-only-Befunde zu Komponenten, Varianten, Zuständen, Variablen und Adressierung | Vollständige Datei-/Library-Abdeckung und fachliche Bedeutung |
| Figma-Schreiben | Begrenzte, schrittweise Piloterfahrung und Validierungsprinzip | Stabiler realer Schreibablauf im Projektfile |
| Dokumentation | D-035 beschreibt vertrauensfähige, menschenlesbare Komponentendokumentation | Wirksamkeit mit realen Nutzer:innen und Development |
| Handoff | Rollen- und Evidenzgrenzen sind beschrieben | Tatsächliche gemeinsame technische Abnahme |
| Externe Tools/Skills | Nutzen, Risiken und Integrationsstufen von Fundstücken sind bewertet | Einsatzfähigkeit und Mehrwert eines konkreten externen Skills |
| Evaluation | Evidenz vor Ableitung, Lean-Prüfung und menschliche Verständlichkeit sind operationalisiert | Nutzen-/Aufwandsvergleich im realen Projektalltag |

## 7. Best Practices und Arbeitsprinzipien

Die folgenden Grundlagen sind nicht alle gleich stark bestätigt. Sie bilden den aktuellen Arbeitsrahmen:

1. **Bedeutung vor Ausprägung.** Zweck, Rolle, Nutzung und Verhalten gehen vor Stil, Figma-Struktur oder Wertewahl.
2. **Quelle vor Tool.** Zuerst das kleinste belastbare Arbeitsobjekt und die fachliche Frage bestimmen, dann die passende Funktion wählen.
3. **Evidenz vor Ableitung.** Sichtbar, abgeleitet, getestet, fehlgeschlagen, nicht getestet, nicht nachgewiesen und blockiert werden getrennt ausgewiesen.
4. **Kleinster ausreichender Kontext.** Ein Node oder Bereich mit klarer Frage wird nicht vorsorglich durch einen Vollinventar-Abruf ersetzt.
5. **Test ist kein Standard.** Ein Artefakt oder ein Tooltreffer wird nur über Evaluation und menschliche Entscheidung zur Regel.
6. **Komponentenauftrag trennen.** Erstellen, prüfen und dokumentieren sind unterschiedliche Auftragsarten (D-036).
7. **Dokumentation dient Menschen.** Sie muss Zweck, Status, Geltung, Quellen und offene Punkte verständlich machen; formale Objektvollständigkeit reicht nicht (D-035).
8. **Kleine reversible Schritte.** Lesen, offene Ebenen klären, begrenzt schreiben, direkt visuell/strukturell prüfen und Ergebnis sichern.
9. **Stoppen statt simulieren.** Bei unpassender Quelle, Funktion oder Freigabe wird die Lücke benannt; ein Ersatzweg wird nicht stillschweigend gewählt.

## 8. Identifizierte Herausforderungen

### Fachlich

- Sichtbare Namen wie `selected` oder `active` erklären nicht, welche Rolle, Nutzung oder Kombination fachlich zulässig ist.
- Implizite Anforderungen können von Tools nicht verlässlich ergänzt werden; ein plausibles Artefakt kann diese Lücke verdecken.
- Projektspezifische Anforderungen dürfen nicht automatisch als generische Basisregel übernommen werden.

### Technisch

- Figma-Lesefunktionen besitzen unterschiedliche Abdeckungsgrade; ein Link ist Anker, aber keine fachliche Scopefestlegung.
- Große Schreibaufträge erhöhen das Risiko von Zielverschiebung und unklarer Validierung.
- Dateiübernahmen müssen zwischen lokaler Kopie, verknüpfter Instanz, Verschieben und Rekonstruktion unterscheiden.
- Accessibility, Laufzeitverhalten und Code-Parität brauchen passende Produkt- und/oder Code-Evidenz.

### Organisatorisch

- Rollen, Zeitpunkt und Umfang einer Development-Rückkopplung sind für einen konkreten Fall zu klären.
- Ressourcen, Pflegeverantwortung und Kompetenzaufbau müssen zum kleinen Pilotumfang passen.
- Wirtschaftlicher Nutzen kann nicht ohne Vergleichsprozess und Erfassung bewertet werden.

## 9. Gewählte Methodik für einen möglichen Testfall

Die Methodik ist ergebnisoffen und proportional:

1. **Prüffrage bestimmen:** nicht „Kann KI Komponenten?“, sondern eine konkrete Frage zu einer Komponente und Entscheidung.
2. **Eingang begrenzen:** eine Komponente oder klar abgegrenzte Gruppe, Projektkontext, bekannte Anforderungen, Figma-Bereich und nur bei Bedarf Codekontext.
3. **Rollen sichtbar machen:** Gestaltung trägt Zweck und fachliche Abnahme; Agent strukturiert Kontext und Befund; Figma liefert Scope-gebundene Evidenz; Development prüft technische Fragen; Review prüft Quellen, Grenzen und Abnahme.
4. **Evidenzstatus ausweisen:** Tooloutput und fachliche Deutung werden getrennt.
5. **Reversible Schritte wählen:** erst lesen, dann fehlende Entscheidungen klären, nur mit Freigabe begrenzt ändern und direkt validieren.
6. **Auswertung trennen:** erst nach Durchführung bewerten, was funktioniert hat, was manuell blieb, welchen Aufwand es gab und was wiederverwendbar wäre.

Die Methodik ist keine automatische Abfolge. Eine Durchführung braucht vorher einen eigenständigen Auftrag mit Ziel, Gegenstand, Modus, Rolle, Aktion, Grenzen, Ergebnis und Abnahme.

## 10. Bisherige Befunde und Learnings

| Befund | Aussage | Einordnung |
|---|---|---|
| Read-only Figma-Tests | Komponenten, Varianten, Properties, Zustände und Variablen können als begrenzte Evidenz sichtbar werden. | Belegt im jeweiligen Scope; keine Semantik-, Accessibility- oder Codeaussage. |
| Button-/Teaserbefunde | Sichtbare Struktur beantwortet nicht Interaktionsrolle, Inhaltsgrenzen, unterstützte Kombinationen, Fokus oder Code-Parität. | Grundlage für Komponentenvertrag und offene Fragen. |
| Schreibbefunde V2–V4 | Kleine, schrittweise Schritte sind belastbarer als große Schreibaufträge; Dokumentation kann den Komponentenauftrag verdrängen. | Führte zu D-036. |
| V5/E-069 | Ein echtes lokales Component Set war möglich, aber der reine Komponentenbau-Test scheiterte am vermischten Dokumentationsscope. | Prüfgate ist Regelkandidat, nicht Standard. |
| E-070 | V5 bleibt Befundträger, aber keine bestandene Library-Komponente und kein finales Dokumentationstemplate. | Dokumentierter Standabgleich. |
| Dateiübernahme | „Kopieren“ ist ohne Übernahmeart unpräzise; lokale Main-Component-Kopie war im geprüften Scope nicht als native Transferfunktion belegt. | D-026 und weiterer Klärungsbedarf. |
| Externe Wissens-/Tooldienste | Erreichbarkeit, Installation oder Produktversprechen reichen nicht als fachliche Evidenz. | D-028, D-031 bis D-033. |

## 11. Konkrete Decisions und ihre Bedeutung

| Decision | Status | Bedeutung für den Testpilot |
|---|---|---|
| D-026 – Übernahmeart und Toolrouting | bestätigt | Bei Datei-/Komponentenübernahmen zuerst Erhaltungsziel und Funktionsklasse klären. |
| D-028 – Externe Wissens-MCPs | bestätigt | Externe Treffer zählen nur als Evidenz, wenn sie fachlich passen und Quellen zuordenbar sind. |
| D-029 – Entwicklungspriorisierung | bestätigt | Pilotnutzen, Aufwand und Nichtstun-Folge vor weiterer Iteration sichtbar machen. |
| D-031 – Externe KI-Dienste | bestätigt | Je Dienst und Einzelfall gelten Freigabe-, Daten-, Lizenz- und ISMS-Grenzen. |
| D-032/D-033 – Fundstücke und Wissen | bestätigt | Erkenntnisse können selektiv übernommen werden; Tool-/Skill-Installation folgt daraus nicht. |
| D-034 – Erweiterungsfähigkeit von Komponentenverträgen | bestätigt | Projektfall und generische Regel werden nicht vermischt. |
| D-035 – Vertrauensfähige Dokumentation | bestätigt | Eine spätere Dokumentation wird an Nutzbarkeit, nicht an Objektmenge gemessen. |
| D-036 – Auftragsarten trennen | bestätigt | Komponentenbau, Prüfung und Dokumentation werden vor Ausführung getrennt oder sequenziell beschrieben. |

Weitere zentrale Grundlagen, darunter Transparenznachweis, Evidenzreihenfolge, Rollen- und Regelkandidatenlogik, sind teils als Entwurf oder Regelkandidat geführt. Sie dürfen deshalb nicht als endgültiger Standard ausgegeben werden.

## 12. Standabgleich zur eingereichten Arbeitsübersicht

Die Arbeitsübersicht trifft die Projektidee und den Nutzen eines realen Testfalls überwiegend richtig. Besonders passend sind die Abgrenzung gegen einen vorgezogenen Rollout, die Betonung menschlicher Entscheidung, die Trennung von Toolfähigkeit und Projektwert sowie die offenen Fragen zu Handoff und Wirtschaftlichkeit.

Zu korrigieren oder klarer zu kennzeichnen sind:

- Der Testpilot ist Planung, bis ein konkreter Fall ausdrücklich beauftragt wird.
- Der Bestand enthält keine bestätigte produktive Basislibrary, keine validierte Design-to-Code-Pipeline und keinen bereits bewiesenen Workflow-Nutzen.
- Die aktuelle Komponentenarbeit liefert relevante Befunde, ist aber nicht mit dem Gesamtpilot gleichzusetzen.
- Das Prüfgate und die Aufbaustufe-/Generationsunterscheidung sind Regelkandidaten.
- Externe Angaben sind Voraussetzungen oder Hypothesen, solange ihre Primärquelle nicht geprüft ist.

## Präsentationsfassung

> Der Testpilot ist ein geplantes Projektvorhaben, mit dem wir an einem realen, klar begrenzten Komponentenfall prüfen wollen, ob unser bisher entwickelter Regel-, Evidenz- und Toolingansatz im Arbeitsalltag trägt. Wir führen damit weder eine vollständige Library noch eine automatische KI-Freigabe ein. Wir wollen sichtbar machen, welche Informationen Figma und KI belastbar liefern, welche Entscheidungen bei Gestaltung und Development bleiben, wo Aufwand entsteht und ob ein wiederverwendbarer Nutzen nachweisbar ist. Die Grundlagen dafür sind weitgehend vorbereitet; offen sind der konkrete Projektfall, Freigaben, Beteiligte und der praktische Nutzen.

## Nächster Planungsschritt

Menschlich entscheiden, ob ein konkreter Pilotfall ausgewählt und als eigenständiger, begrenzter Auftrag freigegeben werden soll.
