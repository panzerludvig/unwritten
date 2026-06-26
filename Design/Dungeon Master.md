# Dungeon Master

The AI referee and narrator that sits between the player and the world. The DM frames scenes, narrates outcomes, and decides which NPCs are present and active. It is distinct from individual NPCs, which have their own simulation. See [[Design/NPCs]] and [[Technical/NPC Simulation]].

---

## Responsibilities

- Narrate the world and the results of actions
- Decide what the player perceives
- Route player input to the right NPC(s) or to the rules engine
- Maintain pacing and scene framing

## What the DM cannot do

The DM proposes; the engine disposes. Like NPCs, the DM cannot silently change game state — state changes go through validated actions. See [[Design/Core Concepts]].

## Open Questions

- Is the DM one model instance, or an orchestration layer over several?
- How much narration is the DM's vs. the active NPC's?

_To be filled in._
