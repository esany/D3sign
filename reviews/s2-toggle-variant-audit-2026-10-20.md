# S2 – Variantenaudit des Toggle Switch

## Status und Transparenz

Dieser Befund ergänzt den vorherigen Variablenabruf um die tatsächlich
vorhandene Variantstruktur und die je Variante zurückgegebenen Definitionen.
Er ist ein begrenzter, reversibler Read-only-Pilot. Er ändert weder Figma noch
den bestehenden Komponenten- oder Tokenvertrag und ersetzt keine fachliche
Bewertung durch den Designer.

| Feld | Befund |
|---|---|
| Nutzungsebene | `Systementwicklung` mit getrennter fachlicher Wirkung |
| Modus | `Pilot` / read-only |
| Rollen | `Design`, `Development`, `Review` |
| Quelle | Figma-Datei `dW1nRf8fNQ0890eyHKO0BT`, Component Set `155:61945` |
| Struktur-Funktion | `mcp__codex_apps__figma_get_metadata` und `mcp__codex_apps__figma_get_context_for_code_connect` |
| Variablen-Funktion | `mcp__codex_apps__figma_get_variable_defs` je Variant-Node |
| Toolstatus | `confirmed` für die konkreten Abrufe |
| Ergebnisstatus | `partial`; Collection-/Mode-Kontext und fachliche Passfähigkeit bleiben offen |
| Nicht ausgeführt | keine Figma-Änderung, kein Screenshot, keine Accessibility-Abnahme, keine automatische Pass-/Fail-Bewertung |

**Mantra:**

> **Zustand sehen → visuelle Rolle verstehen → Token-Zuweisung prüfen → Lücke bewerten → Entscheidung treffen.**

## 1. Fachliche Frage und Erkenntnislücke

**Frage:** Welche realen Toggle-Zustände existieren, welche Definitionen sind
je Zustand sichtbar, und reicht dieser Nachweis für eine fachliche Bewertung
der aktuellen Variablenzuweisung?

**Erkenntnislücke vor diesem Lauf:** Der vorherige Befund zeigte Werte am
Hauptknoten, aber noch keine belastbare Verbindung von

```text
Variantenzustand → konkreter Variant-Node → zurückgegebene Definition
```

Diese erste Verbindung ist jetzt hergestellt. Nicht hergestellt ist die
weitere Verbindung zu Collection und Mode sowie zu einer konkreten
Figma-Property von Track oder Handle.

## 2. Tatsächliche Variantstruktur

Das Component Set `Atoms / Toggle Switch` besitzt genau diese drei Achsen:

| Achse | Tatsächliche Optionen |
|---|---|
| `Active` | `on`, `off` |
| `Enabled` | `off`, `on` |
| `Hover` | `off`, `on` |

Die Struktur enthält sechs reale Varianten. Weitere Kombinationen oder Namen
werden nicht ergänzt.

| Variant-Node | `Active` | `Enabled` | `Hover` |
|---|---|---|---|
| `155:61946` | `on` | `on` | `off` |
| `155:61949` | `on` | `on` | `on` |
| `155:61953` | `on` | `off` | `off` |
| `155:61956` | `off` | `on` | `off` |
| `155:61959` | `off` | `on` | `on` |
| `155:61963` | `off` | `off` | `off` |

Die Variantennamen stammen aus der Figma-Struktur. Sie sind keine
semantische Neubenennung und keine Aussage darüber, ob `Enabled=off` fachlich
als „disabled“ bezeichnet werden soll.

## 3. Direkter Farb- und Variablenbefund

Die folgenden Werte wurden je Variant-Node einzeln mit
`figma_get_variable_defs` ausgelesen. Die Farbfelder machen den sichtbaren Wert
direkt wahrnehmbar; der Hexwert ist die technische Ergänzung.

