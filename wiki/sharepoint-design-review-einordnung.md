# SharePoint-Wissen zum Design Review: Einordnung

## Worum es hier geht

Die bereitgestellte SharePoint-Quelle beschreibt einen historisch gewachsenen
Design-Review-Prozess, Figma-Handoff-Praxis sowie Hinweise zu Tokens und Dev
Mode. Diese Seite macht das Wissen als **Vergleichs- und Orientierungsquelle**
auffindbar. Sie übernimmt daraus keine neue verbindliche Regel.

**Status:** `beobachten` – Quelle erhoben; einzelne Erkenntnisse sind
Regelkandidaten, keine bestätigten Standards.

## Quelle, Evidenz und Grenze

| Feld | Befund |
|---|---|
| Quelle | Bereitgestellter Export „Design Review Prozess“ vom SharePoint, 1.770 Zeilen; lokale Kopie außerhalb des Repositories. |
| Sichtbar | Reviewrollen und -schritte, Ticket-/Artefaktbezüge, Figma-/Miro-/SharePoint-Nutzung, Token-, Variablen- und Dev-Mode-Hinweise. |
| Nicht geprüft | Vollständigkeit des SharePoint-Bestands, verlinkte Szenarien und PDFs, reale Zugriffsrechte, aktueller Tool-/Planstand sowie tatsächliche Projektpraxis. |
| Geltung | Organisations- bzw. projektspezifische Referenz; keine automatisch gültige Quelle für das generische Base Template. |

Die Bewertung stützt sich auf die sichtbare Exportfassung. Aussagen zu Figma
Features, Plugins, API-Zugängen, GitHub oder Enterprise-Plänen sind
zeitgebunden und daher keine aktuelle Tooling-Evidenz.

## Struktur des erhobenen Wissens

| Kategorie | Inhalt der Quelle | Relevanz für dieses Projekt |
|---|---|---|
| Review und Abnahme | asynchrone/synchrone Reviews, Rollen, Annotationen, Iteration, Kundenabnahme | hoch – als Praxisfall für spätere Projektkits und Übergaben |
| Nachweis und Arbeitsstand | benannte Versionen, Single Point of Truth, Links, Anforderungen, Entscheidungshistorie | hoch – passt zu Transparenz, Quelle und Abnahme |
| Design–Development-Schnittstelle | technischer Review, Machbarkeit, Übergabe, Umsetzungsabgleich | hoch – ergänzt die vorhandene Handoff-Einordnung |
| Qualitätskriterien | Vollständigkeit, Nachvollziehbarkeit, Konsistenz, Usability, Accessibility, Machbarkeit | mittel – nützlich als Fragen, nicht als universelle Checkliste |
| Figma-Library und Handoff | veröffentlichte, geprüfte Stände; Komponenten-/Entwurfsdateien; Dev Mode | mittel – Zielbild einer späteren Projektausprägung, derzeit nicht Teil von v0.1/v0.2 |
| Tokens und Variablen | primitive/semantische/Komponentenebene, Modes, Benennung, Alias/Nesting | mittel – Grundprinzipien passen; konkrete Struktur erst bei realem Projektbedarf |
| Tool- und Organisationsabläufe | Redmine, SharePoint, Miro, GitHub-Workflows, Plugins, kundenspezifische Rollen | außerhalb des Projektkerns; als Schnittstellenkontext sichtbar |

## Bewertung gegenüber dem Bestand

