# Evaluation Framework

Status: Entwurf

Dieses Framework ist die wiederkehrende Qualitätsprüfung für die
Projektsteuerung, die operative Dokumentation und die menschliche Wiki. Es
prüft nicht nur, ob Dateien vorhanden sind, sondern ob sie Design Ops
unterstützen, lean und ausführbar bleiben und Menschen den Stand verstehen und
bewerten können.

Es ist kein Compliance-Zertifikat. „State of the art“ bedeutet hier: aktuelle,
risikobasierte Governance mit klaren Rollen, nachvollziehbaren Entscheidungen,
kontrollierter Änderung und verständlicher Informationsarchitektur.

## Reihenfolge jedes Evaluationsbefunds

Jeder Befund beginnt mit dem **Evidenz- und Toolingstatus**, bevor fachliche
Ableitungen erscheinen:

1. Arbeitsmodus und Rolle
2. gewählte Tool-Funktion und tatsächlicher Scope
3. automatisch sichtbare Informationen
4. nicht sichtbare oder nicht geprüfte Informationen
5. Vollständigkeit und Unsicherheit der Evidenz
6. erst danach: fachliche Bewertung, Design-Ops-Befund und Empfehlung

Fehlt die notwendige Evidenz, wird der fachliche Aspekt als `nicht bewertet`
oder `eingeschränkt bewertet` ausgewiesen. Tooling-Grenzen werden nicht in
fachliche Qualitätsmängel umgedeutet.

## Anwendung

| Anlass | Prüfung | Nachweis |
|---|---|---|
| Folgenreiche Entscheidung, Ausnahme oder neue Steuerungsregel | Kurzprüfung | Ein Zeile im [Evaluation Log](evaluation-log.md) |
| Strukturänderung, Pilotabschluss oder Übernahme als Standard | Vollprüfung | Vollständiger Befund im Evaluation Log |
| Wiederkehrender Projekt-Review | Vollprüfung und Vergleich zum letzten Befund | Trend und nächste Korrektur |

## Bewertungsmaßstab

Jedes Kriterium erhält einen Status:

| Status | Bedeutung |
|---|---|
| `0 – kritisch` | fehlt, ist widersprüchlich oder verhindert sichere Ausführung bzw. verständliche Kontrolle |
| `1 – teilweise` | vorhanden, aber nicht vollständig operationalisiert oder noch ungeprüft |
| `2 – erfüllt` | klar, auffindbar, anwendbar und für den aktuellen Umfang nachgewiesen |
| `n/a` | für den geprüften Umfang nicht relevant; Begründung erforderlich |

Ein Vollbefund ist nur `bestanden`, wenn kein kritisches Kriterium offen ist.

## A. Design-Ops- und Governance-Konformität

| Kriterium | Prüffrage |
|---|---|
| Entscheidungsrechte | Ist klar, was Agenten ausführen, vorschlagen oder eskalieren müssen? |
| Quellen- und Regelhierarchie | Ist die verbindliche Quelle für jede relevante Regel auffindbar und konfliktfähig eingeordnet? |
| Status-/Anwendungsabgleich | Ist sichtbar, ob eine praktisch referenzierte Regel bestätigt, als Pilot begrenzt oder noch Regelkandidat ist? |
| Nachvollziehbarkeit | Sind folgenreiche Entscheidungen, Ausnahmen und Ablösungen im Decision Log nachvollziehbar? |
| Wiederverwendung | Wird vor Neuerstellung nach bestehenden Bausteinen gesucht und die Entscheidung begründet? |
| Lebenszyklus | Gibt es einen Weg von Entwurf über Pilot zu bestätigter Regel oder Verwerfung? |
| Tool-Fit | Ist für Figma-, Design-System- und Code-Aufgaben die passende Werkzeugfamilie benannt, ohne Fähigkeiten vorzutäuschen? |
| Externe KI-Einsatzfreigabe | Sind Integrationsweg, Lizenz-/Planstatus, Datenfluss, ISMS-/ISB-Status und die Grenzen für Lesen, Vorschlag und Schreiben sichtbar, ohne eine Freigabe zu unterstellen? |
| Funktionswahl und Prompt-Scope | Wählt der Agent die passende und tokensparende Zugriffsebene selbst, formuliert den passgenauen Prompt und macht jede dadurch entstehende Einschränkung transparent? |
| Befundtrennung | Werden Tooling-Grenzen getrennt von fachlichen Qualitätsbefunden bewertet, sodass nicht zugängliche Aspekte nicht als fachliche Mängel erscheinen? |
| Agentische Arbeitsteilung | Sind Lesen, Bewerten, Vorschlagen, Schreiben und Freigeben sicher getrennt und ist die technische Funktion passend gewählt? |
| State-of-the-art-Nachweis | Werden aktuelle agentische, Tooling- oder Informationsdesign-Empfehlungen durch belastbare Quellen oder einen begrenzten Test abgesichert? |

