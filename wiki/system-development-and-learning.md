# System entwickeln und aus der Praxis lernen

## Worum es hier geht

Dieses Gebiet erklärt, wie das System als praxistaugliches, möglichst
operationalisiertes, leanes und tokensparendes Werkzeug besser wird. Es richtet
sich nicht auf eine einzelne Gestaltung, sondern auf Regeln, Wissensquellen,
Tooling und wiederverwendbare Erkenntnisse aus der Arbeit.

## Der kleine Lernkreislauf

```text
Praxisbeobachtung → begrenzter Befund → menschliche Bewertung → Evaluation →
gegebenenfalls Übernahme
```

Eine Beobachtung kann eine wiederkehrende Qualitätsfrage, eine unklare
Übergabe, fehlende Evidenz oder eine Toolgrenze sein. Sie wird nicht
automatisch zu einer Regel. D-029 verlangt eine sichtbare Einordnung:
`jetzt umsetzen`, `Pilot/Kandidat`, `bewusst bewahren`, `derzeit nicht
relevant` oder `verwerfen/ablösen`.

## Was das System liefern soll

- **Best Practice verfügbar machen:** belastbare, verlinkte Quellen so
  erschließen, dass sie eine konkrete Qualitätsentscheidung unterstützen.
- **Lessons Learned sichern:** nachvollziehbare Befunde mit Quelle, Grenze,
  Wirkung und menschlicher Bewertung sammeln.
- **Werkzeuge betriebsfähig bewerten:** Fähigkeit, Scope, Fehlerbild und
  Rückfallebene testen – nicht nur Erreichbarkeit oder Produktversprechen.
- **Aus Fundstücken lernen:** Auch nicht aufgenommene Tools, Methoden oder
  Referenzen auf übertragbare Prinzipien, Kontextaufwand, Unabhängigkeit und
  ihre passende Integrationsstufe prüfen.
- **Aufwand begrenzen:** kleinste ausreichende Prüfung, keine doppelte
  Dokumentation und keine Iteration ohne zusätzlichen Nutzen oder Evidenz.

## Neue Fundstücke einordnen

Ein Fundstück ist ein mögliches Werkzeug, eine Methode, ein Pattern oder eine
Referenz, die für das System interessant sein könnte. Die Frage lautet nicht
nur „Nehmen wir es auf?“. Auch ein ähnlicher Ansatz kann zeigen, wie Kontext
kleiner, unabhängiger oder verständlicher wird.

