# Evaluation und Review

## Warum wir prüfen

Die Dokumentation und Steuerung sollen nicht nur vollständig wirken. Sie
sollen im Projektalltag Entscheidungen erleichtern, Orientierung geben und
Gestaltung sowie Entwicklung sinnvoll verbinden. Deshalb wird nach relevanten
Änderungen geprüft, ob das System weiterhin verständlich, schlank und
anwendbar ist.

## Was geprüft wird

| Perspektive | Leitfrage |
|---|---|
| Design Ops | Sind Rollen, Quellen, Entscheidungen, Wiederverwendung und Tool-Einsatz nachvollziehbar gesteuert? |
| Lean und operativ | Hilft die Struktur bei einer konkreten Handlung, oder erzeugt sie nur zusätzliche Dokumentation? |
| Menschliches Verständnis | Können Beteiligte Zweck, aktuellen Stand, Entscheidungen, offene Fragen und nächste Schritte schnell einordnen? |
| Gestalterischer Arbeitsprozess | Ist erkennbar, was eine Änderung für Nutzung, Gestaltung und die eigene nächste Entscheidung bedeutet? |
| Automatik und Kontrolle | Ist eindeutig, was automatisch geschieht und was der Mensch steuert, prüft oder freigibt? |
| Selbsterklärung | Kann eine dritte Person Auftrag und Ergebnis ohne Chat-Verlauf nachvollziehen? |

Die verbindlichen menschenzentrierten Kriterien stehen im [Evaluation
Framework](../docs/governance/evaluation-framework.md) und die ausführbare
Prüfung in der [Wiki-Checkliste](../docs/operations/checklists.md). Rollenbezogene
Bedürfnisse und User Stories stehen im Governance-Artefakt [Rollen und User
Stories](../docs/governance/role-needs-and-user-stories.md).

## Wann ein Review stattfindet

- nach einer folgenreichen Entscheidung, Ausnahme oder neuen Regel
- nach einer Strukturänderung
- vor dem Abschluss eines Piloten oder der Übernahme eines Standards
- bei einem regelmäßigen Projekt-Review

## Was aus einem Befund folgt

Ein Befund löst nicht automatisch eine neue Iteration aus. Bevor das System
verändert wird, wird sichtbar entschieden, ob etwas jetzt einen konkreten
Nutzen für die Arbeit bringt, erst in einem kleinen Pilot geprüft werden soll,
bewusst erhalten bleibt, im aktuellen Reifegrad nicht relevant ist oder
verworfen wird. So bleibt Entwicklung auf Erkenntnisse und reale
Arbeitsbedürfnisse gerichtet statt auf bloße Vollständigkeit.

Die verbindliche Einordnung von Nutzen, Aufwand, Nichtstun und Stoppkriterium
steht in [D-029](../docs/governance/decisions.md) sowie im
[Evaluation Framework](../docs/governance/evaluation-framework.md).

## Routinemäßige Prüfung der Informationsarchitektur

**Aktiver Steuerbefehl:** `WIKI PRÜFEN`

Der Befehl soll eine wiederkehrende, begrenzte Prüfung des Wiki-Schnitts
auslösen. Er bewertet nicht die fachliche Richtigkeit des Base Templates,
sondern die Vermittlung für Menschen:

- beantwortet jede Seite eine klar erkennbare Frage?
- sind Themen eindeutig geschnitten und Überschneidungen begrenzt?
- sind Status, Quellen, offene Punkte und nächste Handlung auffindbar?
- sind automatische Schritte, menschliche Prüfung und Freigabe getrennt?
- führt die Seite ohne Chat-Kontext verständlich weiter?
- erzeugen Struktur oder Text vermeidbare kognitive Last?

Das Ergebnis besteht aus einem kurzen Gesamtbefund, einer seitenweisen
Bewertung, höchstens einem kleinen Anpassungsvorschlag je Befund und einer
Linkprüfung. Neue Dateien oder verbindliche Regeln entstehen daraus nicht
automatisch. Die operative Prüfliste steht in der
[Menschenzentrierten Wiki-Prüfung](../docs/operations/checklists.md).