## B. Lean und Operationalisierbarkeit

| Kriterium | Prüffrage |
|---|---|
| Zweckbindung | Hat jedes Artefakt einen eindeutigen Zweck und keine bloße Dokumentationsdoppelung? |
| Zielgruppenpassung | Passen Zielgruppe, Zweck, Inhaltstyp und Detailtiefe des Inhalts zum gewählten Artefakt? |
| Ausführbarkeit | Benennt jede relevante Regel Auslöser, zulässige Aktion, erwartetes Ergebnis und nötigen Nachweis? |
| Proportionalität | Ist Tiefe, Prüfaufwand und Freigabe dem Risiko und der Reichweite angemessen? |
| Aktive Gegenprüfung | Prüft der Agent vor Zustimmung oder Erweiterung aktiv Zielbeitrag, Wiederverwendung, Overhead, Tokenaufwand und Operationalisierbarkeit? |
| Entwicklungspriorisierung | Ist die Maßnahme als `jetzt umsetzen`, `Pilot/Kandidat`, `bewusst bewahren`, `derzeit nicht relevant` oder `verwerfen/ablösen` eingeordnet – einschließlich Nutzen, Aufwand und begründeter Nicht-Umsetzungsoption? |
| Auffindbarkeit | Finden Agenten und Menschen die zuständige Quelle über stabile Links und klare Benennung? |
| Rückfluss | Werden bestätigte Muster, Ausnahmen und Fehler kontrolliert in Regeln oder Wiki-Einordnung überführt? |
| Designer-Praxistauglichkeit | Unterstützt die Lösung eine konkrete Entwurfshandlung mit vertretbarem Pflege- und Dokumentationsaufwand? |
| Verhältnismäßige Tests | Ist die Testtiefe an Anlass, Risiko und Reichweite gekoppelt, ohne ein paralleles Testsystem aufzubauen? |

## C. Menschliche Verständlichkeit und gestalterische Einordnung