| Fundstück / Aussage | Bestand und Überlappung | Einordnung | Rückfluss |
|---|---|---|---|
| Review braucht klaren Stand, Version, Annotationen und Anforderungsbezug. | [Base Template](../docs/governance/base-template.md) verlangt Quelle, Kontext, Abnahme und Nachweis; die [Übergabe](figma-handoff.md) benennt Kontext und offene Fragen. | **Anschlussfähig mit Anpassungsbedarf:** Der Bestand ist absichtlich generisch; ein konkretes Review-Gate wäre erst im Projektkit sinnvoll. | Regelkandidat: minimale Review-Evidenz an einem realen Fall testen. |
| Design-, Development- und Review-Perspektiven prüfen unterschiedliche Aspekte. | Rollen und ihre Grenzen sind im [Arbeitsmodell](working-model.md) und im Base Template getrennt. | **Direkt anschlussfähig:** bestätigt die vorhandene Arbeitsteilung, ohne neue Rechte zu erzeugen. | Kein neuer Standard nötig. |
| Ein Designstand wird erst nach Review als umsetzbar übergeben; Umsetzung wird gegen die Designabsicht rückgeprüft. | [Qualität übergeben und abnehmen](figma-handoff.md) beschreibt bereits Zweck, Zustände, offene Fragen und gemeinsame Abnahme. | **Anschlussfähig:** Der Quellenbefund konkretisiert den Nutzen eines expliziten Reife-/Übergabestatus. | Regelkandidat: Status- und Rückprüffelder mit einem realen Handoff erproben. |
| Vollständigkeit, Nachvollziehbarkeit, Selbsterklärung, Konsistenz, Machbarkeit, Usability und Accessibility sind Reviewgesichtspunkte. | Der Bestand fordert Qualitätsnachweis, Semantik, Zustände und Accessibility; er besitzt bewusst keine fachliche Design-QA-Checkliste. | **Relevant, aber nicht unmittelbar normierbar:** Kriterien müssen je Baustein, Nutzung und Risiko ausgewählt werden. | Als Fragen in einem späteren Projekt-Review verwenden, nicht pauschal in Operations übernehmen. |
| Eine Library ist Single Point of Truth; nur geprüfte Stände werden veröffentlicht. | v0.1/v0.2 schließen konkrete Library-Dateien, Publishing und Projektkits ausdrücklich aus. | **Derzeit out of scope, als Schnittstelle relevant.** | Bei aktivierter Projektableitung Library-Lebenszyklus, Version und Übergabeart klären. |
| Tokens sind in primitive, semantische und komponentenspezifische Ebenen zu ordnen; Modes folgen einem klaren Zweck. | [Standards](../docs/foundations/standards.md) enthält dieselbe Ebenentrennung; konkrete Collections, Modes und Namenssyntax sind offen. | **Direkt anschlussfähig im Prinzip; projektspezifisch in der Ausprägung.** | Kein neues Dokument; bei realen Tokens nur belegte Projektanforderungen ergänzen. |
| Figma-Plugins, API, Dev Mode, GitHub-Token-Synchronisation oder Miro unterstützen Übergabe und Automatisierung. | Die [Tooling Map](../docs/tooling/tooling-map.md) verlangt konkrete Freigabe, Datenfluss- und Scopeprüfung; Miro und externe KI-/Plugin-Wege stehen derzeit auf `STOPP`. | **Nicht als Toolentscheidung verwendbar.** Historische Produkt-/Planangaben sind nicht validiert. | Erst bei konkreter Lücke eine begrenzte, freigegebene Toolprüfung starten. |
| Redmine, SharePoint und kundenspezifische Rollen steuern Tickets, Ablage und Kommunikation. | Das Base Template bleibt werkzeug- und organisationsneutral. | **Out of scope, jedoch Schnittstellenwissen.** | Bei einer Projektableitung nur Verantwortungs-, Link- und Nachweisbedarf übernehmen; kein Tool erzwingen. |

## Was bewusst nicht übernommen wird

- konkrete Ticketstatus, Rollenbezeichnungen, Jour-fixe- und Kundenabläufe;
- Redmine-, SharePoint-, Miro-, GitHub- oder Plugin-Konfigurationen;
- eine verbindliche Figma-Datei-, Library- oder Publishing-Struktur;
- Aussagen über aktuelle Figma-, Dev-Mode-, API- oder Lizenzfähigkeiten;
- eine vollständige Design-QA-Checkliste ohne konkreten Baustein und Nutzungskontext.

Diese Themen können Schnittstellenbedingungen eines späteren Projektkits sein.
Sie sind keine Lücke des aktuellen generischen Regelkerns.

## Gezielte Regelkandidaten

| Kandidat | Nutzen | Kleinste Prüfung | Entscheidung erforderlich |
|---|---|---|---|
| Review-Evidenz für einen übergabefähigen Stand | Design und Development können denselben Stand, offene Fragen und Abnahme nachvollziehen. | Ein realer, begrenzter Handoff mit Quelle, Versions-/Standreferenz, Anforderungen, offenen Punkten und Abnahmekriterium. | Ob dies als projektspezifische Checkliste übernommen wird. |
| Reife- und Rückprüfstatus zwischen Design und Umsetzung | Verhindert, dass Entwurf, geprüfter Übergabestand und Umsetzung vermischt werden. | Einen einzelnen Baustein oder Frame vor und nach Umsetzung vergleichen. | Ob ein Statusmodell nötig ist und wo es verbindlich liegt. |
| Kontextabhängige Reviewdimensionen | Qualitätsfragen werden früh sichtbar, ohne einen pauschalen Prozess zu erzeugen. | Für einen Baustein höchstens die relevanten Dimensionen auswählen: Anforderungen, Semantik, Zustände, Accessibility, Machbarkeit oder Konsistenz. | Ob eine projektbezogene Reviewkarte nachgewiesen wiederverwendbar ist. |

