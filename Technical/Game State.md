# Game State

The authoritative model of the world — the single source of truth the rules engine owns and the LLM only reads from. See [[Technical/Architecture]].

---

## What lives in state

- World facts: locations, time, factions, quest flags
- Characters: player and NPC stats, position, inventory, conditions
- NPC memory: per-character history and relationship values — see [[Design/NPCs]]
- Session/conversation log

---

## State changes

Every mutation goes through a validated **action**. The model can request an action ("the merchant hands over the key") but the engine decides whether it is legal and applies it. Nothing the model says changes state until an action does. See [[Technical/NPC Simulation]].

---

## Persistence

_To be filled in._ Save format, schema, and how NPC memory is stored and queried.
