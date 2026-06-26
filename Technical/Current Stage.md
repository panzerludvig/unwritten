# Current Stage

What is actually built and in scope *right now* — as distinct from the eventual architecture in [[Technical/Architecture]]. Because the game is built by playing it, this note changes often; update it whenever the working scope shifts.

---

## Stage: narration-only text prototype

The first version is the simplest thing that can be played:

- **Fully text-based.** The player types; the DM narrates back. No UI, no graphics.
- **The DM narrates everything.** All description, options, and outcomes come from the DM in prose. See [[Design/Dungeon Master]].
- **No dice / no rules engine yet.** Outcomes are decided by the DM's judgement (interesting but reasonable), not by mechanical resolution. See [[Design/Mechanics]].
- **Setting:** classic D&D fantasy baseline. See [[Design/World]].

---

## Deferred (intended, not yet built)

These remain the long-term direction in [[Technical/Architecture]] — just not part of the first playable version:

- The deterministic **rules engine** as source of truth for game state.
- **Dice mechanics** and any mechanical resolution.
- **Tool use / validated actions** for state changes.
- Distinct per-NPC simulation separate from the DM. See [[Technical/NPC Simulation]].

---

## Why start here

Narration-only is the fastest path to actually playing, which is how this project discovers what it needs (see the build-by-playing approach in [[Dev Log/Log]]). Mechanics get added when play reveals that the DM's judgement alone is no longer enough — e.g. when fairness or uncertainty starts to matter.
