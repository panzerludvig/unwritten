# Dungeon Master

The AI referee and narrator that sits between the player and the world — the same role a human DM plays at a tabletop. It guides the player(s) through the world, describes what they can perceive, presents them with options, and reacts to their choices with interesting but reasonable situations. It is distinct from individual NPCs, which have their own simulation. See [[Design/NPCs]] and [[Technical/NPC Simulation]].

---

## Responsibilities

- **Guide the player** — lead them through the world, scene by scene, the way a tabletop DM does.
- **Describe perception** — tell the player what their character can see, hear, and otherwise notice in the current scene. The player only knows what the DM reveals.
- **Present options** — surface what the player could reasonably do or where they could go, without railroading. Options are suggestions, not an exhaustive menu; the player can always attempt something unlisted.
- **React to choices** — improvise interesting but *reasonable* consequences and situations based on what the player does. Surprising, but never arbitrary — it should follow from the established world and the player's actions.
- **Maintain pacing and scene framing** — decide when to zoom in on a moment and when to move on.
- **Route input** — hand player input to the right NPC(s) or to the rules engine when an action needs adjudication. See [[Technical/NPC Simulation]].

---

## World State

The DM maintains an evolving model of the world and remembers it across the session. This is owned by the simulation, not the model's context window — the DM reads from and writes to authoritative state. See [[Technical/Game State]] and [[Design/Core Concepts]] (Memory is canon).

It tracks at least:
- **Characters** the player has met — who they are, where, and the player's history with them. See [[Design/NPCs]].
- **Places** the player has seen or heard of — and what is known about each.
- **Events** — what has happened, so consequences stay consistent over time.
- **The current scene** — where the player is now, who is present, what is happening.

The world is revealed progressively: places and characters come into existence as the player encounters them, and once established they persist and stay consistent.

---

## The Setting

The starting assumption is a **classic D&D fantasy world** — the familiar shared imagination of swords, magic, taverns, dungeons, and adventuring parties. This is deliberately a loose baseline so play can begin immediately; specifics are dreamt up as the player explores and refined into [[Design/World]] as they solidify. See [[Design/Overview]] (the dreamt-as-you-go design).

---

## What the DM cannot do

The DM proposes; the engine disposes. Like NPCs, the DM cannot silently change game state — state changes go through validated actions. This is what keeps an improvised world internally consistent rather than contradicting itself. See [[Design/Core Concepts]].

---

## Open Questions

- Is the DM one model instance, or an orchestration layer over several?
- How much narration is the DM's vs. the active NPC's?
- How does the DM decide when something needs a mechanical resolution (a roll) vs. pure narration? See [[Design/Mechanics]].
- How are "reasonable" consequences kept consistent as the improvised world grows?
