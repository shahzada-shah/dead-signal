<p align="center">
  <img src="media/banner.png" alt="DEAD SIGNAL — top-down zombie extraction shooter for PC" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/engine-Unity%206-e5303a?style=flat-square&labelColor=101214" alt="Unity 6">
  <img src="https://img.shields.io/badge/render-URP-e8e6e1?style=flat-square&labelColor=101214" alt="URP">
  <img src="https://img.shields.io/badge/UI-UI%20Toolkit-e8e6e1?style=flat-square&labelColor=101214" alt="UI Toolkit">
  <img src="https://img.shields.io/badge/platform-PC%20%C2%B7%20Steam-e8e6e1?style=flat-square&labelColor=101214" alt="PC · Steam">
  <img src="https://img.shields.io/badge/status-in%20development-e8a33d?style=flat-square&labelColor=101214" alt="In development">
</p>

<p align="center">
  <a href="#the-game">The game</a> ·
  <a href="#features">Features</a> ·
  <a href="#in-engine">In engine</a> ·
  <a href="#architecture">Architecture</a> ·
  <a href="#roadmap">Roadmap</a> ·
  <a href="#studio">Studio</a>
</p>

> This repository is the public page for **DEAD SIGNAL** by **KAZI Studio Games**. The game source is private. Technical write-ups are in [`docs/`](docs).

<a id="the-game"></a>
<img src="media/headers/01-the-game.png" alt="01 · The game" width="100%">

Go into an overrun city, search it, and get out before the timer ends. What you carry out is yours. Die and it stays behind.

| | |
|---|---|
| **Camera** | Top-down · 17 m |
| **Zones** | 6 · 25–45 min raids |
| **Infected types** | 5 |
| **Bunker rooms** | 12 |

<p>
  <img src="media/art/key-art-breach.jpg" alt="Operators clearing a hospital ward" width="49%">
  <img src="media/art/key-art-refinery.jpg" alt="Refinery extraction under fire" width="49%">
</p>

<a id="the-loop"></a>
<img src="media/headers/02-the-loop.png" alt="02 · The loop" width="100%">

<img src="media/loop.png" alt="Raid → Loot → Extract → Bunker" width="100%">

<a id="features"></a>
<img src="media/headers/03-features.png" alt="03 · Features" width="100%">

<img src="media/features.png" alt="Feature overview" width="100%">

- **Five infected.** Walker, Runner, Brute, Bloater, Screamer. Each one changes how you move.
- **Infection.** Bites build infection. Veins creep in from the screen edge as it climbs.
- **Scavenged builds.** Mod with taped and improvised parts, and live with the jam risk.
- **The bunker.** Twelve rooms to build and power, each with its own bonus.
- **Radio traders.** Contacts on live feeds who trade, hand out contracts and judge your trust.
- **KAZI badges.** Rank insignia taken from the dead. Collect, sell, or turn them in for contracts.

<a id="in-engine"></a>
<img src="media/headers/04-in-engine.png" alt="04 · In engine" width="100%">

<p>
  <img src="media/ui/ui-contracts.jpg" alt="Bunker · Contracts screen" width="100%">
</p>
<p>
  <img src="media/art/trader-iron-angel.jpg" alt="Iron Angel, trader" width="32%">
  <img src="media/art/trader-feed-glitch.jpg" alt="Trader feed glitch on a failed deal" width="32%">
  <img src="media/art/key-art-visor.jpg" alt="KAZI operator visor" width="32%">
</p>

<a id="kazi-badges"></a>
<img src="media/headers/05-kazi-badges.png" alt="05 · KAZI badges" width="100%">

<img src="media/badges.png" alt="Eight KAZI rank badges, Recruit to The Founder" width="100%">

Every KAZI soldier carries a rank badge. Each one is a unique item: it records the callsign of the soldier who wore it and who killed them, and comes in pristine, scratched or bloodied condition. Contracts ask for them, traders buy them, and the collection screen tracks every rank.

<p>
  <img src="media/ui/ui-badges-collection.jpg" alt="Badge collection screen" width="100%">
</p>
<p align="center">
  <img src="media/art/badge-conditions.png" alt="Veteran badge in pristine, scratched and bloodied condition" width="80%">
</p>

<a id="architecture"></a>
<img src="media/headers/06-architecture.png" alt="06 · Architecture" width="100%">

<img src="media/architecture.png" alt="Architecture overview" width="100%">

```mermaid
flowchart LR
  D[Design pages<br/>v4 → v11] --> T[tokens · motion · strings<br/>JSON]
  T --> G[Token generator<br/>Editor]
  G --> C[C# tokens + USS]
  C --> U[UI Toolkit screens]
  U --> K[Capture checks<br/>1080p · 1440p · 21:9]
  K -. diff .-> D
```

- **Runtime:** Unity 6, URP, UI Toolkit. Raid simulation, bunker meta progression, presentation and core data are separate layers.
- **One full-screen pass for conditions.** Infection, bleeding, low health, exhaustion and hit feedback combine in a single URP pass with one material and one draw.
- **Design system in the build.** Design hands off versioned tokens and specs. An editor generator turns them into C# and USS, and engine captures are diffed against the spec each wave.

Full write-up: [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md)

<a id="design-system"></a>
<img src="media/headers/07-design-system.png" alt="07 · Design system" width="100%">

**Signal Red.** Void black, bone text, one red accent. Every screen ships at 1080p, 1440p and 21:9, with keyboard and gamepad prompts, colour-blind and reduce-motion modes.

| Token | Hex | Use |
|---|---|---|
| `void` | `#08090a` | Backgrounds |
| `panel` | `#101214` | Panels, cards |
| `bone` | `#e8e6e1` | Text |
| `accent` | `#e5303a` | Primary actions, selection, danger |
| `mint` | `#6fc2c4` | Success, ready |
| `trader-angel` | `#e8a33d` | Trader colour |

Type: Big Shoulders Display (titles), Chakra Petch (numbers), Share Tech Mono and IBM Plex Mono (labels, data), Saira Condensed (UI headings).

More: [`docs/DESIGN_SYSTEM.md`](docs/DESIGN_SYSTEM.md)

<a id="roadmap"></a>
<img src="media/headers/08-roadmap.png" alt="08 · Roadmap" width="100%">

<img src="media/roadmap.png" alt="Roadmap: Prototype done; Vertical slice next; Early Access and 1.0 planned" width="100%">

| Milestone | Status | Scope |
|---|---|---|
| Prototype | **Done** | Core loop, AI, inventory, UI hand-off |
| Vertical slice | Next | Mercy General final art, bunker, 3 contacts |
| Early Access | Planned | 4 zones, all contacts, Steam launch |
| 1.0 | Planned | 6 zones, story complete, console port |

<a id="studio"></a>
<img src="media/headers/09-studio.png" alt="09 · Studio" width="100%">

**KAZI Studio Games** builds DEAD SIGNAL. For investor, press or hiring enquiries, contact us through this GitHub organisation's profile.

<img src="media/footer.png" alt="KAZI Studio Games" width="100%">

<sub>© KAZI Studio Games. All rights reserved. See [LICENSE.md](LICENSE.md) and [CREDITS.md](CREDITS.md).</sub>