Die operative Bewertung unterscheidet deshalb: beobachten, Erkenntnis oder
Arbeitsmuster übernehmen, begrenzt testen, integrieren oder nur als Referenz
sichtbar halten. Das bewahrt gute Ideen, ohne jedes Fundstück in einen neuen
Prozess oder eine neue Abhängigkeit zu verwandeln. Details und die
Fundstückkarte stehen im [Workflow für neue Fundstücke](../docs/operations/workflows.md#neue-fundstucke-bewerten-und-integrieren).

Der **Status** sagt, wo ein Fundstück aktuell steht: etwa nur beobachten, als
Pilot/Kandidat prüfen oder integriert. Die **Integrationsgrade** erklären
getrennt, was daraus möglicherweise zurückfließt — zum Beispiel nur eine
Erkenntnis oder ein Referenzfall. Ein möglicher Lernwert ist daher keine
Toolfreigabe.

Gesicherte Fundstückbewertungen sind in der
[zentralen Übersicht im Evaluation Log](../docs/governance/evaluation-log.md#fundstuckbewertungen)
verlinkt. Dort zeigt jede Zeile nicht nur das Fundstück und seine Lizenz,
sondern auch Mehrwert und Risiko gegenüber dem Bestand, die entscheidenden
Kriterien, den aktuellen Integrationsrand und den konkreten Auslöser für eine
Wiederprüfung.

Der Vergleich fragt dabei nicht nur, ob zwei Werkzeuge dasselbe können. Für
jeden betroffenen Bereich wird sichtbar, was der vorhandene Weg leistet,
welche Lücke bleibt und ob das Fundstück ihn sinnvoll ergänzt, später als
Rückfallebene absichern oder nur wiederholen würde. Auch eine mögliche Paywall,
ein Anbieterwechsel oder die Wartbarkeit eines freien Tools gehören zu dieser
Einordnung. So entsteht aus einem Fundstück eine begründete Systementscheidung
statt einer bloßen Toolliste.

## Wissen übernehmen, ohne ein Tool zu übernehmen

Ein gutes externes Skill oder Plugin kann einen brauchbaren Ablauf zeigen, auch
wenn es im Projekt nicht installiert wird. Übernommen wird dann nur das
Arbeitswissen: eine kleine Aufgabe mit klarer Voraussetzung, begrenztem Lesen,
sichtbarer Schreibgrenze und einer Prüfung danach. Besonders wichtig ist die
Trennung: Was wurde aus Figma gelesen? Was folgt aus einer festen Regel? Was
ist nur ein KI-Vorschlag? Was entscheidet ein Mensch?

Ein Lint-Befund oder Score hilft beim Sortieren von Auffälligkeiten, entscheidet
aber nicht über Qualität oder Veröffentlichung. Ebenso sind Figma-Zugriff über
die normale Anmeldung und ein direkter REST-Zugriff mit persönlichem Token zwei
verschiedene Wege mit unterschiedlichen Freigaben. Die verbindliche
Detailregel steht im [Fundstück-Workflow](../docs/operations/workflows.md#ubernommenes-wissen-aus-externen-skills).

Eine eigene Wiki-Seite ist nur sinnvoll, wenn ein Befund eine relevante
Entscheidung erklärt oder später als Vergleichsfall hilft. Sonst genügt der
Evaluationseintrag; operative Regeln bleiben in `docs/`.

## Aktuelle Lessons Learned: Quelle vor Tool, Evidenzstatus vor Ableitung

Der Southleft Design Systems MCP war am 28. Juli 2026 erreichbar, lieferte bei
begrenzten Fachfragen jedoch keine passenden, quellenzuordenbaren Treffer. Die
Chat-Oberfläche scheiterte zusätzlich an einer Cloudflare-Worker-
Ressourcenbegrenzung. Für die konkrete Arbeit war das Werkzeug deshalb keine
verwendbare Evidenzquelle – ohne daraus ein Urteil über dessen mögliches
Potenzial oder über Design-System-Qualität abzuleiten.

Der Figma-/Button-Pilot zeigte denselben Befund aus einer anderen Richtung:
Ein File-Link, ein Node-Link, ein Screenshot, eine Library-Suche oder ein
generierter Designkontext sind unterschiedliche Quellen mit unterschiedlichem
Evidenzwert. Der Button war dabei nur die Testsonde. Der wichtigere Rückfluss
ist ein allgemeinerer Arbeitsvertrag für Mensch, KI und Tooling: erst die
fachliche Frage und die kleinste belastbare Quelle klären, dann das passende
Werkzeug wählen und danach den Evidenzstatus vor jeder Ableitung ausweisen.

Aus dem V3/V4-Strang kam ein zweites, praktisch wichtiges Learning hinzu:
Komponenten-Erstellung und Komponenten-Dokumentation sind unterschiedliche
Arbeitsgegenstände. Ein Figma-Komponentenpilot darf nicht in eine reine
Dokumentationsfläche kippen. Dieser Kern ist mit D-036 als bestätigte Regel
gesetzt: Komponenten erstellen, prüfen und dokumentieren müssen vor Ausführung
als Auftragsarten unterschieden werden. Für weitere Tests werden außerdem
Aufbaustufe und Generation getrennt: Die Aufbaustufe begrenzt den fachlichen
Umfang, die Generation benennt nur den konkreten Versuch. Das bleibt aktuell
Projektwissen und Regelkandidat, kein eigener Skill.

Der V5-Review hat daraus ein operatives Gate gemacht: Für reinen
Komponentenbau werden acht Tests geprüft — Auftragstyp, Komponenten-
Gegenstand, Anatomy, Varianten, Properties, Overrides, Scope und Sichtbarkeit.
Dieses Gate ist noch kein endgültiger Standard, verhindert aber im nächsten
Figma-Test genau den Drift, der V5 unbrauchbar gemacht hat.

Der Standabgleich nach E-070 verschärft den praktischen Lernpunkt: Ein
Artefakt kann technisch ein Component Set enthalten und trotzdem als
Komponentenauftrag scheitern, wenn Auftrag, Scope und Nutzungskontext
vermischen. V5 ist deshalb begrenzt verwertbar, aber nicht bestanden. Für die
Gestaltungspraxis reicht es nicht, Pilotstatus, offene Punkte und Anatomy zu
benennen; eine normale Library-Komponente muss operational lesbar machen,
wann der Baustein genutzt wird, welche Varianten unterstützt sind, was stabiler
Vertrag ist und was nur Beispiel bleibt. Erst wenn der Baustein selbst sauber
steht, wird diese Dokumentation sinnvoll.

Die praktische Konsequenz: Bei fehlender passender Evidenz Primärquellen oder
präzisere Arbeitsobjekte nutzen, die Toolgrenze sichtbar machen und erst bei
veränderter Ausgangslage begrenzt erneut testen. Das ist keine automatische
Toolfreigabe und keine neue Designregel, sondern ein Betriebsprinzip für
belastbare Wissensarbeit. Die menschliche Einordnung steht im
[Arbeitsmodell](working-model.md#evidenzbasierte-toolnutzung); die operative
Fassung steht in den
[Workflows](../docs/operations/workflows.md#arbeitsprinzipien-fur-evidenzbasierte-toolnutzung).
Nachweis und Testkriterium zum Southleft-Befund stehen in
[D-028](../docs/governance/decisions.md) und
[E-033](../docs/governance/evaluation-log.md).

## Fünf Fragen für eine schlanke KI-Unterstützung

Diese Fragen sind keine neue Regelkarte. Sie helfen, die vorhandenen Regeln
vor einer Tool- oder Strukturentscheidung kurz anzuwenden:

1. Reicht der kleinste bereits bestätigte Kontext?
2. Ist die Bedeutung geklärt, bevor über Darstellung oder Technik gesprochen
   wird?
3. Stützt sich der Befund auf direkte Evidenz statt auf Vermutung?
4. Löst die vorgeschlagene Struktur einen wiederkehrenden Bedarf?
5. Ist die Frage einschließlich notwendiger Validierung beantwortet — dann
   kann die Arbeit enden?

Die Antworten führen nicht zu einem neuen Pflichtprozess. Sie verweisen auf
die bestehenden Arbeitsprinzipien und helfen besonders dabei, unnötige
Inventare, Toolaufrufe, Dokumentation und Regelkandidaten zu vermeiden.

Ein neuer Figma-Tooling-Test hat diese Trennung weiter konkretisiert: Zwei
Lesefunktionen mit ähnlich klingendem Zweck können unterschiedliche Ausschnitte
zeigen. Bei einer ausdrücklich verlangten Dateiübersicht wird deshalb geprüft,
welcher Lesepfad im konkreten Setup die Page-Ebene tatsächlich abdeckt. Ein
Share-Link mit Node-ID bleibt ein technischer Einstiegspunkt; er entscheidet
nicht selbst, ob die Frage die Datei, eine Page oder den Node betrifft. Der
vollständige, begrenzte Testbefund steht in
[E-063](../docs/governance/evaluation-log.md#e-063--figma-adressierungs--scope--und-page-inventar-test).

Für KI-Unterstützung wird eine Datei außerdem nur dann inventarisiert, wenn
der direkte Arbeitskontext für die Frage nicht genügt oder eine Übersicht
ausdrücklich verlangt ist. Ein bekannter Node mit klarer Frage wird direkt
geprüft. Erst bei diesem Inventar-Trigger wird eine Datei nicht als bloße
Liste behandelt:
Das **Strukturinventar** zeigt, was technisch sichtbar ist; das
**Systeminventar** trennt mögliche von menschlich bestätigten
Systembausteinen; das **Arbeitsinventar** benennt den kleinsten sinnvollen
nächsten Schritt. So wird ein sichtbarer Frame nicht vorschnell zur
Komponente, ein Library-Treffer nicht zur Übernahme und ein Screenshot nicht
zur fachlichen Entscheidung. Die operative Vorlage und Evidenztypen stehen in
der [Tooling Map](../docs/tooling/tooling-map.md#ki-orientiertes-figma-inventar);
der Test- und Regelkandidatenstatus in
[E-065](../docs/governance/evaluation-log.md#e-065--ki-orientiertes-figma-inventar).

## Wo weiterarbeiten

- [Arbeitsmodell](working-model.md): Ebenen, Arbeitsteilung und der Unterschied
  zwischen Test und Systementwicklung.
- [Evaluation und Review](evaluation-and-review.md): Wie Befunde geprüft und
  Priorisierungen nachvollziehbar gemacht werden.
- [Steuerung und Quellen](governance-and-sources.md): verbindliche Quelle für
  eine Regel, Entscheidung oder Tooling-Frage finden.

**Nächster Schritt:** Einen tatsächlichen Praxisbefund mit Nutzen, Grenze und
kleinstem prüfbaren Schritt in die Evaluation einbringen.
