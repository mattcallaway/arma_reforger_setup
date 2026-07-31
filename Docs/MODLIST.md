# MODLIST.md

---
Status: SUPPORTING
Authority: High
Scope: Gameplay Configuration
Version: 1.0

Depends On:
- SERVER_VISION.md
- DESIGN_PRINCIPLES.md

Purpose:

This document defines every approved mod used by the server.

A mod is accepted because it strengthens the project's vision—not because it is popular.

If a mod conflicts with the design philosophy,
it should be removed regardless of how impressive it is.
---

# Mod Philosophy

The best mod pack is not the largest.

The best mod pack creates the best player experience.

Every mod should answer at least one of these questions:

- Does this improve immersion?
- Does this improve replayability?
- Does this support Special Operations gameplay?
- Does this create better stories?
- Does this reduce development effort?
- Does this improve server stability?

If the answer is "No"...

The mod probably does not belong.

---

# Core Gameplay Mods

These are considered foundational.

Without them the project loses part of its identity.

| Mod | Purpose | Status | Notes |
|------|---------|--------|------|
| RHS Status Quo | Modern military equipment | Approved | Foundation of the server |
| RHS Content Pack 01 | Additional vehicles/assets | Approved | Required dependency |
| RHS Content Pack 02 | Additional equipment | Approved | Required dependency |
| Bacon Loadout Editor | Persistent player loadouts | Approved | Essential QoL |
| CRX AI | Improved AI behavior | Approved | Core gameplay enhancement |
| DarcMissions | Dynamic mission generation | Approved | Initial mission framework |
| DarcChopper | Helicopter AI/support | Approved | Supports insertion and extraction |

---

# Quality of Life

These improve the experience without changing gameplay philosophy.

| Mod | Purpose | Status |
|------|---------|--------|
| Server Admin Tools | Administration | Approved |
| Persistent Vehicles | Vehicle persistence | Candidate |
| Enhanced Radio Actions | Better interaction | Candidate |
| Better Blood/VFX | Visual immersion | Candidate |

---

# Vehicle Expansion

These are optional until gameplay requires them.

| Vehicle | Purpose | Priority |
|----------|----------|----------|
| MRZR | Recon | Medium |
| Bradley | Mechanized Support | Medium |
| Stryker | Infantry Transport | Medium |
| Abrams | Heavy Armor | Low |
| UH-60 Blackhawk | Air Assault | High |
| Attack Helicopters | CAS | Future |

Vehicles should exist because missions require them.

Never because they are cool.

---

# Weapons & Equipment

Additional equipment should create meaningful choices.

Not inventory clutter.

Examples:

- Night Vision
- Suppressors
- Thermal Optics
- Laser Designators
- Demolition Charges
- Breaching Equipment

Every item should support a mission type.

---

# Candidate Mods

Interesting mods that require testing.

Adding a mod here does **not** mean it becomes part of the server.

Each candidate should be evaluated for:

- Stability
- Performance
- Compatibility
- Gameplay value
- Maintenance burden

Example table:

| Mod | Reason for Testing | Result |
|------|-------------------|--------|
| Example Mod | Better patrols | Pending |
| Example Mod | Weather improvements | Rejected |
| Example Mod | Better logistics | Approved |

---

# Rejected Mods

Rejected mods remain documented.

This prevents repeatedly evaluating the same ideas.

| Mod | Reason Rejected |
|------|----------------|
| Example | Performance issues |
| Example | Breaks immersion |
| Example | Redundant functionality |

---

# Compatibility Notes

Document important interactions between mods.

Example:

CRX AI requires...

RHS version...

Known conflicts...

Required load order...

Configuration changes...

This section becomes invaluable as the project grows.

---

# Future Custom Systems

As the project matures, some responsibilities may move from mods into custom systems.

Potential replacements include:

- Mission Director
- Strategic AI Commander
- Dynamic Logistics
- Persistent World State
- Regional Alert System
- Dynamic Reinforcement Manager

The goal is **not** to replace mods.

The goal is to build custom systems only where no existing solution satisfies the project's needs.

---

# Mod Acceptance Checklist

Before adding any mod ask:

✓ Does it support the vision?

✓ Does it improve Special Operations gameplay?

✓ Does it increase replayability?

✓ Does it improve immersion?

✓ Is it stable?

✓ Does it perform well?

✓ Does it work with the existing mod stack?

✓ Is it actively maintained?

✓ Can we accomplish the same thing with configuration instead?

If several answers are "No"...

Do not install it.

---

# The Golden Rule

A smaller, stable, carefully curated mod pack is always preferable to a massive mod pack filled with overlapping functionality.

Every mod should earn its place.

The objective is not to have the most mods.

The objective is to build the most memorable Special Operations experience possible.
