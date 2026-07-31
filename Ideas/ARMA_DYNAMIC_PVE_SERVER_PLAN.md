# Arma Reforger Dynamic PvE Server Plan

## Project Goal

Create an action-packed, replayable Arma Reforger PvE server where missions, enemy reactions, reinforcements, vehicles, and battlefield conditions change from session to session.

The initial target is a small cooperative group of roughly 3–8 players, with room to expand later.

## Core Server Identity

A modern cooperative special-operations server set inside a larger reactive conflict.

Players should feel like they are conducting meaningful missions while the enemy behaves like an organized force rather than a collection of static spawns.

Key goals:

- Dynamic missions
- Smarter infantry behavior
- Ground quick-reaction forces
- Tanks and mechanized reinforcements
- Helicopter insertions, searches, and support
- Regional alert levels
- Mission consequences
- Limited persistence
- Strong server performance
- A curated mod list rather than an oversized dependency stack

## Recommended Development Approach

Use a hybrid system.

Let Reforger or a selected AI framework handle:

- Navigation
- Shooting
- Cover usage
- Basic squad movement
- Vehicle operation
- Waypoint execution

Build custom systems for:

- Mission generation
- Strategic enemy decisions
- Regional alert levels
- Reinforcement budgets
- Mission chains
- Persistent consequences
- Vehicle routing
- Helicopter task coordination
- Cleanup and performance management

## Dynamic Mission Director

The Mission Director decides what happens.

Responsibilities:

- Select mission type
- Select mission location
- Scale difficulty by player count
- Spawn or activate defenders
- Trigger reinforcements
- Monitor objectives
- Handle mission success and failure
- Clean up entities
- Update persistent campaign state
- Schedule the next operation

Potential mission types:

- Assault an occupied town
- Defend a position
- Destroy an artillery battery
- Destroy a radar installation
- Rescue captives
- Recover a downed pilot
- Intercept an armored convoy
- Eliminate a high-value target
- Escort a logistics convoy
- Sabotage an enemy base
- Clear and hold multiple objectives
- Repel a counterattack

## Strategic AI Commander

The AI Commander decides how the enemy responds.

Examples:

- Send infantry to reinforce a town
- Establish defensive positions
- Redirect nearby patrols
- Hold an armored vehicle as a reserve
- Dispatch a ground quick-reaction force
- Launch helicopter search operations
- Escalate to armor after repeated player success
- Withdraw damaged or isolated units
- Reduce response strength when radar or logistics assets are destroyed

Suggested regional state:

- Alert level
- Enemy strength
- Reinforcement points
- Radar status
- Armor availability
- Helicopter availability
- Regional control
- Recent player activity

## Smarter Infantry Behavior

The AI should appear intelligent without being omniscient.

Recommended awareness stages:

1. Unaware
2. Suspicious
3. Alerted
4. Engaged
5. Searching
6. Returning to normal

Recommended behaviors:

- Investigate nearby gunfire
- Share limited contact reports
- Lose confidence in old player positions
- Search last-known areas
- Request anti-armor support
- Flank static player positions
- Retreat after heavy casualties
- Use smoke when withdrawing
- Call reinforcements only when communication or command assets are available

## Contact Memory

Enemy groups should remember the player's last-known location, but the information should become less accurate over time.

Example:

- 0–10 seconds: precise location
- 10–30 seconds: approximate location
- 30–90 seconds: broad search area
- 90+ seconds: contact lost

This creates believable search behavior and prevents the AI from knowing the player's exact location forever.

## Tanks and Armored Vehicles

Armor should be used as a battlefield asset, not spawned directly on top of players.

Recommended armor roles:

- Mobile reserve
- Counterattack force
- Convoy escort
- Long-range fire support
- Blocking force
- Infantry support

Recommended armored behavior:

1. Spawn with a valid driver, gunner, and commander.
2. Move to a safe staging point.
3. Follow prevalidated routes.
4. Take a support or overwatch position.
5. Engage from useful range.
6. Support infantry advances.
7. Withdraw when heavily damaged or isolated.

Use hand-validated route nodes around:

- Bridges
- Narrow towns
- Forest roads
- Compounds
- Steep terrain
- River crossings

## Helicopter AI

Helicopters need strict task states and recovery logic.

Potential tasks:

- Troop insertion
- Extraction
- Search patrol
- Reconnaissance
- Medevac
- Close air support
- Reinforcement delivery

Suggested helicopter task flow:

1. Preparing
2. Crew boarding
3. Passenger boarding
4. Takeoff
5. Transit
6. Approach
7. Landing
8. Disembarking
9. Departure
10. Return to base
11. Abort or fallback

Every state should include:

- Success condition
- Timeout
- Failure condition
- Recovery action

Landing zones should be predefined and validated for:

- Terrain flatness
- Obstacle clearance
- Approach direction
- Distance from threats
- Alternate landing options

If a helicopter cannot complete a task, it should try another landing zone, abort safely, or convert the reinforcement into a ground response.

## Dynamic Mission Generation

Each mission should combine several variables:

- Mission type
- Location
- Enemy force composition
- Supporting objectives
- Complication
- Reinforcement pattern
- Time of day
- Weather
- Extraction condition
- Follow-up consequence

Example generated mission:

**Objective:** Destroy an enemy communications site  
**Location:** Hilltop relay northeast of a town  
**Defenders:** Infantry platoon and machine-gun team  
**Support:** Armored patrol nearby  
**Complication:** Friendly reconnaissance team trapped in the region  
**Reaction:** Truck-mounted QRF after the alarm is raised  
**Escalation:** Helicopter insertion after twenty minutes  
**Consequence:** Enemy reinforcement response is weaker for future missions  

## Difficulty Scaling

