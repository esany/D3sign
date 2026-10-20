# Checklists

Status: Entwurf

Scope: operative Prüfungen für Prozess, Governance, Tooling und Transparenz.
Nicht enthalten: fachliche Design-QA, visuelle Entwurfsbewertung oder
allgemeine Vermittlungstexte.

## Mensch–Maschine-Entscheidung vor einer Änderung

**Zweck:** Sicherstellen, dass ein Agent nur im freigegebenen Umfang handelt
und menschliche Entscheidungsrechte sichtbar bleiben.

**Anwendungszeitpunkt:** Vor jeder schreibenden oder standardverändernden
Aktion.

- [ ] Aktion, Zielbereich und betroffene Quellen sind eindeutig.
- [ ] Bei Datei-, System- oder Librarygrenzen sind Übernahmeart,
      Erhaltungsziel und Funktionsklasse ausdrücklich geklärt.
- [ ] Der Scope der konkreten Funktion ist vor dem Schreiben gegen die
      bestätigte Aktion geprüft; ein abweichender Ersatzweg liegt nicht vor.
- [ ] Quellenklarheit, Neuheit, Reichweite und Reversibilität sind eingeordnet.
- [ ] Die Aktion fällt entweder unter eine bestätigte Regel oder ist als
      Eskalationsfall erkannt.
- [ ] Bei Eskalation enthält der Befund Situation, Optionen, Auswirkungen,
      Empfehlung und die konkret benötigte Freigabe.
- [ ] Eine erforderliche Freigabe liegt vor, bevor geändert wird.
- [ ] Folgenreiche Entscheidung oder Ausnahme ist im Entscheidungslog erfasst.

**Ergebnis:** `ausführen`, `zur Freigabe vorlegen` oder `nicht ausführen`.

## Pflege- und Statusabgleich von Regeln

**Zweck:** Verhindern, dass ein Entwurf faktisch als verbindliche Regel
verwendet wird oder dass eine Statusänderung nur in einer Datei ankommt.

**Anwendungszeitpunkt:** Bei neuen oder verschobenen Regeln, Änderungen an
`AGENTS.md`, Änderungen an Quick Controls sowie vor `REGEL SETZEN`.

- [ ] Regelkandidat, Entwurfsentscheidung oder bestätigte Regel ist eindeutig
      benannt.
