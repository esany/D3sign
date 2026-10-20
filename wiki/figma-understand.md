# Qualitätskontext aus Figma

## Welche Frage beantwortet diese Seite?

„Welchen sichtbaren Kontext aus Figma brauche ich für eine Qualitätsentscheidung
oder eine Umsetzung?“ Der Zweck ist nicht, möglichst viele Figma-Daten zu
sammeln, sondern die für die Qualitätsfrage relevante Bedeutung sichtbar zu
machen.

## Vom Anliegen zum belastbaren Kontext

1. **Gestaltungsfrage benennen.** Zum Beispiel: „Welche Zustände braucht diese
   Komponente, damit ihr Verhalten verständlich bleibt?“
2. **Quelle und Grenze bestimmen.** Das konkrete Arbeitsobjekt wird benannt:
   File, Page, Section, Frame, Component, Instance oder Node. Ein ausdrücklicher
   Nicht-Scope begrenzt die Abfrage.
3. **Sichtbares erfassen.** Varianten, Zustände, Eigenschaften, Variablen oder
   visuelle Annotationen werden nur im bestätigten Umfang ausgelesen.
4. **Bedeutung einordnen.** Design entscheidet, was davon für Nutzung,
   Hierarchie, Verhalten und Zugänglichkeit relevant ist. Ein Name oder Wert
   allein beweist keine Absicht.

Ein bloßer File-Link kann für Datei- oder Library-Fragen genügen. Für eine
belastbare Qualitätsbewertung ist meistens ein konkreteres Arbeitsobjekt
hilfreicher, etwa eine Section, ein Frame, eine Component oder Instance. Für
visuelle Bewertungen ist ein Screenshot die bevorzugte Evidenzquelle; für
Strukturfragen können Node-Kontext, Properties, Variablen oder Metadaten
passender sein.

## Was Menschen entscheiden – was das Werkzeug beiträgt

| Menschen | Figma / Agent |
|---|---|
| Zweck, Wirkung, Priorität und akzeptierbare Abweichung | findet den begrenzten Kontext und macht sichtbare Struktur transparent |
| ob ein Befund für Gestaltung oder Übergabe genügt | nennt Funktion, tatsächlichen Scope sowie nicht sichtbare Bereiche |
| ob eine Abweichung übernommen, geklärt oder verworfen wird | trennt sichtbare Evidenz, Unsicherheit und Tooling-Grenze |

Die konkrete Funktionswahl muss ein Mensch nicht vorab liefern. Notwendig sind
hingegen eine fachliche Frage, bekannte Quellen, ein Umfang und ein erkennbares
Ergebnis. Wenn die Quelle zu grob ist, muss der Agent die benötigte
Nachschärfung benennen, statt aus einem unpassenden Ausschnitt eine
Qualitätsaussage abzuleiten.

## Was hier nicht entschieden wird

Diese Seite setzt keine Tokens, Komponentenstandards oder Design-to-Code-
Annahmen. Bei einer Übernahme zwischen Dateien muss vor der Toolwahl geklärt
sein, ob eine lokale Kopie, verknüpfte Instanz, ein Verschieben oder eine
Rekonstruktion gemeint ist. Die verbindliche Abgrenzung steht in der
[Figma-MCP-Tooling-Dokumentation](../docs/tooling/figma-mcp-tooling.md).

**Nächster Schritt:** Wenn die Bedeutung geklärt ist, die benötigten
Informationen für Development über [Qualität übergeben und
abnehmen](figma-handoff.md) zusammenstellen.
