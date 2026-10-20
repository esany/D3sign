# S2 – Designerorientierter Toggle-Befund

## Status und Transparenz

Dieser Befund ist die fachliche Aufbereitung eines begrenzten Read-only-
Abrufs. Er verwendet den bestehenden S1-Vertrag und die vorhandene semantische
Struktur. Er erzeugt keine neue Befundlogik und ersetzt keine menschliche
Designentscheidung.

**Arbeitsstand:** Historische S2-Evidenz. Dieser Befund ist kein aktueller
Arbeitsweg und kein kanonisches Auditformat; seine Beobachtungen bleiben als
Nachweis für E-073/E-074 erhalten.

| Feld | Befund |
|---|---|
| Nutzungsebene | `Systementwicklung` mit fachlicher Nutzung als getrennte Wirkungsebene |
| Modus | `Pilot` / read-only |
| Rollen | `Design`, `Development`, `Review` |
| Quelle | Figma-Datei `dW1nRf8fNQ0890eyHKO0BT`, Node `155:61945` |
| Capability | `mcp__codex_apps__figma_get_variable_defs` |
| Toolstatus | `confirmed` für diesen konkreten Abruf |
| Ergebnisstatus | `partial`; fachliche Zuordnung bleibt offen |
| Nicht ausgeführt | keine Figma-Änderung, kein Screenshot, kein Design-Context, keine Variantenauflistung |

**Mantra:**

> **Zustand sehen → visuelle Rolle verstehen → Token-Zuweisung prüfen → Lücke bewerten → Entscheidung treffen.**

## 1. Fachliche Frage und Erkenntnislücke

**Frage:** Sind die aktuellen Variablenzuweisungen des Toggles mit dem
bestehenden Komponenten-, Zustands- und Theming-Vertrag vereinbar?

**Erkenntnislücke:** Der bisherige Abruf zeigt Variablennamen und aufgelöste
Werte, verbindet sie aber noch nicht sicher mit einem konkreten Toggle-Element,
Variantenzustand, Collection- oder Mode-Kontext. Genau diese Verbindung ist
nötig, damit ein Designer fachlich entscheiden kann, ob eine Zuweisung passend,
zu ändern oder weiter zu prüfen ist.

**Gewünschte Entscheidung:**

- aktuelle Zuweisung beibehalten;
- Zuweisung fachlich oder technisch korrigieren;
- weitere Varianten- und Mode-Evidenz einholen;
- Befund bewusst offen lassen.

## Kognitive Unterstützung

Der Befund unterstützt den Designer als fachlich entscheidenden Menschen und
verlangt keine Rekonstruktion aus Toolsyntax:

- **Wiedererkennen statt Erinnern:** Zustand, Element, Farbmuster und Hexwert
  stehen direkt zusammen.
- **Kontext vor Detail:** Die fachliche Frage und der geprüfte Gegenstand
  stehen vor der Variablenliste.
- **Bedeutung vor Benennung:** Eine Variablenbezeichnung wird nicht als
  semantische Wahrheit behandelt; ihre Rolle wird am bestehenden Vertrag
  geprüft.
- **Ist, Ableitung und Offenheit trennen:** Sichtbarer Wert, begrenzte
  Einordnung und nicht nachgewiesener Kontext bleiben unterscheidbar.
- **Entscheidung vorbereiten, nicht ersetzen:** Der Designer erhält Optionen
  und eine klare Grenze, behält aber Bewertung und Entscheidung.

## 2. Gegenstand und Grenzen

**Geprüft:** Die vom Tool am Toggle-Hauptknoten zurückgegebenen Variablen-
definitionen und der zugehörige Drop-Shadow-Effekt.

**Nicht geprüft:** Die konkrete Bindung an Track, Handle oder eine einzelne
Varianteneigenschaft; Zustände wie `Active`, `Off`, `Enabled` und `Hover`; die
Collection und der Mode; visuelle Qualität; Accessibility; Nutzerwirkung.

