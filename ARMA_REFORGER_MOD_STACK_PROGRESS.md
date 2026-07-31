# Arma Reforger PvE Server Mod Stack Progress

**Project:** Operation Black Tide  
**Updated:** July 30, 2026  
**Current target:** 3-4 players initially, scalable to 16-32 players

## Server Vision

Build a modern, persistent PvE Arma Reforger server featuring:

- Strong tactical AI
- AI-controlled helicopters and ground vehicles
- Dynamic missions and changing objectives
- Persistent player loadouts and vehicles
- Modern weapons, equipment, uniforms, and vehicles
- Enemy quick-reaction forces and reinforcement systems
- A campaign that scales with player count
- A stable core mod set that can expand over time

## Current Recommended Direction

Start with a hybrid of:

1. **Dynamic Special Operations**
   - HVT missions
   - Hostage rescues
   - Cache destruction
   - Convoy ambushes
   - Crash-site recovery
   - Base assaults

2. **Dynamic Frontline War**
   - AI captures and defends territory
   - Vehicle convoys
   - Helicopter patrols
   - Counterattacks
   - Regional threat escalation

3. **Persistent Campaign Systems**
   - Saved loadouts
   - Persistent vehicles
   - FOB progression
   - Long-term mission consequences

## 15-Mod Shortlist

> Workshop links and compatibility should be rechecked before final deployment because Reforger updates can break dependencies.

| Priority | Mod | Purpose | Workshop URL / Search |
|---|---|---|---|
| 1 | Bacon Loadout Editor | Saved operator kits, classes, and custom loadouts | https://reforger.armaplatform.com/workshop/606B100247F5C709 |
| 2 | RHS: Status Quo | Modern weapons, uniforms, factions, and vehicles | https://reforger.armaplatform.com/workshop |
| 3 | RHS Content Pack 01 | Additional RHS assets and dependencies | https://reforger.armaplatform.com/workshop |
| 4 | RHS Content Pack 02 | Additional RHS vehicles and equipment | https://reforger.armaplatform.com/workshop |
| 5 | DarcMissions | Dynamic missions, patrols, HVTs, caches, roadblocks, and crash sites | https://reforger.armaplatform.com/workshop/5ED0FAC84A48D018 |
| 6 | DarcChopper | AI helicopter patrols, attacks, landings, and troop insertions | https://reforger.armaplatform.com/workshop/689EDED542F881AF |
| 7 | CRX Enfusion A.I. | Smarter infantry movement, flanking, suppression, and reactions | https://reforger.armaplatform.com/workshop/5F268647F8A1A1F4 |
| 8 | IPC Autonomous Capture AI | Autonomous attacking, defending, and territory capture | Search the official Workshop for `IPC Autonomous Capture AI` |
| 9 | Server Admin Tools | Administration, debugging, moderation, and server control | Search the official Workshop for `Server Admin Tools` |
| 10 | WCS Armaments | Modern weapons and attachments | Search the official Workshop for `WCS Armaments` |
| 11 | RIS Laser Attachments | Tactical lasers and weapon accessories | Search the official Workshop for `RIS Laser Attachments` |
| 12 | MH-60 DAP / Fastroping | Special-operations transport and assault helicopter gameplay | Search the official Workshop for `MH-60 DAP Fastroping` |
| 13 | Persistent Vehicles | Keeps vehicles available between sessions or restarts | Search the official Workshop for `Persistent Vehicles` |
| 14 | ACE Core | Framework for realism and quality-of-life systems | Search the official Workshop for `ACE Core` |
| 15 | EE Radio Actions | Radio-based CAS, transport, artillery, reinforcement, and medevac actions | Search the official Workshop for `EE Radio Actions` |

## Recommended First Test Stack

Do not enable all 15 mods immediately. Begin with a controlled test build:

### Core Test Build

- Bacon Loadout Editor
- RHS: Status Quo
- Required RHS dependencies
- DarcMissions
- CRX Enfusion A.I.
- DarcChopper
- Server Admin Tools

