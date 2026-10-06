# Design system · Signal Red

The UI is designed in versioned hand-offs and built from generated tokens. Each hand-off adds to the last; nothing is restyled by hand in the engine.

## Colour

| Token | Hex | Use |
|---|---|---|
| `void` | `#08090a` | Backgrounds |
| `panel` | `#101214` | Panels, cards |
| `line` | `#262a2e` | Borders, dividers |
| `bone` | `#e8e6e1` | Primary text |
| `muted` | `#7a7f84` | Secondary text |
| `accent` | `#e5303a` | Primary actions, selection, danger |
| `mint` | `#6fc2c4` | Success, ready |
| `warning` | `#e8a33d` | Warnings, trader colour |
| `infection` | `#7fae2a` | Infection stage colour |

Colour-blind mode swaps accent and danger to orange, infection to yellow and success to blue.

## Type

| Role | Font |
|---|---|
| Titles, trader names, tab labels | Big Shoulders Display |
| HUD and price numbers | Chakra Petch |
| HUD labels, data | Share Tech Mono |
| Body, specs | IBM Plex Mono |
| UI headings | Saira Condensed |

All fonts are from Google Fonts under the SIL Open Font License.

## Rules

- Every screen ships at **1080p** (reference), **1440p** (×1.333) and **21:9** (menus centred in 1920; top bar, backgrounds and HUD extend to the edges).
- Keyboard and gamepad prompts on every screen.
- Selection uses bracket corners and never pulses. Nothing pulses when the player is calm.
- One accent. Red means "act here" or "danger"; it is not decoration.

## Hand-offs

| Version | Scope |
|---|---|
| v4–v7 | Front end, raid HUD, bunker, components, icons |
| v8 · Signal Red | Palette, condition diagnostic, HUD vitals, facilities, inventory |
| v9 · Traders | Trader list, trade screen, trust tiers, radio intro |
| v10 · Beta | Condition FX, intel archive, contracts, trade back + glitch, operator storage |
| v11 · Badges | KAZI rank badges: collection, inspect, loot tables |

<img src="../media/ui/ui-badges-collection.jpg" alt="Badge collection screen" width="100%">
