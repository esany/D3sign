# Arbeitsmodell und menschliche Kontrolle

## Die drei Ebenen

```text
Base Template
  generische Regeln für einen Library-Grundbaustein
        ↓
Project Template
  spätere Vorlage für ein Projektkit
        ↓
Projektkit
  konkrete Library- und Entwurfsregeln eines Vorhabens
```

Die erste Ebene ist der aktuelle Entwicklungsgegenstand. Die beiden folgenden
Ebenen bleiben Zielbild und werden erst bei belegtem Projektbedarf konkret.

## Zwei Informationsschichten

| Schicht | Zweck | Erwartung an Leserinnen und Leser |
|---|---|---|
| Menschenschicht: Wiki | Bedeutung, Motivation, Status, Auswirkungen, Entscheidungen und nächste Handlung vermitteln | Kein Chat-, Struktur- oder Modellvorwissen erforderlich |
| Maschinenschicht: `AGENTS.md` und `docs/` | Regeln, Quellen, Abläufe, Prüfkriterien und maschinenlesbare Steuerung bereitstellen | Nur bei einer konkreten Prüfung oder Ausführung öffnen |

Die Wiki beschreibt deshalb nicht nur, **was** eine Datei enthält, sondern
auch, **warum** sie für die Arbeit relevant ist. Eine Regel wird in der Wiki
höchstens eingeordnet und verlinkt; ihre verbindliche Fassung bleibt in der
Maschinenschicht.

**Verbindlicher menschenzentrierter Mindeststandard gemäß D-019:** Jede neue Wiki-Seite
beginnt mit Zweck und Hauptaussage und beantwortet anschließend mindestens
Relevanz, Status, Arbeitsteilung, offene Entscheidung und nächsten Schritt.
Die vollständigen Prüfkriterien stehen im
[Evaluation Framework](../docs/governance/evaluation-framework.md) und in der
[Wiki-Checkliste](../docs/operations/checklists.md).

## Was geschieht automatisch, was steuert der Mensch?

Die Regeln unter `AGENTS.md` steuern das Verhalten des Agenten. Sie ersetzen
aber keine menschliche Ziel-, Risiko- oder Freigabeentscheidung.

| Bereich | Vom System automatisch bzw. regelgeleitet | Mensch kann steuern | Mensch muss ausdrücklich angeben oder entscheiden |
|---|---|---|---|
| Perspektive | Rolle aus eindeutiger Aufgabe ableiten | Rolle überschreiben | Rolle bei gemischtem oder folgenreichem Auftrag |
| Quellen | vorhandene Quellen suchen und Hierarchie anwenden | verbindliche Quelle priorisieren | Konflikt, fehlende oder unklare Quelle |
| Aktion | innerhalb bestätigter Regeln ausführen | Umfang und gewünschte Aktion setzen | neue Regel, neue Bausteine, Löschen oder Veröffentlichung |
| Test | Testkarte anwenden, Befund strukturieren | Tool, Kontext und Grenze wählen | Prüffrage, Abnahme und Abbruchkriterium |
| Status | Ergebnis und offenen Punkt dokumentieren | nächste Iteration anstoßen | Übernahme, Freigabe, Verwerfen oder Ausnahme |
| Wiki | bei relevanter Änderung Einordnung aktualisieren | Schwerpunkt und Verständlichkeit prüfen | fachliche Bedeutung oder Priorität ändern |

„Automatisch“ bedeutet hier: durch dokumentierte Regeln ausführbar. Es bedeutet
nicht, dass der Agent fachliche Absichten erraten oder Entscheidungen ersetzen
darf.

### Mindestverständlichkeit für Dritte

Ein Auftrag und sein Ergebnis müssen ohne Chat-Verlauf erkennen lassen:

1. Worum geht es?
2. In welchem Modus wurde gearbeitet?
3. Welche Rolle und Quellen galten?
4. Was wurde automatisch getan und was blieb unverändert?
5. Was muss ein Mensch noch prüfen oder entscheiden?

Der verbindliche Kurz-Nachweis steht im
[Base Template](../docs/governance/base-template.md).

## Evidenzbasierte Toolnutzung

Wenn KI ein Werkzeug nutzt, soll nicht das Werkzeug die Arbeit definieren. Die
menschlich wichtigste Prämisse lautet: Vor jedem Toolaufruf muss klar sein,
welche fachliche Frage beantwortet werden soll, welche Quelle dafür minimal
erforderlich ist und welchen Evidenzstatus das Ergebnis später haben kann.

