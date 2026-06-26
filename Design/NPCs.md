# NPCs

What a non-player character is in Stories Yet Unwritten, and how it behaves. NPCs are the heart of the project — they are simulated by a language model rather than scripted. The runtime mechanics live in [[Technical/NPC Simulation]]; this note covers the design.

---

## What defines an NPC

Every NPC has an explicit, authored profile:
- **Identity** — name, role, appearance, voice
- **Personality** — temperament, values, quirks, how they speak
- **Goals** — what they want, short and long term
- **Knowledge** — what they know (and crucially, what they don't)
- **Relationships** — feelings toward the player and other NPCs
- **State** — mood, location, inventory, current situation

This profile is the NPC's "character sheet" for the model. See [[Technical/NPC Simulation]] for how it becomes a prompt.

---

## Memory

An NPC accumulates memories of what has happened — conversations, betrayals, favours. Memory is stored by the simulation and summarised into the model's context, not left to the context window. See [[Design/Core Concepts]] (Memory is canon).

---

## Behaviour boundaries

The model gives voice to an NPC but cannot change the world on its own — it cannot grant items, move characters, or set facts. Those require an action the engine validates. This prevents hallucinated state. See [[Design/Dungeon Master]].

---

## Authoring NPCs

_To be filled in._ How designers create and balance NPC profiles, and how much is hand-authored vs. generated.

---

## Open Questions

- How is consistency enforced across long play (days/weeks of game time)?
- How do NPCs talk to each other, if at all?
- What's the budget for how many NPCs can be "live" at once? See [[Technical/Claude Integration]].