### Aktueller IA-Review

| Bereich | Befund | Lean-Folge |
|---|---|---|
| Seitenschnitt | Die Wiki trennt nun Qualitätsarbeit mit KI-Unterstützung von Systementwicklung und Lessons Learned; Figma ist ein nachgeordneter Kontextweg. | Keine weitere Bereichs- oder Toolseite ohne eigenständige menschliche Frage. |
| Vermittlung | Einstieg ohne Vorwissen beginnt mit den zwei Arbeitsanliegen statt mit Dateien oder Werkzeugen. | Erst am realen Fall mit Design, Development und Review gegenlesen. |
| Transparenz | Automatik, menschliche Kontrolle, Status und Quellen sind getrennt beschrieben. | Keine neue Regel ableiten. |
| Kognitive Last | Qualitätsdimensionen, Figma-Kontext, Übergabe und Systemlernen sind getrennt; verbindliche Details bleiben verlinkt. | Neue Inhalte nur bei eindeutigem Praxisbedarf ergänzen. |
| Verknüpfungen | Wiki-Links sind geprüft: relative Dateien, Tabellenlinks und Abschnittsanker. | Bei einem Fehler zuerst Linkziel korrigieren; keinen inhaltlichen Ersatztext einfügen. |

Gesamtstatus: **weitgehend erfüllt; die Praxisverständlichkeit muss noch mit
einer dritten Person geprüft werden**.

## Kurzer Wiki-Qualitätscheck

Vor einer Veröffentlichung oder strukturellen Änderung werden fünf Fragen mit
`ja` oder `nein` beantwortet:

| Prüffrage | Mindestkriterium |
|---|---|
| Zweck | Die Seite beantwortet eine erkennbare menschliche Frage. |
| Orientierung | Status, offene Punkte und nächster prüfbarer Schritt sind sichtbar. |
| Arbeitsteilung | Automatik, menschliche Prüfung und Freigabe sind getrennt benannt. |
| Nachvollziehbarkeit | Aussagen verweisen auf ihre verbindliche Quelle oder sind als Befund/Entwurf markiert. |
| Last | Keine Regel wird dupliziert; Abschnitte und Links führen ohne Chat-Kontext weiter. |

Bei einem `nein` wird die Seite nicht als abgeschlossen markiert. Zuerst wird
die kleinste redaktionelle Korrektur vorgenommen; eine neue Regel oder Datei
entsteht daraus nicht automatisch.

## Was Menschen aus einem Befund mitnehmen sollen

### Lesereihenfolge eines Befunds

Ein Befund wird immer von oben nach unten gelesen:

1. **Evidenz und Tooling:** Was wurde tatsächlich erreicht und mit welcher
   Funktion geprüft?
2. **Grenzen:** Was war nicht sichtbar oder nicht bestimmbar?
3. **Fachliche Einordnung:** Welche Aussage ist durch die Evidenz gedeckt?
4. **Menschliche Entscheidung:** Was wird übernommen, verworfen oder zur
   Klärung vorgelegt?
5. **Nächster Schritt:** genau eine begrenzte, prüfbare Anschlussaktion.

Ein eingeschränktes Tooling-Ergebnis darf deshalb nicht als fachlicher Mangel
gelesen werden. Nicht sichtbare Aspekte bleiben ausdrücklich `nicht bewertet`.

Ein Review beantwortet kurz:

1. Was wurde geprüft?
2. Was funktioniert bereits?
3. Was ist noch unklar oder riskant?
4. Was bedeutet das für die gestalterische Arbeit?
5. Was ist die nächste konkrete Entscheidung oder Prüfung?

Zusätzlich muss erkennbar sein, welche Teile aus Regeln automatisch entstanden
sind und an welcher Stelle menschliche Verantwortung beginnt.

Die verbindlichen Kriterien und die aktuellen Befunde stehen im
[Evaluation Framework](../docs/governance/evaluation-framework.md) und im
[Evaluation Log](../docs/governance/evaluation-log.md).