| Kriterium | Prüffrage |
|---|---|
| Orientierung | Ist klar, worum es geht, wo das Projekt steht und welche Ebene gerade betrachtet wird? |
| Kognitive Entlastung | Beginnt jede Wiki-Seite mit Zweck und Hauptaussage, gliedert Informationen in kleine erkennbare Abschnitte und vermeidet unnötige Wiederholung? |
| Lesbarkeit | Sind Überschriften, Sprache, Links und Begriffe verständlich, eindeutig und für die Zielgruppe erklärt? |
| Transparenz | Werden Status, offene Fragen, Grenzen, Entscheidungen und ihre Auswirkungen sichtbar? |
| Automatik und Kontrolle | Ist eindeutig, was automatisch geschieht und was der Mensch steuert, prüft oder freigibt? |
| Selbsterklärung | Kann eine dritte Person Auftrag und Ergebnis ohne Chat-Verlauf nachvollziehen? |
| Motivation und Handlungsfähigkeit | Wird deutlich, warum ein Thema für die eigene gestalterische Arbeit relevant ist und was als Nächstes geprüft oder entschieden werden kann? |
| Funktionale Einordnung | Werden Funktionen, technische oder operative Änderungen als Wirkung auf Nutzung, Gestaltung und Arbeitsprozess erklärt – nicht nur als Datei- oder Tooländerung? |
| Informationsarchitektur | Folgt die Wiki den Fragen von Menschen und verweist sie gezielt auf die verbindliche Quelle, ohne sie mit Detailregeln zu überladen? |
| Menschenzentrierter Seitenstandard | Beginnt jede Wiki-Seite mit Zweck und Hauptaussage und vermittelt sie ohne Chat-, Struktur- oder Modellvorwissen Relevanz, Status, Arbeitsteilung, offene Entscheidung und nächsten Schritt? |
| Begriffliche Zugänglichkeit | Werden Fachbegriffe beim ersten Auftreten erklärt oder verlinkt, statt implizites Projektwissen vorauszusetzen? |
| Progressive Offenlegung | Ermöglicht die Seite selektives Lesen von Orientierung über Entscheidungshilfe bis zu Detail und verbindlicher Quelle? |
| Semantische Auszeichnung | Unterstützen Überschriften, Statuslabels, Tabellen, Links und Codeformatierung die Wissenshierarchie und Lesbarkeit statt nur dekorativ zu wirken? |
| Rollenpassung | Sind die Bedürfnisse der angesprochenen Arbeitsrolle und ihr konkreter Prüffokus aus dem Governance-Artefakt ableitbar? |
| Werkzeugverständnis und Rationale | Werden Fähigkeiten, Grenzen, Does & Don’ts und die fachliche Begründung für relevante Design- oder Tooling-Entscheidungen vermittelt? |
| Informationsdesign | Unterstützen Aufbau, Textmenge und Auszeichnung die konkrete Nutzungssituation der angesprochenen Rolle? |
| Mensch-/Maschinenschicht | Sind operative Regeln und Prüfschritte von menschlicher Einordnung, Motivation und Didaktik getrennt? |
| Linktest-Abdeckung | Werden technische Linkgültigkeit, strukturelle Pflichtfelder und semantische Quellenpassung getrennt geprüft und im Umfang korrekt ausgewiesen? |

## Ergebnis und Rückführung

Der Befund enthält immer:

1. Evidenz- und Toolingstatus
2. geprüfter Umfang und Anlass
3. Status je Bereich (`0`, `1`, `2` oder `n/a`)
4. kritische Lücken und konkrete Korrektur
5. Wiki-Auswirkung und notwendige Aktualisierung
6. Entscheidung: `bestanden`, `bestanden mit Nacharbeit` oder `nicht bestanden`

Bei Register-Detail-Quellen wie dem Evaluation Log ist ein Nachweis erst
vollständig, wenn Übersichtseintrag, Detailbefund, ID, Reihenfolge und interne
Verweise konsistent geprüft sind.

Korrekturen gehen in die zuständige Regeldatei. Erfordert die Korrektur eine
neue Regel, Ausnahme oder Freigabe, wird zusätzlich das Decision Log gepflegt.

## Routineprüfung der Wiki-Informationsarchitektur

Der Steuerbefehl `WIKI PRÜFEN` löst eine Vollprüfung der menschlichen
Vermittlungsschicht aus. Die Prüfung umfasst den Seitenschnitt, die Reihenfolge
der Wissensvermittlung, Quellenverweise, Status- und Verantwortlichkeitstransparenz,
Begrifflichkeit, kognitive Last sowie interne Links. Der Befund trennt
redaktionelle Lücken von fachlichen oder maschinenbezogenen Mängeln und erzeugt
höchstens einen kleinen Anpassungsvorschlag pro Befund.