Difficulty should not rely only on higher AI accuracy.

Scale difficulty with:

- Number of enemy groups
- Defensive preparation
- Reinforcement speed
- Armor availability
- Helicopter availability
- Flanking frequency
- Enemy coordination
- Intelligence quality
- Mission complexity

Suggested threat-budget costs:

- Rifle squad: 10
- Machine-gun team: 5
- Anti-tank team: 7
- Truck reinforcement: 8
- APC: 18
- Tank: 35
- Transport helicopter: 25
- Attack helicopter: 45

The director should spend a limited threat budget rather than spawn unlimited enemies.

## Persistence

Start with limited persistence.

Save:

- Regional alert
- Completed missions
- Destroyed strategic assets
- Enemy reinforcement strength
- Territory control
- Important FOB state
- Mission-chain progress

Avoid full world persistence in the first release.

## Performance Strategy

Use three simulation levels:

### Active

Full AI and vehicle simulation near players and active objectives.

### Dormant

Entities exist but update less frequently.

### Strategic

No live entities. Units are represented only as data.

Suggested initial targets:

- 3–8 players
- 40–60 active AI
- One major active combat zone
- One or two active helicopters
- Limited armored groups
- No unnecessary distant AI simulation

Avoid expensive logic every frame. Use scheduled updates and stagger AI evaluations.

## Multiplayer Rules

Mission state, spawning, rewards, objective completion, reinforcements, and persistence should be server-authoritative.

Replicate only what clients need:

- Objective status
- Mission markers
- Notifications
- Timers
- Simplified regional state

Custom replicated behavior should verify authority through the relevant `RplComponent` before changing shared state or invoking RPCs.

## Recommended Mod Strategy

Use one primary AI overhaul and avoid stacking multiple large AI systems.

Potential categories:

- One AI overhaul
- One dynamic mission framework
- One main faction and equipment pack
- One helicopter family
- One ground-vehicle family
- One loadout or arsenal utility
- One administration tool
- A small selection of immersion enhancements

Mods discussed as candidates:

1. CRX Enfusion A.I.
2. RHS: Status Quo
3. Bacon Loadout Editor
4. Dynamic Special Operations
5. Combat Ops Enhanced
6. Escapists
7. Server Admin Tools
8. WCS AH-6M
9. WCS Scopes
10. WCS Sounds
11. CRX Very Hard AI
12. Dynamic Frontline War
13. Advanced Medical
14. Civilian Population
15. Logistics or Supply Framework

> Important: Verify every current Workshop URL, dependency, license, compatibility note, and game-version requirement before installation. Do not assume multiple AI or scenario frameworks can run together safely.

## Recommended First Release

The first playable milestone should be:

> A 2–8 player operation that selects one of three mission types, deploys infantry defenders, triggers a ground quick-reaction force, launches a counterattack after objective completion, and safely cleans up all mission entities.

Do not make tanks or helicopters mandatory for the first stable loop.

## Development Roadmap

### Phase 1 — Stable Base Server

- Dedicated server configuration
- One map
- One friendly faction
- One hostile faction
- Curated equipment
- Administration tools
- Repeatable benchmark mission

### Phase 2 — Dynamic Infantry Missions

- Raid
- Rescue
- Sabotage
- Defend
- Convoy ambush
- Player-count scaling
- Reliable cleanup

### Phase 3 — Enemy Response System

- Regional alert
- Patrol redirection
- Ground QRF
- Search behavior
- Reinforcement limits
- Escalation and cooldown

### Phase 4 — Ground Vehicles

- Transport trucks
- Armed vehicles
- Mechanized QRF
- Convoys
- Route validation
- Armor fallback logic

### Phase 5 — Helicopters

- Patrol
- Search
- Troop insertion
- Extraction
- Alternate landing zones
- Timeout and abort handling

### Phase 6 — Persistent Frontline

- Territory ownership
- Regional resources
- Mission chains
- Strategic enemy commander
- Persistent threat
- Connected operations

## Suggested Repository Structure

```text
arma_reforger_setup/
├── README.md
├── docs/
│   ├── SERVER_VISION.md
│   ├── AI_ARCHITECTURE.md
│   ├── MISSION_ARCHITECTURE.md
│   ├── MOD_CANDIDATES.md
│   ├── PERFORMANCE_BUDGET.md
│   ├── ROADMAP.md
│   ├── CURRENT_STATE.md
│   └── DECISIONS.md
├── server/
│   ├── serverConfig.example.json
│   └── mods.example.json
└── addons/
    └── DynamicPvE/
        ├── Scripts/
        │   └── Game/
        │       ├── Mission/
        │       ├── AI/
        │       ├── Vehicles/
        │       ├── Aviation/
        │       ├── Persistence/
        │       └── Networking/
        ├── Configs/
        └── Prefabs/
```

## First Custom System to Build

The best first custom feature is a Regional Alert and Reinforcement Manager.

Player actions could produce effects such as:

- Destroy radar: reduce enemy detection and helicopter response
- Eliminate patrol: slightly increase regional alert
- Attack base: strongly increase alert
- Capture intelligence: reveal future mission opportunities
- Destroy QRF: reduce regional reinforcement points
- Complete mission undetected: avoid major escalation
- Destroy logistics: reduce future vehicle availability

This system provides continuity and replayability before a full persistent campaign is implemented.

## Collaboration Workflow

Use GitHub as the shared source of truth.

Recommended files:

- `CURRENT_STATE.md` — what works, what is broken, and what is being tested
- `DECISIONS.md` — agreed architectural decisions
- `ROADMAP.md` — planned milestones
- Separate session summaries for each collaborator
- Commit messages that describe completed work clearly

Keep separate conversations separate, but record all important decisions in the repository so both collaborators stay aligned.