### Why Start Here

This stack tests the most important server features:

- Custom player kits
- Modern factions and equipment
- Dynamic objectives
- Improved infantry AI
- AI helicopter behavior
- Administration and troubleshooting

## Compatibility Rules

### Avoid Multiple AI Overhauls Initially

Do not combine several major AI mods until each one is tested independently.

Potential conflict areas include:

- Infantry behavior
- Squad command logic
- Vehicle pathfinding
- Target detection
- Spawning systems
- AI commanders

Start with **CRX Enfusion A.I.** as the primary infantry AI improvement.

Add **IPC Autonomous Capture AI** only after the base mission stack is stable.

### Limit Duplicate Weapon Packs

Avoid installing many overlapping weapon packs. Too many packs can cause:

- Duplicate guns
- Broken magazines
- Missing loadout items
- Arsenal clutter
- Large downloads
- Dependency conflicts
- Longer startup times

Prefer one primary equipment ecosystem, ideally RHS plus carefully selected Bacon-compatible additions.

## Planned Server Progression

### Phase 1 - Four-Player Special Operations

- 3-4 players
- One active mission at a time
- 40-60 active AI maximum
- Dynamic HVT, rescue, cache, and convoy missions
- AI helicopter patrols and troop insertions
- Bacon loadouts
- RHS equipment

### Phase 2 - Living Frontline

- Territory ownership
- AI counterattacks
- Enemy reinforcement convoys
- Helicopter quick-reaction forces
- Regional alert levels
- Persistent FOB resources
- Multiple mission chains

### Phase 3 - Public Server Expansion

- 16-32 players
- Multiple active operations
- Player-count-based AI scaling
- Regional AI budgets
- Distant AI caching or despawning
- Squad-specific objectives
- Dedicated armor and aviation missions
- Expanded administration and moderation tools

## Possible Bonus Mods

These should be evaluated after the core stack is stable:

- MRZR special-operations vehicle
- KA-52 attack helicopter
- KA-27 transport helicopter
- OH-58D Kiowa
- M1 Abrams
- Bradley IFV
- Stryker
- JLTV
- C-130J
- Game Master Enhanced
- Better Blood / VFX
- Advanced Zeroing System
- Wirecutters
- Keep Gun When Unconscious

## Current Design Name

# Operation Black Tide

A persistent modern PvE campaign where a small special-operations team influences a larger AI-controlled war.

### Desired Gameplay Loop

1. Players select saved Bacon loadouts.
2. A dynamic mission is generated.
3. Players deploy by ground vehicle or helicopter.
4. Enemy AI patrols, reinforces, and counterattacks.
5. Mission success changes regional threat or territory control.
6. New missions are generated from the campaign state.
7. The server scales enemy presence based on active players.

## Immediate Next Steps

- [ ] Verify exact official Workshop URLs for every shortlisted mod
- [ ] Record all mod IDs and dependency IDs
- [ ] Confirm every mod supports the current Arma Reforger version
- [ ] Create a minimal dedicated-server configuration
- [ ] Test Bacon Loadout Editor with RHS
- [ ] Test DarcMissions without additional AI mods
- [ ] Add CRX AI and check mission behavior
- [ ] Add DarcChopper and test AI landings and troop deployment
- [ ] Measure server FPS with 40, 60, and 100 active AI
- [ ] Document crashes, conflicts, and broken dependencies
- [ ] Lock the first stable release as `v0.1.0`

## Suggested Repository Files

```text
README.md
WORKLOG.md
TODO.md
MOD_STACK.md
SERVER_CONFIG.md
COMPATIBILITY_NOTES.md
CHANGELOG.md
```

## Release Goal: v0.1.0

The first playable release should include:

- One stable map
- Saved custom loadouts
- Modern player and enemy factions
- At least five dynamic mission types
- Improved infantry AI
- One functioning AI helicopter system
- Basic administration tools
- Stable performance for four players