| Rolle | Verantwortung |
|---|---|
| Mensch | Ziel, fachliche Frage, bekannte Quellen, Grenze und Entscheidungskontext benennen. |
| KI / Agent | passenden Tool-Fit vorschlagen, begründen, fehlende Quellen anfordern und Evidenzstatus ausweisen. |
| Werkzeug | einen begrenzten Ausschnitt liefern; es ersetzt keine fachliche Auslegung oder Freigabe. |

Menschen müssen dafür nicht die technische Funktion oder jede Node-ID kennen.
Hilfreich sind aber konkrete Arbeitsobjekte und die beabsichtigte Bewertung:
etwa „dieser Frame für visuelle Prüfung“, „diese Komponente für Varianten“ oder
„diese Quelle nur als Vergleich“. Ist die Quelle zu grob, muss der Agent das
sichtbar machen und die kleinste belastbare Nachschärfung anfordern.

Die operative Ausführung steht in den
[Arbeitsprinzipien für evidenzbasierte Toolnutzung](../docs/operations/workflows.md#arbeitsprinzipien-fur-evidenzbasierte-toolnutzung).

## Der iterative Entwicklungsschritt

```text
eine fachliche Annahme
        ↓
ein kleiner wiederverwendbarer Baustein
        ↓
eine konkrete Projektableitung
        ↓
Pass/Fail-Befund
        ↓
bestätigen, überarbeiten oder verwerfen
```

Eine Iteration erweitert das System nur, wenn der Prüffall einen Bedarf oder
wiederverwendbaren Nutzen belegt. Der aktuelle v0.1-Schritt prüft generische
Library-Regeln. Die nächste Ausbaustufe v0.2 prüft eine einzelne
read-only-Tooling-Fähigkeit; eine konkrete Komponenten- oder Tokenbibliothek
entsteht auch daraus noch nicht.

## Test oder Systementwicklung?

### Zwei Gegenstände, zwei Abnahmen

Die **fachliche Nutzung** fragt: Hilft ein Muster, eine Library oder ein
Tooling-Befund im konkreten Entwurfs- und Entwicklungsalltag? Die
**Systementwicklung** fragt: Verbessert eine Regel, Quelle oder Struktur das
wiederverwendbare Repro? Ein Auftrag kann beides berühren, darf die Antworten
aber nicht vermischen. Im Befund stehen deshalb Nutzungsebene, Evidenz und
Abnahme getrennt.

Ein **Test** untersucht eine einzelne KI- oder Tooling-Fähigkeit in einem
isolierten, reversiblen Rahmen. Er erzeugt Erkenntnisse, aber keinen neuen
Standard.

**Systementwicklung** liegt vor, sobald eine Regel, ein Baustein oder eine
Struktur als Teil des Base Templates oder eines Projektkits übernommen werden
soll. Dafür braucht es eine menschliche Entscheidung und die dokumentierte
Evaluation.

### Voraussetzungen für einen Test

Menschen müssen vor Beginn erkennen können:

- welche eine Frage geprüft wird,
- welcher Kontext und welches Tool verwendet werden,
- woran ein Ergebnis gemessen wird,
- wo der Test stattfindet und was ausdrücklich nicht verändert werden darf,
- wer das Ergebnis bewertet und wann der Test endet.

Der Zweck dieser Angaben ist nicht zusätzliche Bürokratie. Sie verhindern,
dass Dritte aus einem plausiblen KI-Ergebnis unbemerkt eine Regel oder eine
Freigabe ableiten.

Die vollständige Testkarte steht in der
[Operations-Checkliste](../docs/operations/checklists.md).
Die Wiki erklärt die Bedeutung; die operative Karte bleibt unter `docs/`.

## Arbeitsrollen

Die verbindlichen Rollen, ihre Prüffoki und ihre konkreten Bedürfnisse an die
Vermittlung stehen im Governance-Artefakt [Rollen und User
Stories](../docs/governance/role-needs-and-user-stories.md). Die Wiki erklärt
hier nur die Anwendung: Eine Rolle fokussiert Perspektive und Output, verleiht
aber keine Entscheidungsbefugnis. Bei eindeutigen Routineaufträgen darf der
Agent sie aus Gegenstand und Aktion ableiten und im Befund nennen; bei
unklaren oder folgenreichen Aufträgen bleibt die Analyse neutral, bis die
Perspektive geklärt ist.

Bei neuen Anforderungen, Tooling-Wünschen oder Wiki-Strukturänderungen wird
`Review` zusätzlich technisch, agentisch und informationsarchitektonisch
angewendet: Zielpassung, Machbarkeit, Toolgrenzen, Wissensvermittlung,
Leanheit und Designer-Praxistauglichkeit werden aktiv gegengeprüft. Die
verbindlichen Bedürfnisse und Prüffoki stehen in der Governance-Quelle.

## Wie Entwicklung gesteuert wird

Ein Agent darf innerhalb bestätigter Regeln arbeiten. Sobald eine neue Regel,
eine Ausnahme, eine unklare Quelle oder eine weitreichende Änderung entsteht,
legt er einen Entscheidungsbefund vor. Menschen entscheiden über Ziel,
Priorität, Ausnahmen und Freigaben.

Das bedeutet nicht, dass jeder Arbeitsschritt freigegeben werden muss. Die
menschliche Kontrolle konzentriert sich auf die Punkte, an denen fachliche
Verantwortung oder Risiko tatsächlich wechseln.

Der Agent führt diese Gegenprüfung ebenfalls aktiv durch. Er weist kurz darauf
hin, wenn eine Idee redundant, überdimensioniert, nicht operationalisierbar
oder für den aktuellen Reifegrad nicht erforderlich ist. Zustimmung allein
setzt daher keine neue Ebene oder Datei in Gang.

Bei unstrukturierten Aufträgen wird zuerst `PROMPT` verwendet. Der Agent zeigt
verständlich, was er tun würde und was nicht. Erst `AUSFÜHREN` startet die
bestätigte Aktion; technische Kennungen müssen nicht vom Menschen kopiert
werden.

Erkennt der Agent dabei ein wiederverwendbares Muster, kennzeichnet er es als
`Regelkandidat`. Bei Unsicherheit fragt er, ob daraus eine verbindliche Regel
werden soll. Ohne Zustimmung bleibt es ein Befund oder Vorschlag. Das Codewort
`REGEL SETZEN` ist die eindeutige menschliche Anweisung zur Überführung in die
Steuerungsdateien. Eine Übersicht der Befehle steht in der
[Schnellsteuerung](quick-controls.md).

## Was Menschen bei einer Änderung prüfen sollten

- Ist das Ziel verständlich und der Umfang angemessen begrenzt?
- Beruht die Arbeit auf den richtigen Quellen und einer nachvollziehbaren
  Entscheidung?
- Wird etwas wiederverwendet, variiert oder neu angelegt – und ist das
  begründet?
- Gibt es eine Ausnahme, eine neue Regel oder eine Auswirkung, die Freigabe
  braucht?
- Ist der sichtbare bzw. fachliche Erfolg gegen die vereinbarte Abnahme
  geprüft?

## Wie die Artefakte zusammenarbeiten

| Frage | Primärer Ort |
|---|---|
| „Was bedeutet das für das Projekt?“ | diese Wiki |
| „Welche Regel gilt genau?“ | [Base Template](../docs/governance/base-template.md) oder fachliches Dokument unter `docs/` |
| „Warum wurde das entschieden?“ | [Decision Log](../docs/governance/decisions.md) |
| „Wie formuliere ich einen Auftrag?“ | [Prompting Guide](../docs/operations/prompting-guide.md) |
| „Welches Werkzeug verwenden wir?“ | [Tooling Map](../docs/tooling/tooling-map.md) |
| „Wie bewerte ich einen Baustein mit KI-Unterstützung?“ | [Qualität gestalten – mit KI-Tooling als Unterstützung](quality-and-ai-tooling.md) |
| „Wie wird aus Praxiserfahrung ein besseres Werkzeug?“ | [System entwickeln und aus der Praxis lernen](system-development-and-learning.md) |
| „Welcher Kontext gehört nach Figma, ins Repository oder in den Code?“ | [Figma als Kontext für Qualitätsarbeit](figma-context-and-handoff.md) |

So bleibt die Wiki eine Vermittlungs- und Bewertungsoberfläche, während die
operative Dokumentation ihre Funktion als präzise Arbeitsgrundlage behält.
