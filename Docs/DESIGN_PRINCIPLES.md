# DESIGN_PRINCIPLES.md

---
Status: SUPPORTING
Authority: High
Scope: Entire Project
Version: 1.0
Depends On:
- SERVER_VISION.md

If this document conflicts with SERVER_VISION.md,
SERVER_VISION.md always takes precedence.
---

# Design Principles

This document defines *how* we design systems.

Not every feature belongs in the project.

Every new idea should be measured against these principles before implementation.

---

# Principle 1
## Fun Comes First

Nothing is added simply because it is realistic.

Nothing is added simply because it is technically impressive.

Nothing is added simply because another server has it.

A feature exists only if it makes the game more enjoyable.

Every milestone must immediately improve the player experience.

If a feature isn't fun yet...

It isn't finished.

---

# Principle 2
## Build the Illusion

Players do not need a perfectly simulated battlefield.

They need a battlefield that *feels believable.*

Never simulate something the player cannot perceive.

Examples:

Instead of simulating hundreds of AI...

Simulate a living war through:

- radio traffic
- helicopter flyovers
- distant artillery
- smoke
- moving convoys
- changing objectives
- evolving mission availability

The player's imagination fills the gaps.

---

# Principle 3
## Systems Create Stories

Never build isolated content.

Build systems that naturally generate memorable situations.

Instead of:

Create 100 missions.

Prefer:

Create 10 systems capable of producing 10,000 different missions.

---

# Principle 4
## Small Team First

Every system must be enjoyable for:

3 players.

If it isn't fun with three...

It will not magically become fun with thirty.

Small-team gameplay is the benchmark.

---

# Principle 5
## Scale Through Systems

Never create separate gameplay for different server sizes.

Instead...

Scale using variables.

Examples:

Enemy budgets

Patrol density

Mission concurrency

QRF response

Vehicle availability

Mission frequency

The experience changes in scale...

Not identity.

---

# Principle 6
## Stealth Is Gameplay

Players should rarely want to eliminate every enemy.

The optimal solution is often:

Avoid.

Distract.

Sneak.

Sabotage.

Escape.

Detection should change the mission...

Not automatically fail it.

Stealth creates tension.

Combat resolves tension.

Both should exist.

---

# Principle 7
## Consequences Matter

Every mission should leave fingerprints on the world.

Examples:

Destroy radar

↓

Enemy aircraft become less effective.

Destroy logistics

↓

Enemy armor appears less frequently.

Capture intelligence

↓

New missions unlock.

Failure should matter too.

Players should feel responsible for the evolving battlefield.

---

# Principle 8
## The Enemy Is Intelligent, Not Omniscient

Enemy AI should behave credibly.

Not perfectly.

Enemies:

Search.

Communicate.

Lose track.

Investigate.

Flank.

Retreat.

Reinforce.

They should never possess magical information.

Losing sight of players should matter.

---

# Principle 9
## Every System Needs Knobs

Every important system should be configurable.

Examples:

Patrol count

Detection distance

Reaction delay

Mission frequency

Helicopter availability

Threat budget

Difficulty should come from configuration.

Not rewriting code.

---

# Principle 10
## Mods Before Code

Always ask:

Can an existing mod solve this?

Can configuration solve this?

Can scripting solve this?

Only then ask:

Should we build a custom framework?

Respect the work of the modding community.

Custom code fills gaps.

It does not replace excellent existing work.

---

# Principle 11
## Performance Is Gameplay

Frame rate is part of immersion.

Server stability is part of immersion.

Network synchronization is part of immersion.

Never sacrifice playability for complexity.

Simple systems executed well outperform complicated systems executed poorly.

---

# Principle 12
## Player Agency

Players should solve problems.

Not follow scripts.

Whenever possible...

Offer choices.

Example:

Destroy the bridge.

Hack the communications tower.

Assassinate the commander.

Each solution should produce different strategic outcomes.

---

# Principle 13
## Emergence Over Scripting

The most memorable moments are unplanned.

Design systems that interact.

Examples:

Weather

Helicopters

Patrols

Logistics

Civilian traffic

Mission timers

These interactions naturally produce stories no designer explicitly wrote.

---

# Principle 14
## Everything Should Be Replaceable

Every system should be modular.

Mission generation.

AI.

Persistence.

Vehicles.

Weather.

Reputation.

Nothing should depend on one irreplaceable implementation.

Modules should communicate through clear interfaces.

---

# Principle 15
## Documentation Is Code

A feature is not complete until it is documented.

Every completed system should explain:

Purpose

Inputs

Outputs

Configuration

Dependencies

Known limitations

Good documentation makes future development exponentially easier.

---

# The Evolution Rule

Every release should make the game better than the previous release.

Not larger.

Better.

Players should always prefer the newest version.

If they don't...

We failed.

---

# Decision Checklist

Before implementing any feature ask:

✓ Is it fun?

✓ Does it create memorable stories?

✓ Does it improve replayability?

✓ Does it respect player agency?

✓ Can it work with three players?

✓ Can it scale naturally?

✓ Is it performant?

✓ Can an existing mod accomplish this?

✓ Is it documented?

If any answer is "No"...

Stop.

Reconsider.

Simplify.

---

# Final Principle

The objective is not to build the most complicated Arma server.

The objective is to build the most memorable one.

Complexity is never the goal.

Great stories are.