| Zustand | Element-/Rollenhinweis aus Definition | Aktuelle Definition | Sichtbarer Wert | Opazität | Evidenz |
|---|---|---|---|---:|---|
| `Active=on`, `Enabled=on`, `Hover=off` | Handle-nahe Definition | `toggle/themed/handle` | <span aria-label="#001e50" style="display:inline-block;width:1rem;height:1rem;background:#001e50;border:1px solid #777"></span> `#001e50` | 100 % | am Variant-Node zurückgegeben; konkrete Property nicht aufgelöst |
| `Active=on`, `Enabled=on`, `Hover=off` | Hintergrund-nahe Definition | `toggle/themed/bg` | <span aria-label="#e5e8ef" style="display:inline-block;width:1rem;height:1rem;background:#e5e8ef;border:1px solid #777"></span> `#e5e8ef` | 100 % | am Variant-Node zurückgegeben; konkrete Property nicht aufgelöst |
| `Active=on`, `Enabled=on`, `Hover=on` | Hover-nahe Definition | `toggle/themed/bg-hover` | <span aria-label="#bcc5d9 mit Alpha 1A" style="display:inline-block;width:1rem;height:1rem;background:#bcc5d9;border:1px solid #777"></span> `#bcc5d91a` | ca. 10,2 % | am Variant-Node zurückgegeben; konkrete Property nicht aufgelöst |
| `Active=on`, `Enabled=on`, `Hover=on` | Handle-nahe Definition | `toggle/themed/handle` | <span aria-label="#001e50" style="display:inline-block;width:1rem;height:1rem;background:#001e50;border:1px solid #777"></span> `#001e50` | 100 % | am Variant-Node zurückgegeben; konkrete Property nicht aufgelöst |
| `Active=on`, `Enabled=on`, `Hover=on` | Hintergrund-nahe Definition | `toggle/themed/bg` | <span aria-label="#e5e8ef" style="display:inline-block;width:1rem;height:1rem;background:#e5e8ef;border:1px solid #777"></span> `#e5e8ef` | 100 % | am Variant-Node zurückgegeben; konkrete Property nicht aufgelöst |
| `Active=on`, `Enabled=off`, `Hover=off` | Disabled-Handle-nahe Definition | `toggle/themed/handle-disabled` | <span aria-label="#6a767d" style="display:inline-block;width:1rem;height:1rem;background:#6a767d;border:1px solid #777"></span> `#6a767d` | 100 % | am Variant-Node zurückgegeben; konkrete Property nicht aufgelöst |
| `Active=on`, `Enabled=off`, `Hover=off` | Disabled-Hintergrund-nahe Definition | `toggle/themed/bg-disabled` | <span aria-label="#dfe4e8" style="display:inline-block;width:1rem;height:1rem;background:#dfe4e8;border:1px solid #777"></span> `#dfe4e8` | 100 % | am Variant-Node zurückgegeben; konkrete Property nicht aufgelöst |
| `Active=off`, `Enabled=on`, `Hover=off` | weiße Definition | `primary/white` | <span aria-label="#ffffff" style="display:inline-block;width:1rem;height:1rem;background:#ffffff;border:1px solid #777"></span> `#ffffff` | 100 % | am Variant-Node zurückgegeben; konkrete Property nicht aufgelöst |
| `Active=off`, `Enabled=on`, `Hover=off` | Hintergrund-nahe Definition | `toggle/themed/bg` | <span aria-label="#e5e8ef" style="display:inline-block;width:1rem;height:1rem;background:#e5e8ef;border:1px solid #777"></span> `#e5e8ef` | 100 % | am Variant-Node zurückgegeben; konkrete Property nicht aufgelöst |
| `Active=off`, `Enabled=on`, `Hover=on` | Hover-nahe Definition | `toggle/themed/bg-hover` | <span aria-label="#bcc5d9 mit Alpha 1A" style="display:inline-block;width:1rem;height:1rem;background:#bcc5d9;border:1px solid #777"></span> `#bcc5d91a` | ca. 10,2 % | am Variant-Node zurückgegeben; konkrete Property nicht aufgelöst |
| `Active=off`, `Enabled=on`, `Hover=on` | weiße Definition | `primary/white` | <span aria-label="#ffffff" style="display:inline-block;width:1rem;height:1rem;background:#ffffff;border:1px solid #777"></span> `#ffffff` | 100 % | am Variant-Node zurückgegeben; konkrete Property nicht aufgelöst |
| `Active=off`, `Enabled=on`, `Hover=on` | Hintergrund-nahe Definition | `toggle/themed/bg` | <span aria-label="#e5e8ef" style="display:inline-block;width:1rem;height:1rem;background:#e5e8ef;border:1px solid #777"></span> `#e5e8ef` | 100 % | am Variant-Node zurückgegeben; konkrete Property nicht aufgelöst |
| `Active=off`, `Enabled=off`, `Hover=off` | Disabled-Handle-nahe Definition | `toggle/themed/handle-disabled` | <span aria-label="#6a767d" style="display:inline-block;width:1rem;height:1rem;background:#6a767d;border:1px solid #777"></span> `#6a767d` | 100 % | am Variant-Node zurückgegeben; konkrete Property nicht aufgelöst |
| `Active=off`, `Enabled=off`, `Hover=off` | Disabled-Hintergrund-nahe Definition | `toggle/themed/bg-disabled` | <span aria-label="#dfe4e8" style="display:inline-block;width:1rem;height:1rem;background:#dfe4e8;border:1px solid #777"></span> `#dfe4e8` | 100 % | am Variant-Node zurückgegeben; konkrete Property nicht aufgelöst |

Zusätzlich ist an allen sechs Variant-Nodes derselbe Effekt sichtbar:

| Definition | Wert |
|---|---|
| `Drop Shadow/2` | Schattenfarbe `#2727271A`, Offset `(0, 2)`, Radius `4`, Spread `0` |

Die Tabelle zeigt, was Figma am jeweiligen Node zurückgibt. Sie behauptet nicht,
dass der Name bereits die fachlich richtige Rolle oder die Collection des
Elements beweist.

## 4. Was ist nachgewiesen, was bleibt offen?

### Nachgewiesen

- Das Component Set besitzt die drei genannten Variant-Achsen und genau sechs
  reale Variant-Nodes.
- Die sechs Nodes geben unterschiedliche, zustandsabhängige Definitionen für
  themed, Hover, disabled-nahe und weiße Farbrollen zurück.