## 3. Sichtbarer Ist-Befund

Die Farbfelder machen den Rohwert unmittelbar wahrnehmbar. Die Bezeichnung
„am Node zurückgegeben“ bedeutet nicht automatisch, dass die Bindung an eine
bestimmte Property oder Variante bewiesen ist.

### Themed-nahe Definitionen

| Sichtbare Rolle | Farbmuster und Wert | Was ist belegt? |
|---|---|---|
| Themed Handle | <span aria-label="#001e50" style="display:inline-block;width:1rem;height:1rem;background:#001e50;border:1px solid #777"></span> `#001e50` | Definition `toggle/themed/handle` wurde zurückgegeben |
| Themed Hintergrund | <span aria-label="#e5e8ef" style="display:inline-block;width:1rem;height:1rem;background:#e5e8ef;border:1px solid #777"></span> `#e5e8ef` | Definition `toggle/themed/bg` wurde zurückgegeben |
| Themed Hover-Hintergrund | <span aria-label="#bcc5d9 mit Alpha 1A" style="display:inline-block;width:1rem;height:1rem;background:#bcc5d9;border:1px solid #777"></span> `#bcc5d91a` · ca. 10,2 % | Definition `toggle/themed/bg-hover` und Alpha-Byte `1A` wurden zurückgegeben |

### Disabled-nahe Definitionen

| Sichtbare Rolle | Farbmuster und Wert | Was ist belegt? |
|---|---|---|
| Disabled Handle | <span aria-label="#6a767d" style="display:inline-block;width:1rem;height:1rem;background:#6a767d;border:1px solid #777"></span> `#6a767d` | Definition `toggle/themed/handle-disabled` wurde zurückgegeben |
| Disabled Hintergrund | <span aria-label="#dfe4e8" style="display:inline-block;width:1rem;height:1rem;background:#dfe4e8;border:1px solid #777"></span> `#dfe4e8` | Definition `toggle/themed/bg-disabled` wurde zurückgegeben |

### Weitere sichtbare Definitionen

| Definition | Sichtbarer Wert | Einordnung |
|---|---|---|
| `primary/white` | <span aria-label="#ffffff" style="display:inline-block;width:1rem;height:1rem;background:#ffffff;border:1px solid #777"></span> `#ffffff` | Definition sichtbar; tatsächliche Property-Nutzung nicht belegt |
| `Drop Shadow/2` | Schattenfarbe `#2727271A`, Offset `(0, 2)`, Radius `4` | Effektdefinition sichtbar; keine Farbtokenrolle |

## 4. Systemische Einordnung

Die Einordnung folgt dem vorhandenen Semantic Model und dem S1-Vertrag:

- **Komponente:** Toggle als interaktiver Baustein.
- **Anatomie:** Track/Hintergrund und Handle sind die erwarteten visuellen
  Elemente; ihre konkrete Node-Bindung wurde in diesem Abruf nicht aufgelöst.
- **Zustand:** Themed- und Disabled-nahe Definitionen sind sichtbar; die
  Zuordnung zu `Active`, `Off`, `Enabled` oder `Hover` ist offen.
- **Tokenebene:** Die Namen wirken wie komponentennahe Definitionen; Collection
  und Mode wurden nicht zurückgegeben und werden daher nicht behauptet.
- **Semantik:** Eine fachliche Rolle wie „primärer visueller Ton“ oder
  „unthemed weiße Handle-Farbe“ darf erst aus dem bestehenden Vertrag oder
  einer menschlichen Vorgabe übernommen werden.

## 5. Wer bewertet was – und auf welcher Basis?

