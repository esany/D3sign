# S2 – Read-only-Variablenbefund am Toggle

## Status und Transparenz

Dies ist ein begrenzter Read-only-Test an einem konkreten Figma-Node. Er
dokumentiert den tatsächlichen Tooloutput, ersetzt keine fachliche Abnahme und
ändert weder Figma noch Repository-Strukturen außerhalb dieses Nachweises.

| Feld | Befund |
|---|---|
| Nutzungsebene | `Systementwicklung` mit fachlicher Nutzung als getrennte Wirkungsebene |
| Modus | `Pilot` / read-only |
| Rolle | `Design`, `Development` und `Review` |
| Quelle | Figma-Datei `dW1nRf8fNQ0890eyHKO0BT`, Node `155:61945` |
| Capability | `mcp__codex_apps__figma_get_variable_defs` |
| Toolstatus | `confirmed` für diesen Abruf |
| Automatisch ausgeführt | Variablen-Definitionsabruf und Rohbefunddokumentation |
| Nicht ausgeführt | keine Figma-Änderung, kein Screenshot, kein Design-Context, keine Variantenauflistung |
| Menschlich zu entscheiden | fachliche Passung, Property-/Variantenbezug und Collection-/Mode-Zuordnung |

## 1. Tatsächlich zurückgegebene Definitionen

| Sichtbare Definition | Rückgabewert | Opazität | Befundstatus |
|---|---|---:|---|
| `toggle/themed/handle` | `#001e50` | 100 % | sichtbar |
| `Drop Shadow/2` | `Effect(type: DROP_SHADOW, color: #2727271A, offset: (0, 2), radius: 4, spread: 0)` | ca. 10,2 % im Schattenfarbwert | sichtbar; Effektdefinition |
| `toggle/themed/bg` | `#e5e8ef` | 100 % | sichtbar |
| `toggle/themed/bg-hover` | `#bcc5d91a` | ca. 10,2 % | sichtbar |
| `toggle/themed/handle-disabled` | `#6a767d` | 100 % | sichtbar |
| `toggle/themed/bg-disabled` | `#dfe4e8` | 100 % | sichtbar |
| `primary/white` | `#ffffff` | 100 % | sichtbar |

Die Opazitätsangaben sind aus dem Alpha-Byte `1A` abgeleitet; der
maßgebliche Rohbefund bleibt der vom Tool zurückgegebene Wert.

## 2. Fachlich belegbar

Am geprüften Node sind Definitionen für folgende Toggle-nahe Rollen sichtbar:

- themed Handle;
- themed Hintergrund;
- themed Hover-Hintergrund;
- disabled Handle;
- disabled Hintergrund;
- eine weiße Definition `primary/white`;
- ein Drop-Shadow-Effekt.

Damit lässt sich prüfen, ob der Hauptknoten grundsätzlich Definitionen für
Track-/Handle-nahe Rollen trägt und welche aufgelösten Farbwerte der Abruf
liefert.

## 3. Fachlich noch nicht belegbar

Der Abruf liefert eine Liste sichtbarer Definitionen, aber keine vollständige
Beziehung zwischen Definition und konkreter Component-Property. Deshalb ist
aus diesem Ergebnis allein nicht sicher ableitbar:

- welche Definition an welchem Variant-Node gebunden ist;
- welcher Wert zu `Active`, `Enabled`, `Off` oder `Hover` gehört;
- ob `toggle/themed/*` aus der erwarteten Collection oder einem bestimmten Mode
  stammt;
- ob `primary/white` tatsächlich am Handle verwendet wird oder nur im geprüften
  Node-Kontext sichtbar ist;
- ob `bg-inactive`, `handle-inactive` oder andere Definitionen in der Datei
  existieren, aber am geprüften Node nicht zurückgegeben wurden;
- ob die aktuelle Zuordnung fachlich zum vorgesehenen Theming-Konzept passt.

Das Fehlen einer Definition in diesem Abruf bedeutet nur: Sie wurde für den
geprüften Node nicht zurückgegeben. Es bedeutet nicht, dass sie in der Datei
insgesamt nicht existiert.

## 4. Bezug zum S1-Vertrag

```yaml
evidence_packet:
  evidence_id: ep-toggle-variable-read-2026-10-20
  request_id: wr-toggle-variable-read-2026-10-20
  source: "Figma dW1nRf8fNQ0890eyHKO0BT / node 155:61945"
  capability_id: figma.read.variable_defs.node
  scope_read: "ein konkreter Toggle-Hauptknoten"
  evidence_type: E2
  observations:
    - "sieben sichtbare Definitionen bzw. Effekte zurückgegeben"
    - "toggle/themed/bg-hover enthält den Alpha-Wert 1A"
  omissions:
    - "keine Property-/Variant-Zuordnung"
    - "keine Collection-/Mode-Information"
    - "keine fachliche Theming-Abnahme"
  completeness: partial
  tool_status: confirmed
  data_class: freigegeben
```

## 5. Ergebnis und nächster Schritt

**Ergebnis:** Der read-only-Variablenabruf funktioniert für den konkreten
Hauptknoten und liefert verwertbare Rohwerte. Für eine fachliche Aussage über
Zustände, Varianten und Theming reicht der Abruf allein noch nicht.

**Genau ein nächster Schritt:** Die relevanten Variant-Nodes des Toggles
gezielt einzeln prüfen und dabei die Property-/Variant-Zuordnung sowie die
Collection-/Mode-Evidenz getrennt nachweisen.