- Die aufgelösten Werte einschließlich Hex und Alpha sind je Node sichtbar.
- Der Drop Shadow ist über alle sechs Nodes gleich zurückgegeben.

### Nicht nachgewiesen

- Welche konkrete Figma-Property jeweils Track, Handle oder ein anderes
  Descendant-Element trägt.
- In welcher Collection und welchem Mode jede Definition liegt.
- Ob `Enabled=off` fachlich als disabled bezeichnet werden soll.
- Ob die aktuelle Zuweisung im bestehenden semantischen Vertrag passfähig ist.
- Accessibility, Kontrast, Interaktionswirkung oder Nutzerverständlichkeit.

Insbesondere wird aus dem Namen `toggle/themed/...` keine Collection- oder
Mode-Zuordnung abgeleitet. Ebenso wird `primary/white` nicht automatisch als
Handle-Zuweisung bewertet; die konkrete Property-Bindung ist in diesem Lauf
nicht sichtbar.

## 5. Systemische Einordnung und Arbeitsteilung

| Beteiligter | Liefert oder entscheidet | Grundlage |
|---|---|---|
| Figma | reale Variant-Achsen, Node-IDs, zurückgegebene Definitionen und Werte | tatsächlicher Read-only-Output |
| Assistenz | ordnet Zustände, Werte, Evidenz und Grenzen lesbar | bestehender S1-Vertrag, Semantic Model und Tooling Map |
| Bestehender Vertrag | liefert Begriffe, Rollen und Prüfreihenfolge | bestehende `docs/`-Quellen; keine neue Regel in diesem Lauf |
| Designer:in | bewertet Bedeutung, Passfähigkeit, Priorität und Konsequenz | sichtbarer Zustand, Wert, bestehende semantische Rollen und eigene Absicht |
| Review | prüft Beleg, Scope und Trennung von Beobachtung und Ableitung | EvidencePacket/Finding-Logik |
| Repository | hält den Befund außerhalb des Chats auffindbar | diese Datei und E-073 |

Der Lauf unterstützt den Designer beim Wiedererkennen und Vergleichen. Er
entscheidet nicht, ob ein Mapping geändert werden muss.

## 6. Befund nach dem S1-Vertrag

### `EvidencePacket`

- **Quelle:** Figma-Datei `dW1nRf8fNQ0890eyHKO0BT`, Component Set `155:61945`
  und sechs Variant-Nodes.
- **Capabilities:** `figma_get_metadata`,
  `figma_get_context_for_code_connect`, `figma_get_variable_defs`.
- **Evidenztyp:** `E1` für Variantstruktur, `E2` für Definitionen am konkreten
  Variant-Node.
- **Beobachtung:** Drei Achsen, sechs Nodes und die in Abschnitt 3 sichtbaren
  Definitionen/Werte wurden zurückgegeben.
- **Auslassungen:** keine Property-/Descendant-Bindung, keine Collection-/Mode-
  Information, kein Screenshot, keine fachliche Abnahme.
- **Status:** `confirmed` für die Abrufe, `partial` für die Fachfrage.

### `Finding`

- **Beobachtung:** Die reale Toggle-Struktur besteht aus sechs benannten
  Kombinationen der Achsen `Active`, `Enabled` und `Hover`. Ihre Definitionen
  wechseln nachvollziehbar zwischen themed-, Hover-, disabled-nahen und weißen
  Werten.
- **Ableitung:** Der Toggle besitzt einen ausreichend konkreten strukturellen
  Vergleichsgegenstand für die nächste Designerbewertung. Eine semantische
  oder technische Korrektur folgt daraus nicht automatisch.
- **Auswirkung:** Der Designer kann jetzt Zustände und sichtbare Werte
  vergleichen; für die abschließende Mapping-Bewertung fehlt weiterhin die
  Nachweisführung bis zur konkreten Property und Collection/Mode-Ebene.
- **Status:** `visible` für Struktur und Werte, `derived` für die
  Vergleichbarkeit, `not_proven` für Property-/Collection-/Mode-Zuordnung und
  fachliche Passfähigkeit.
- **Optionen:** aktuelle Zuweisung fachlich prüfen; Collection-/Mode-Evidenz
  nachholen; Befund bis zu dieser Evidenz offen lassen.

### `Decision`

Es wurde keine fachliche Decision getroffen. Es wurde keine Figma-Zuweisung
geändert und keine neue Regel gesetzt.

### `RunRecord`

- **Repository-Pfad:** diese Datei und der Anschluss in E-073
- **Menschliche Beteiligung:** Der Variantenaudit war durch den bestätigten
  Prompt begrenzt; die fachliche Bewertung und jede Änderung bleiben offen.
- **Completion:** `recorded`, fachlich nicht abgeschlossen

## 7. Ein nächster menschlicher Entscheid

Soll der Designer die aktuelle Zuweisung auf Basis der jetzt sichtbaren sechs
Zustände und Farbwerte fachlich bewerten, oder soll vor dieser Bewertung noch
gezielt Collection-/Mode- und Property-Evidenz beschafft werden?

Bis zu diesem Entscheid bleibt der Befund dokumentiert und unverbindlich.
