# Schnellsteuerung für Menschen

## Worum es hier geht

Diese Seite hilft zuerst bei der Einordnung einer Arbeit und erst danach bei
der Wahl eines Befehls. Ein Befehl ist keine fachliche Entscheidung: Er löst
nur eine begrenzte, bereits geregelte Handlung aus.

## Erst die Arbeitsdimension wählen

| Wenn du gerade … | Nutzungsebene | Du steuerst | KI/Tooling darf | Beginne hier |
|---|---|---|---|---|
| einen generischen Baustein qualitativ beurteilen oder verbessern willst | Fachliche Nutzung | Qualitätsfrage, Kontext, Grenze und Abnahme | sichtbaren Kontext erfassen, Unterschiede strukturieren und Grenzen ausweisen | [Qualität gestalten – mit KI-Tooling als Unterstützung](quality-and-ai-tooling.md) |
| Figma oder KI für eine konkrete Qualitätsfrage einsetzen willst | Fachliche Nutzung | Quelle, Scope, Nicht-Scope und erwartetes Ergebnis | nur den bestätigten Kontext nutzen; keine Absicht oder Qualität erraten | [Figma als Kontext für Qualitätsarbeit](figma-context-and-handoff.md) |
| Regeln, Wissensquellen oder Tooling aus Praxisbefunden verbessern willst | Systementwicklung | Nutzen, Aufwand, kleinsten Pilot und Abbruchkriterium | Befund und Optionen strukturiert vorbereiten | [System entwickeln und aus der Praxis lernen](system-development-and-learning.md) |
| eine Regel, Ausnahme oder Übernahme verbindlich entscheiden willst | Governance | Freigabe und Geltungsbereich | Entscheidung und Quellen transparent nachweisen | `REGEL SETZEN` |
| bestätigte Inhalte nur an der zuständigen Stelle dokumentieren willst | Dokumentation | Zielquelle und gesichertes Delta | eindeutig zuordenbare Inhalte übertragen | `Status sichern` |

Fachliche Nutzung und Systementwicklung dürfen verbunden sein, ihre Befunde
und Abnahmen bleiben jedoch getrennt. Ein einzelner Toolfehler oder eine
Beobachtung löst keine Systemiteration aus.

## Passende Befehle

### Auftrag vorbereiten und ausführen

| Befehl | Wann er passt | Was er nicht entscheidet |
|---|---|---|
| `PROMPT` | Das Anliegen, die Quelle, der Scope oder die Abnahme sind noch nicht klar genug für eine Aktion. Ein ausführungsbereiter Prompt endet sichtbar mit „Mit `AUSFÜHREN` führe ich … im Modus … aus.“ | Ob die Arbeit fachliche Nutzung oder Systementwicklung ist; diese Einordnung wird im Auftrag sichtbar gemacht. |
| `AUSFÜHREN` | Als alleinstehende Nachricht: den unmittelbar zuvor bestätigten, noch nicht ausgeführten Auftrag starten. | Neue Regel, Qualitätsfreigabe, Ausnahme, Wiederholung eines erledigten Auftrags oder eine über den Auftrag hinausgehende Änderung. |

### Systementwicklung und Governance

| Befehl | Wann er passt | Was er nicht entscheidet |
|---|---|---|
| `REGEL SETZEN` | Ein benannter Regelkandidat soll nach menschlicher Freigabe verbindlich übernommen werden. | Ob aus einem Befund überhaupt ein Regelkandidat werden soll; das braucht Nutzen, Evidenz und Entscheidung. |
| `WIKI PRÜFEN` | Eine relevante Wiki-Struktur oder Vermittlung soll auf Orientierung, Rollenpassung und Last geprüft werden. | Eine neue Regel oder weitere Wiki-Struktur; die Prüfung schlägt höchstens kleine begründete Anpassungen vor. |

Die Einordnung von `jetzt umsetzen`, `Pilot/Kandidat`, `bewusst bewahren`,
`derzeit nicht relevant` oder `verwerfen/ablösen` steht verbindlich in
[D-029](../docs/governance/decisions.md). Sie verhindert Iteration allein
aus Vollständigkeitsdrang.

### Status und Dokumentation

| Befehl | Wann er passt | Was der Agent sichtbar ausweist |
|---|---|---|
| `START CHAT` | Ein neuer Chat oder eine Wiederaufnahme soll an einen passenden, anschlussfähigen Arbeitsstand anknüpfen. | Abgeleiteten oder vorläufigen Arbeitsstand, passende Quellen und offene Entscheidungen; keine Fachentscheidung oder globale Toolzusage. |
| `Status sichern` | Inhalt ist bestätigt und eindeutig einer zuständigen `docs/`-Quelle zuordenbar. | Neu gesichert, geändert, bewusst nicht übernommen und weiter offen. |

`START CHAT` nimmt den Arbeitsstand für die weitere Arbeit wieder auf;
`Status sichern` bewahrt bestätigten Stand in der zuständigen Quelle. Die
ausführbare Kurzform, Routing- und Toolinggrenzen stehen im [Prompting
Guide](../docs/operations/prompting-guide.md#start-chat--bedarfsorientierter-einstieg-pilot).

## Menschliche Kontrolle

KI und Werkzeuge unterstützen die jeweilige Arbeit, entscheiden aber nicht
über fachliche Bedeutung, Priorität, Freigabe oder die Übernahme einer Regel.
Die verbindlichen Entscheidungsrechte, Regeln und Prüfschritte stehen in
[AGENTS.md](../AGENTS.md), im [Decision Log](../docs/governance/decisions.md)
und in den verlinkten operativen Dateien.

**Nächster Schritt:** Das eigene Anliegen zunächst einer Arbeitsdimension
zuordnen und erst danach den passenden Einstieg oder Befehl wählen.