- [ ] Die zentrale Kandidatenübersicht in
      [Decisions](../governance/decisions.md#regelkandidaten-und-statusabgleich)
      ist geprüft und enthält Status, Fundstellen und nächste Klärung.
- [ ] Jede praktische Referenz auf eine Entwurfsentscheidung ist als
      unverbindlich, Pilot oder Regelkandidat gekennzeichnet.
- [ ] Es gibt genau eine vorgesehene verbindliche Detailquelle.
- [ ] Vor Kürzung oder Verschiebung ist die Quellen-/Funktionszuordnung
      aktualisiert; keine Funktion oder Schutzwirkung fehlt.
- [ ] Bei `REGEL SETZEN` werden Decision Log, verbindliche Quelle,
      Evaluation-Nachweis und betroffene Wiki-Einordnung gemeinsam geprüft.
- [ ] Status, Kurzliste und Detailabschnitt stimmen überein.
- [ ] Kein neuer Pflegeprozess und keine doppelte Checkliste wurde eingeführt.

**Ergebnis:** `statusklar`, `als Regelkandidat offen` oder `zur Entscheidung
vorlegen`.

## Register- und Detailquellen fortschreiben

**Zweck:** Verhindern, dass Quellen mit Übersicht, Statusliste und
Detailabschnitten strukturell auseinanderlaufen.

**Anwendungszeitpunkt:** Bei `Status sichern`, neuen oder fortgeschriebenen
Evaluationen, neuen oder fortgeschriebenen Decisions sowie bei struktureller
Logpflege.

- [ ] Die nächste oder betroffene ID ist eindeutig bestimmt.
- [ ] Der Übersichtseintrag ist vorhanden oder eine Ausnahme ist begründet.
- [ ] Der Detailabschnitt ist vorhanden oder eine Ausnahme ist begründet.
- [ ] Status, Kurzbeschreibung, Ergebnis und nächste Aktion stimmen zwischen
      Register und Detail überein.
- [ ] Die Reihenfolge ist konsistent oder eine Ausnahme ist dokumentiert.
- [ ] Interne Links und Abschnittsanker sind geprüft.
- [ ] Zusatztabellen wie Regelkandidaten- oder Fundstückübersichten sind mit
      dem Detailbefund synchron.
- [ ] Es wurde keine neue Regel, Decision oder fachliche Wahrheit ohne
      Freigabe gesetzt.

**Ergebnis:** `konsistent`, `nacharbeiten` oder `zur Entscheidung vorlegen`.

## Späterer Projektkit-Vertikalschnitt

**Zweck:** Prüfen, ob ein späteres Projektkit eine konkrete Benutzerhandlung
einordnen und in einen wiederverwendbaren Bausteinvertrag überführen kann,
ohne Projektwerte oder technische Lösungen vorwegzunehmen.

**Anwendungszeitpunkt:** Erst nach Aktivierung der Projektkit-Ebene und dem
Ausfüllen des minimalen Piloten im
[Project Template](../../templates/project-template.md#späterer-minimaler-projektkit-pilot).

- [ ] Nutzungskontext, Nutzerziel, Wirkung, Plattform, Quellen und Grenzen sind
      angegeben oder ausdrücklich als offen markiert.
- [ ] Die Handlung ist begründet als Aktion oder Navigation eingeordnet.
- [ ] Ihre Priorität ist nur relativ zu den umgebenden Handlungen beschrieben.
- [ ] Der Bausteinvertrag enthält Zweck, Verwendung, Grenzen, erforderliche
      Zustände, Verhalten, Accessibility, Abhängigkeiten, Quelle und Status.
- [ ] Generische Bedeutung und projektspezifische Ausprägung sind getrennt.
- [ ] Es wurde höchstens ein neuer Baustein vorgeschlagen.
- [ ] Offene Fragen, Abweichungen und erforderliche Freigaben sind sichtbar.

**Ergebnis:**

- `bestanden`: Der Vertrag ist ohne verdeckte Annahmen anwendbar.
- `überarbeiten`: Kontext oder Vertrag reichen für eine sichere Ableitung nicht
  aus.
- `verwerfen`: Der Vertikalschnitt erzeugt keinen wiederverwendbaren Nutzen.

## Prüfung eines generischen Library-Grundbausteins

**Zweck:** Prüfen, ob eine neue oder geänderte Regel ohne Projekt-, Marken-
oder Technikannahme für eine Design-System-Library anwendbar ist.

**Anwendungszeitpunkt:** Vor der Übernahme einer Regel in Design Principles,
Semantic Model oder Standards.

- [ ] Die Regel benennt eine wiederkehrende Bedeutung, Entscheidung oder
      Qualität – keinen projektspezifischen Wert.
- [ ] Es ist klar, ob die Regel Principles, Semantik, Token, Komponente,
      Variante, Zustand, Accessibility oder Governance betrifft.
- [ ] Die Regel beschreibt Auslöser, zulässige Aktion und prüfbares Ergebnis.
- [ ] Die Regel schreibt keine Atomic-Design-Taxonomie, Figma-Dateistruktur
      oder technische Architektur ohne belegten Bedarf vor.
- [ ] Grenzen, offene Fragen und spätere Projektausprägungen sind sichtbar.
- [ ] Die Beziehung zu bestehenden Regeln ist geklärt; Doppelung und
      Widerspruch sind ausgeschlossen.
- [ ] Bei Komponentenregeln ist sichtbar, welche Teile stabile Invariante,
      aktuelle Ausprägung, Kontextentscheidung, additive Erweiterung,
      restriktive Änderung oder semantische Korrektur wären.

**Ergebnis:** `als Entwurf aufnehmen`, `überarbeiten` oder `nicht aufnehmen`.

## Qualitätsprüfung für Figma-Komponentendokumentation

**Zweck:** Prüfen, ob eine Figma-Fläche für Komponenten nicht nur formal
angelegt, sondern als vertrauensfähige Dokumentation nutzbar ist.

**Anwendungszeitpunkt:** Vor Abschluss eines Figma-Piloten oder einer
Figma-Komponentendokumentation.

- [ ] Die Auftragsart ist getrennt ausgewiesen: Komponente `erstellen`,
      bestehende Komponente `prüfen`, Komponente `dokumentieren` oder
      kombinierter Auftrag mit festgelegter Reihenfolge.
- [ ] Bei einem Komponentenpilot ist der Mindestgegenstand erfüllt: echte
      Figma-Komponente, Component Set oder ausdrücklich benannter bestehender
      Komponenten-Gegenstand. Andernfalls wird der Auftrag als
      Dokumentationspilot behandelt.
- [ ] Aufbaustufe und Generation sind getrennt benannt: fachlicher Umfang des
      Tests einerseits, konkrete Figma-Version oder Versuchsgeneration
      andererseits.
- [ ] Die sichtbare Library-Dokumentation ist auf Deutsch, sofern kein anderer
      Sprachscope bestätigt wurde.
- [ ] Die Fläche unterstützt eine konkrete Komponentenprüfung oder
      Entscheidung; sie ist keine bloße Ablage von Prompttext.
- [ ] Menschen können Zweck, Status, Geltung, Beispiele, offene Punkte und
      Quellen ohne Chat-Kontext visuell erfassen.
- [ ] Die Informationshierarchie führt von Überblick über Aufbau zu
      entscheidungsrelevanten Details.
- [ ] Text, Tabellen und Beispiele sind im Screenshot vollständig lesbar und
      nicht verdeckt, abgeschnitten oder layoutbedingt missverständlich.
- [ ] KI-Lesbarkeit entsteht durch sichtbare Labels, Frame-Namen und klare
      Gliederung; sie dominiert die menschliche Dokumentationsform nicht.
- [ ] Pilot-, Governance-, Token-, Code- oder Tooling-Hinweise bleiben nur dann
      sichtbar, wenn sie zum bestätigten Scope gehören, und sind sekundär.
- [ ] Regel, Beispiel, offene Information, Quelle und Pilotkontext sind
      unterscheidbar, ohne als dekorative oder störende Marker zu wirken.
- [ ] Leere Gerüste, Scheintabellen, Platzhalter ohne Funktion und reine
      Formularschemata werden als `nicht erfüllt` gewertet.

**Ergebnis:** `abnahmefähig`, `nacharbeiten` oder `verwerfen`.

## Prüfgate für reinen Figma-Komponentenbau

**Status:** Regelkandidat; abgeleitet aus E-069 und D-036. Dieses Gate gilt
für den nächsten reinen Komponentenbau-Test, insbesondere Button/Figma, und
ist noch kein universeller Komponentenstandard.

**Zweck:** Prüfen, ob ein Auftrag wirklich eine Komponente bzw. ein Component
Set erstellt oder prüft, statt in Dokumentation, Taxonomie- oder
Governance-Flächen zu kippen.

**Anwendungszeitpunkt:** Vor und nach einem Figma-Auftrag mit Auftragsart
`Komponente erstellen` oder `Komponente prüfen`. Bei reiner
Komponentenerstellung wird keine Dokumentationsfläche erzeugt.

- [ ] **Auftragstyp-Test:** Der Auftrag ist ausschließlich
      `Komponente erstellen` oder `Komponente prüfen`. Dokumentation,
      Taxonomie, Tokenmodell und Code-Anbindung sind nicht Teil des Scopes,
      sofern sie nicht ausdrücklich beauftragt wurden.
- [ ] **Komponenten-Gegenstand-Test:** Es existiert eine echte Figma-
      Komponente, ein Component Set oder ein ausdrücklich benannter bestehender
      Komponenten-Gegenstand.
- [ ] **Anatomy-Test:** Die strukturellen Teile sind konsistent vorhanden und
      benannt, für den Button mindestens `container`, `label` und optional
      `icon-leading`.
- [ ] **Variant-Test:** Alle Varianten sind eindeutige Kombinationen derselben
      Achsen. Variantenachsen vermischen nicht Zustand, Inhalt, Größe,
      Position oder fachlichen Scope.
- [ ] **Property-Test:** Die beabsichtigten Controls sind tatsächlich als
      Figma Properties nutzbar oder eindeutig als noch nicht eingerichtet
      markiert. Der Test darf nicht aus Variantennamen allein auf eine nutzbare
      Component-API schließen.
- [ ] **Override-Test:** Instanzrelevante Inhalte bleiben über Varianten hinweg
      strukturell stabil, insbesondere der Button-`label`.
- [ ] **Scope-Test:** Es entstehen keine nicht beauftragten
      Dokumentationsframes, keine heimliche Button-Taxonomie, keine Token-
      Entscheidung und keine Code- oder Accessibility-Freigabe.
- [ ] **Sichttest:** Die erzeugten Varianten sind sichtbar, unterscheidbar und
      als Komponentenprüfgegenstand inspizierbar. Dieser Sichttest bewertet
      nicht die spätere Dokumentationsqualität nach D-035.

**Ergebnis:** `Komponentenbau bestanden`, `nacharbeiten`,
`nicht bestanden` oder `als Dokumentations-/Governance-Auftrag umklassifizieren`.

## Kompakte KI-Tooling-Testkarte

**Zweck:** Eine einzelne KI- oder Tooling-Fähigkeit ergebnisoffen prüfen, ohne
das Base Template oder andere kanonische Quellen zu verändern.

**Vorbedingungen:**

- [ ] Modus ist ausdrücklich `Test`, nicht `Systementwicklung`.
- [ ] Genau eine Prüffrage, ein begrenzter Eingangskontext und ein Artefakt sind
      festgelegt.
- [ ] Die Testquelle ist als externe Testfixture oder kanonische Quelle
      gekennzeichnet; Testmaterial wird nicht als Standardquelle behandelt.
- [ ] Gewähltes Tool, erwartetes Ergebnis und menschliche Prüfinstanz sind
      benannt.
- [ ] Bei scheinbar gleichartigen Lesefunktionen ist ihr Abdeckungsgrad für
      die konkrete Prüffrage getrennt getestet oder als `nicht nachgewiesen`
      ausgewiesen; Funktionsname oder Produktbeschreibung gelten nicht als
      Gleichwertigkeitsnachweis.
- [ ] Bei einem externen Dienst sind Integrationsweg, berechtigter Zielbereich
      und ISB-/ISMS-Status als `freigegeben`, `mit Auflagen`, `offen` oder
      `nicht bewertet` festgehalten. Ohne Freigabe werden nur synthetische
      oder ausdrücklich freigegebene Daten verwendet.
- [ ] Lizenz-/Nutzungsreferenz, Konto-/Planstatus und relevante Token-,
      Credit-, Zeit- oder Funktionslimits sind als belegter Status oder offen
      ausgewiesen; sie werden nicht aus einer installierten Verbindung
      abgeleitet.
- [ ] Datenfluss, Anbieter-KI, Export, Import und Screenshot sind für den
      konkreten Test als zulässig, ausgeschlossen oder offen markiert.
- [ ] Pilotbereich, Token-/Zeit-/Iterationsgrenze und Abbruchkriterium sind
      festgelegt.
- [ ] Der Test enthält keine Produktionsgeheimnisse und verändert keine
      kanonische Quelle.

**Testkarte:**

```text
Aufgabe:
Eingang:
Testquelle/Testfixture:
Tool:
Erwartetes Ergebnis:
Tatsächliches Ergebnis:
Menschliche Bewertung:
Konsequenz: übernehmen | überarbeiten | verwerfen | weiter testen
```

**Nachweis:** Das Ergebnis wird als Kurzbefund im Evaluation Log erfasst. Eine
Übernahme in das Zielsystem benötigt zusätzlich die Entscheidungs- und
Freigaberegeln aus dem [Base Template](../governance/base-template.md).

### KI-orientiertes Figma-Inventar

**Zweck:** Eine Datei oder einen Bereich so erfassen, dass die KI technische
Sichtbarkeit, mögliche Systembedeutung und nächste Arbeitsschritte nicht
vermischt.

- [ ] Ein Inventar-Trigger ist benannt: Dateiübersicht ist beauftragt oder das
      relevante Arbeitsobjekt ist ohne begrenzte Übersicht nicht bestimmbar.
- [ ] Ein bekannter direkter Node oder Bereich reicht nicht bereits für die
      bestätigte Frage; sonst wird nicht inventarisiert.
- [ ] Analyse-Scope (`Datei`, `Page`, `Section`, `Frame`, `Komponente` oder
      `Node`) und gewünschte Entscheidung sind benannt.
- [ ] Das Strukturinventar enthält nur tatsächlich sichtbare Arbeitsobjekte
      mit Name, ID und Evidenztyp (`E0` bis `E4`).
- [ ] Das Systeminventar trennt `nur sichtbar`, `möglicher Kandidat`,
      `menschlich bestätigt` und `bewusst ausgeschlossen`.
- [ ] Arbeitsobjekt-Typ und Vertragsrelevanz werden nicht aus bloßer
      Sichtbarkeit geraten.
- [ ] Das Arbeitsinventar enthält genau eine begründete nächste Aktion;
      Dokumentation, Review, Vertragsableitung und Änderung bleiben getrennt.
- [ ] Ein Screenshot, Detailkontext oder Library-Treffer wird nicht als
      semantische, Accessibility- oder Übernahmefreigabe ausgegeben.

**Ergebnis:** `inventar belastbar`, `Bedeutung offen` oder `zur menschlichen
Einordnung vorlegen`.

## Testkarte für Kontext-Shortcuts

**Zweck:** Einen Kurzbefehl wie `START CHAT` als Hilfe für einen neuen oder
wiederaufgenommenen Arbeitskontext prüfen. Der Test bewertet Orientierung,
Kontextpassung und aufgabenbezogene Tooling-Bereitschaft – nicht die Qualität
der späteren Facharbeit oder die globale Verfügbarkeit aller Tools.

**Anwendungszeitpunkt:** Bei Einführung, wesentlicher Änderung oder erneuter
Bewertung eines Kontext-Shortcuts. Die vier Fälle können über mehrere reale
Starts gesammelt werden; es entsteht keine eigene Testumgebung oder
Handover-Datei.

**Vorbedingungen:**

- [ ] Der Start enthält eine konkrete Aufgabe und keinen vorab geladenen
      Vollkontext.
- [ ] Die erwartete Nutzungsebene ist für die prüfende Person bekannt oder
      als bewusst unklar markiert.
- [ ] Für einen folgenreichen Anschluss ist ein letzter relevanter Befund mit
      Decision oder offener Frage vorhanden.
- [ ] Kein Tool wird allein für den Test aktiviert; ein Tool wird nur geprüft,
      wenn die konkrete Aufgabe es erfordert.

**Drei minimale Fälle:**

| Fall | Startaufgabe | Besteht, wenn … |
|---|---|---|
| Qualitätsfrage | Einen generischen Baustein beurteilen oder eine konkrete Qualitätsfrage klären. | `Fachliche Nutzung`, Wiki-Einstieg und passende Qualitätsquelle werden gewählt; Systemhistorie und nicht benötigtes Tooling bleiben außen vor. |
| System-/Toolingfrage | Eine Regel, Quelle oder Werkzeuggrenze bewerten. | `Systementwicklung`, docs-Einstieg und passende Decision/Evaluation werden gewählt; benötigtes Tooling erhält einen belegten Status statt einer Annahme. |
| Folgenreicher Anschluss | Einen offenen oder entscheidungsrelevanten Strang fortsetzen. | Letzter Befund und Anschlusskern machen Absicht, Erkenntnis, Geltung/Grenze, Offenheit und nächsten Schritt ohne Chat-Verlauf verständlich. |
| Verbundener Fall | Eine Qualitätsfrage erzeugt zugleich einen möglichen Lern-, Regel- oder Toolingbefund. | Beide Ebenen werden ohne Auswahl erkannt; Quellen, Evidenz, menschliche Abnahme und nächster Schritt bleiben getrennt. Der Fachbefund wird nicht automatisch zur Systemregel. |

**Prüffragen je Fall:**

- [ ] Ziel, Gegenstand, Nutzungsebene, Modus und Rolle sind vor der Aktion
      verständlich ausgewiesen; bei verbundenem Anliegen sind Ebenen und
      Abnahmen getrennt.
- [ ] Der Agent leitet die Nutzungsebene selbst ab; bei nicht ableitbarem
      Kontext liest er beide Einstiegskarten und markiert die Einordnung als
      vorläufig statt eine Auswahl abzufragen.
- [ ] Die gelesenen Quellen sind minimal, begründet und die bewussten
      Auslassungen sichtbar.
- [ ] Jedes tatsächlich benötigte Tool weist Verfügbarkeit, konkreten Scope,
      Zugriff oder Laufzeit und eine belastbare Alternative aus; nicht
      benötigte Tools bleiben ungeprüft.
- [ ] Externe Wissensquellen gelten nur mit passenden, zuordenbaren Treffern
      als Evidenz.
- [ ] Menschliche Aufgabe, Agentenunterstützung, technische Grenze, offene
      Entscheidung und genau ein nächster Schritt sind unterscheidbar.
- [ ] Die prüfende Person kann ohne Zusatzwissen erklären, weshalb dieser
      Einstieg und diese Toolprüfung gewählt wurden.

**Abbruch- und Entscheidungskriterium:** Abbrechen und als `überarbeiten`
werten, wenn wesentlicher Kontext fehlt, ein unpassendes oder nicht benötigtes
Tool geprüft wird, eine Evidenz- oder Freigabegrenze verschwimmt oder die
Einordnung zusätzliche Erklärung braucht. `bestanden` erfordert vier
nachvollziehbare Fälle ohne solche Abweichung. `bestanden mit Nacharbeit`
erlaubt klar abgegrenzte redaktionelle Lücken; es autorisiert keine
Regelübernahme.

**Nachweis im Evaluation Log:** Fall, gelesene und bewusst ausgelassene
Quellen, benötigtes Tooling mit Status, fehlender Kontext, Verständlichkeits-
Rückmeldung, Aufwand (Anzahl Quellen und Toolprüfungen, keine künstliche
Tokenquote) sowie Konsequenz `übernehmen`, `überarbeiten`, `verwerfen` oder
`weiter testen`.

### Geeignete erste Figma-Tests

- Eine konkrete Library rein lesend auf Komponenten-, Varianten- oder
  Variablenstruktur auslesen.
- Prüfen, ob ein Node-Link den nötigen Design-Kontext vollständig liefert.
- Eine Token- oder Komponentenstruktur in primitive, semantische und
  komponentenspezifische Ebene einordnen.

Der Testbericht hält zusätzlich fest, welche Informationen das gewählte Tool
nicht liefern konnte. Fehlende Tool-Sichtbarkeit wird nicht als fehlende
Library-Struktur ausgelegt.

## Transparenznachweis vor Abschluss

Diese kurze Prüfung gilt für jeden relevanten Befund, Pilotabschluss oder
Systementwicklungsschritt.

- [ ] Modus und Rolle sind sichtbar; eine abgeleitete Rolle ist als solche
      gekennzeichnet.
- [ ] Quellen und ausgeführte Aktion sind benannt.
- [ ] Automatisch ausgeführte Schritte und unveränderte Bereiche sind benannt.
- [ ] Menschliche Vorgaben, Prüfung, Entscheidung oder fehlende Freigabe sind
      benannt.
- [ ] Offene Frage, Risiko und genau ein nächster prüfbarer Schritt sind sichtbar.
- [ ] Eine dritte Person könnte den Befund ohne Chat-Verlauf einordnen.

**Ergebnis:** `selbsterklärend`, `nacharbeiten` oder `nicht abschließen`.

## Menschenzentrierte Wiki-Prüfung (`WIKI PRÜFEN`)

**Zweck:** Prüfen, ob die Wiki als Vermittlungsschicht für Menschen ohne
Chat-, Struktur- oder Modellvorwissen funktioniert.

**Anwendungszeitpunkt:** Bei strukturellen Wiki-Änderungen, neuen relevanten
Inhalten und als wiederkehrender Informationsarchitektur-Review.

- [ ] Jede geprüfte Seite beginnt mit Zweck und Hauptaussage.
- [ ] Relevanz für Gestaltung, Entwicklung oder menschliche Entscheidung ist
      verständlich erklärt.
- [ ] Status, betrachtete Ebene, offene Fragen und genau ein nächster
      prüfbarer Schritt sind auffindbar.
- [ ] Automatische Ausführung, menschliche Prüfung, Steuerung und Freigabe sind
      getrennt benannt.
- [ ] Fachbegriffe sind beim ersten Auftreten erklärt oder verlinkt.
- [ ] Die Reihenfolge führt von Verständnis über Bewertung zu Handlung.
- [ ] Selektives Lesen ist möglich: Orientierung, Auswahl/Handlung und Detail
      sind erkennbar getrennt.
- [ ] Überschriften, Statuslabels, Tabellen, Links und `Code` unterstützen die
      Wissenshierarchie semantisch und nicht nur dekorativ.
- [ ] Detailregeln werden nicht dupliziert; verbindliche Quellen sind verlinkt.
- [ ] Seitenschnitt und Themenüberschneidungen sind begründet oder als Lücke
      ausgewiesen.
- [ ] Alle Wiki-Links sind gültig: rekursiv alle Dateien unter `wiki/`,
      einschließlich relativer Dateien, Tabellenlinks und Abschnittsanker,
      werden geprüft.
- [ ] In der Orientierungslandkarte sind „Lesen Sie zuerst“ und die
      verbindliche Quelle als passende, klickbare Ziele ausgewiesen; kein
      erklärender Linktext verweist auf eine nicht vorhandene Wiki-Seite.

### Linktest-Ebenen

- [ ] **Technisch:** Zielpfad, Markdown-Syntax und Abschnittsanker sind gültig.
- [ ] **Strukturell:** erwartete Tabellenzeilen, Spalten und Pflichtfelder sind
      vorhanden; Pflichtfelder enthalten klickbare Ziele.
- [ ] **Semantisch:** Linktext, Einstiegsseite und verbindliche Quelle passen
      fachlich zusammen; eine bloße Dateiexistenz gilt nicht als ausreichend.

Der Test weist getrennt aus:

```text
Wiki-Dateien:
Links:
Abschnittsanker:
Orientierungs-/Quellentabellen:
Tabellenzeilen:
Pflichtfelder:
Technische Fehler:
Strukturelle Fehler:
Semantische Unklarheiten:
Nicht geprüft:
Ergebnis:
```

`Nicht geprüft` bleibt nicht leer, wenn keine semantische oder gerenderte
Prüfung stattgefunden hat. Der Gesamtstatus darf nur den tatsächlich geprüften
Umfang abdecken.

**Ergebnis:** Gesamtstatus, seitenweise Befunde, höchstens ein kleiner
Anpassungsvorschlag je Befund und genau ein nächster prüfbarer Schritt.

Die Prüfung erzeugt keine neue Datei und setzt keine weitere Regel. Eine
strukturelle Regeländerung benötigt eine separate Entscheidung.

## Technisch und informationell versierter Review

**Zweck:** Prüfen, ob ein Wunsch oder eine Strukturänderung dem Ziel dient,
technisch und agentisch machbar, informationell verständlich sowie im
Designer-Alltag lean und operationalisierbar ist.

**Anwendungszeitpunkt:** Bei neuen Anforderungen, Tooling-Vorschlägen,
Wiki-Strukturänderungen, neuen Regeln und vor Pilot- oder Standardübernahme.

- [ ] Zielbeitrag und aktueller Reifegrad sind geklärt.
- [ ] Passende Tool-Funktion und Zugriffsebene sind begründet.
- [ ] Sichtbare Evidenz und Tooling-Grenzen stehen vor fachlichen Ableitungen.
- [ ] Machbarkeit, Token-/Zeitaufwand, Pflegekosten und Alternativen sind
      bewertet.
- [ ] Der erwartete Nutzen für die betroffene Rolle, die Folge des
      Nichtstuns und die kleinste prüfbare Umsetzung sind benannt.
- [ ] Die Maßnahme ist als `jetzt umsetzen`, `Pilot/Kandidat`, `bewusst
      bewahren`, `derzeit nicht relevant` oder `verwerfen/ablösen`
      eingeordnet; eine weitere Iteration hat einen Evidenz- oder
      Entscheidungsgrund.
- [ ] Informationsarchitektur, Wissensvermittlung und Rollenpassung sind
      geprüft.
- [ ] Die kleinste geeignete Umsetzung ist benannt.
- [ ] Risiko, offene menschliche Entscheidung und genau ein nächster Schritt
      sind sichtbar.
- [ ] Fachliche Nutzung und Systementwicklung sind als getrennte Gegenstände
      bewertet; ein verbundener Befund weist beide Abnahmen separat aus.
- [ ] Jede gekürzte oder verschobene Regel/Funktion ist in der Zielquelle
      auffindbar; keine Schutzwirkung oder bestehende Funktion ist entfallen.
- [ ] Jede Regel hat genau eine verbindliche Quelle.
- [ ] `AGENTS.md` enthält nur unmittelbar ausführungsrelevante Sicherheits- und
      Routingregeln; Detailwissen ist verlinkt.
- [ ] Die Änderung führt keinen neuen Pflichtprozess, keine doppelte
      Checkliste und keine unnötige Datei ein.
- [ ] Die Schutzwirkung bleibt für Lesen, Pilot und Standardänderung
      nachvollziehbar.

**Ergebnis:** `ausführen`, `als Vorschlag begrenzen`, `zur Entscheidung
vorlegen` oder `nicht ausführen`.

## Verhältnismäßige Testauswahl

Tests werden an Regeln, Änderungsereignisse und Risiken gekoppelt. Nicht jede
Regel erhält einen eigenen Test.

| Anlass | Mindesttest |
|---|---|
| Routine-Dokumentationsänderung | Link-, Struktur- und Statuscheck |
| Wiki-, Rollen- oder Governance-Änderung | `WIKI PRÜFEN` |
| neue Regel oder strukturelle Änderung | Evaluation plus passender Szenariotest |
| Pilotabschluss oder Standardübernahme | Vollprüfung und menschliche Abnahme |
| konkrete Figma-Fähigkeitsbehauptung | begrenzter read-only Figma-Test |
| kein belegter Bedarf | kein zusätzlicher Test |

Die Testpyramide bleibt lean: viele kostengünstige Strukturtests, wenige
realistische Szenarien und ein Praxistest mit einer dritten Person nur bei
wesentlicher menschenzentrierter Änderung.

## Offene Arbeitsfragen

- Welche Prüfungen gelten für jedes Projekt?
- Welche Prüfungen gelten nur für bestimmte Artefakte?
- Wer bestätigt ein Ergebnis?
