# Core Concepts

The foundational principles the rest of the design is built within. These are the non-negotiables that decisions are checked against.

---

## The model role-plays, the engine adjudicates

The language model is never the source of truth for game state. It proposes intent and provides voice and narration; a deterministic rules engine decides what actually happens (damage, checks, inventory, position). This keeps the game fair, debuggable, and replayable. See [[Technical/Architecture]].

---

## NPCs are agents, not content

An NPC is defined by who it is — goals, knowledge, relationships, personality — not by a fixed script. Its behaviour is emergent from that definition plus the current situation. See [[Design/NPCs]].

---

## Memory is canon

What an NPC "knows" and "remembers" is explicit, stored state — not whatever happens to be in the model's context window. The simulation owns memory; the model only ever sees a curated slice of it. See [[Technical/NPC Simulation]].

---

## You become what you do

Player characters start as a blank slate — no chosen class, no asserted identity — and are shaped entirely by their actions. What you do repeatedly, you grow better at; sustained patterns of behaviour unlock matching abilities. Identity is earned through play, not selected up front. This is the player-character expression of the project's "unwritten" premise. See [[Design/Characters]].

---

## Player freedom within consistent rules

The player may attempt anything in conversation, but the world stays internally consistent. Freedom of expression does not mean freedom from consequence or continuity.