## Zweiter Input: abgeleitete Checklisten

Der zweite bereitgestellte Text übersetzt Teile der SharePoint-Quelle in sieben
Checklisten. Er ist damit eine **Interpretation und Operationalisierung** der
erhobenen Quelle, keine weitere Primärquelle oder beschlossene Regel.

| Vorgeschlagene Checkliste | Passfähigkeit | Grenze und sinnvoller Rückfluss |
|---|---|---|
| Review-Freigabe | hoch | Ein klarer Stand, Quelle, Anforderungen, offene Fragen und Abnahme passen. Redmine, Versionsformat, Miro/Figma als fester Ort und „formal korrekt“ brauchen jedoch eine projektspezifische Definition. |
| Design-Qualität | mittel | Zustände, Semantik, Konsistenz und Accessibility passen zum Bestand. Marke, Projektstil, ausreichender Kontrast oder Zielgrößen sind erst mit Produkt, Plattform und Prüfmethode bewertbar. |
| Technisches Review | hoch | Wiederverwendung, Varianten, Machbarkeit und Übergabefragen passen zur Design–Development-Arbeitsteilung. Architektur, Sicherheit, Performance und Aufwand benötigen Codebasis, Anforderungen und verantwortliche Entwicklungsperspektive. |
| Kundenfreigabe | Schnittstellenthema | Nachweis von Entscheidung, Abnahme und Änderungsbedarf ist übertragbar. Kundentermin, Export und Ticketfolge sind organisations- bzw. projektspezifisch. |
| Design Handoff | hoch | Entspricht der vorhandenen [Übergabe-Einordnung](figma-handoff.md). „Veröffentlicht“, Dev Resources, Library und „Ready for Development“ sind erst bei aktivierter Figma-/Projektkit-Ebene sinnvoll. |
| Design–Implementierungs-Review | Pilot/Kandidat | Anforderungen, Zustände, visuelle und funktionale Abweichungen sind eine sinnvolle Abnahmeform. Sie setzt einen konkreten Designstand, eine Implementierung und einen erlaubten Vergleich voraus. |
| Design System und Variablen | mittel | Semantische Tokenebenen und Wiederverwendung passen zu den [Standards](../docs/foundations/standards.md). Collections, Modes, Zeichenregeln, Publishing und Hardcoding sind konkrete Projekt-/Toolentscheidungen. |

### Gemeinsames Raster: geeignet, aber nicht als Pauschalscore

Die drei vorgeschlagenen Dimensionen sind als **Auswahlhilfe** brauchbar:

| Dimension | Präzisierte Prüffrage |
|---|---|
| Vollständigkeit | Sind die für diesen Fall festgelegten Anforderungen, Zustände und Nachweise vorhanden? |
| Qualität | Erfüllt der Baustein die für ihn ausgewählten Kriterien, etwa Semantik, Verständlichkeit, Konsistenz, Accessibility oder Machbarkeit? |
| Nachvollziehbarkeit | Können Design, Development und Review Quelle, Entscheidung, aktuellen Stand, Abweichungen und Abnahme ohne Rückfrage verstehen? |

Das Raster ist kein universeller Qualitätsscore. Welche Unterfragen gelten,
folgt erst aus Baustein, Nutzungskontext, Risiko und verfügbarer Evidenz.

### Ergebnis der Einordnung

Die sieben Checklisten sind **kein** Kandidat für eine sofortige Übernahme als
vollständiger Prozess. Als kleinste, passende Praxisprobe empfiehlt sich
stattdessen eine Karte für einen einzigen Übergabefall:

```text
Quelle und Stand:
Anforderungen und Scope:
Erwartetes Verhalten, Varianten und Zustände:
Relevante Accessibility-/Responsive-Anforderungen:
Offene Design- und Umsetzungsfragen:
Abweichungen und Entscheidungsbedarf:
Gemeinsame Abnahme:
```

Sie fasst die anschlussfähigen Teile von Review-Freigabe, technischem Review,
Handoff und Umsetzungsabgleich zusammen, ohne Ticket-, Library-, Tool- oder
Kundenprozess zu unterstellen. Sie bleibt **Regelkandidat**, bis ein echter
Fall ihren Nutzen und Aufwand bestätigt.

## Nächster Schritt

Einen konkreten Übergabe- oder Komponentenfall auswählen und **einen** der
Regelkandidaten als kleinen, lesenden bzw. reversiblen Praxischeck prüfen.
Erst dessen Befund kann eine projektspezifische Checkliste oder Regel
rechtfertigen.