| Beteiligter | Aufgabe | Grundlage |
|---|---|---|
| Figma | zeigt Definitionen und aufgelöste Werte am geprüften Node | tatsächlicher Tooloutput |
| Assistenz | strukturiert, gruppiert sichtbar/abgeleitet/offen und benennt Grenzen | `EvidencePacket`, Tooling Map, S1-Vertrag |
| Bestehender Vertrag | liefert semantische Rollen, Zustandslogik und zulässige Begriffe | Semantic Model, Design Principles, bestätigte Entscheidungen |
| Designer:in | bewertet Passfähigkeit, Bedeutung, Priorität und Konsequenz | sichtbarer Wert, bestehender Vertrag, eigene Designabsicht |
| Review | prüft Evidenz, Scope und Schlussfolgerung | Quelle, Capability, Auslassungen und Status |
| Repository | sichert Befund, Entscheidung und Learning | `Finding`, `Decision`, `RunRecord` |

Die Assistenz darf aus `toggle/themed/handle` nicht allein ableiten, dass diese
Definition im Zustand `Active / On` am Handle korrekt verwendet wird. Das wäre
eine fachliche Entscheidung ohne ausreichende Evidenz.

## 6. Befund nach dem S1-Vertrag

### `EvidencePacket`

- **Quelle:** Figma-Datei `dW1nRf8fNQ0890eyHKO0BT`, Node `155:61945`
- **Capability:** `figma.read.variable_defs.node`
- **Evidenztyp:** `E2` – Detailkontext am konkreten Node
- **Beobachtung:** Sieben Definitionen beziehungsweise Effekte wurden
  zurückgegeben; `bg-hover` enthält den Alpha-Wert `1A`.
- **Auslassungen:** keine Property-/Variant-Zuordnung, keine Collection-/Mode-
  Information, keine visuelle oder semantische Abnahme.
- **Status:** `confirmed` für den Abruf, `partial` für die fachliche Frage.

### `Finding`

- **Beobachtung:** Am Hauptknoten sind themed-, disabled- und Hover-nahe
  Definitionen mit den oben gezeigten Werten sichtbar.
- **Ableitung:** Die Komponente verfügt wahrscheinlich über getrennte Rollen
  für themed, disabled und Hover; die konkrete Zustands- und Elementbindung ist
  nicht nachgewiesen.
- **Auswirkung:** Der Rohbefund kann eine gezielte weitere Prüfung vorbereiten,
  erlaubt aber noch keine Aussage über die Passfähigkeit des Toggle-Mappings.
- **Status:** `visible` für Werte, `derived` für die Gruppierung,
  `not_proven` für Zustands-, Property- und Mode-Zuordnung.
- **Optionen:** beibehalten, Varianten einzeln prüfen, Mode-/Collection-Evidenz
  nachholen oder Befund offen lassen.
- **Empfehlung:** keine fachliche Änderung aus diesem Abruf allein ableiten.

### `Decision`

Eine fachliche Decision wurde nicht getroffen. Der Designer bleibt Owner der
Bewertung und entscheidet erst, wenn Zustand, Element und Systemrolle
ausreichend belegt sind.

### `RunRecord`

- **Repository-Pfad:** diese Datei
- **Menschliche Beteiligung:** fachliche Frage, Scope und read-only-Ausführung
  wurden bestätigt; fachliche Passfähigkeit ist offen.
- **Completion:** `recorded`, nicht fachlich abgeschlossen

## 7. Ergebnis für den Designer

Der aktuelle Lauf zeigt direkt wahrnehmbare Farbwerte und macht sichtbar, dass
für den Toggle mehrere themed- und disabled-nahe Definitionen vorhanden sind.
Er beantwortet aber noch nicht, ob der Toggle im bestehenden System korrekt
aufgebaut ist. Dafür fehlt die Verbindung von:

```text
Variantenzustand → Element → Variable → Collection/Mode → erwartete Rolle
```

## 8. Genau ein nächster Schritt

Die relevanten Variant-Nodes des Toggles gezielt einzeln prüfen und dabei die
Property-/Variant-Zuordnung sowie Collection-/Mode-Evidenz getrennt
nachweisen.
