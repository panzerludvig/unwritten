# Dev Log

Chronological record of what was discussed, decided, and *why*. The goal is to preserve reasoning, not just events. See the [[Codex]] for how this is used.

---

## 2026-06-27 — Blank-slate, action-driven characters

- **Defining character mechanic:** player characters start as a **blank slate**. Neither the player nor the DM asserts who they are — identity emerges from decisions. Do a lot of fighting → get better at combat; sneak → get better at stealth; act piously → unlock blessings/healing/paladin-like abilities. The classic D&D archetypes become *destinations arrived at through play*, not up-front choices.
- **Why:** this is the player-character mirror of the project's "unwritten" premise — the character's story is written by playing, same as the world's. Recorded as a Core Concept ("You become what you do") so it constrains future design.
- **Acknowledged open problem:** something must track accumulated behaviour and govern which abilities unlock and when, so progression feels earned rather than arbitrary. Its shape is deliberately undecided — to be figured out through play. Captured the specific open questions in [[Design/Characters]] (what's tracked, how unlocks work, consistency before any engine exists, whether aptitudes can drift).

---

## 2026-06-27 — First-stage scope: narration-only text

- **Decided the first playable version is the simplest thing that can be played:** fully text-based, the DM narrates everything, and there are **no dice / no rules engine** to begin with. Outcomes are the DM's judgement (interesting but reasonable).
- **Why:** narration-only is the fastest path to actually playing, which is how the project is meant to discover what it needs. Mechanics get added only when play reveals the DM's judgement alone isn't enough (e.g. when fairness or genuine uncertainty starts to matter).
- Captured this in a new note [[Technical/Current Stage]], kept deliberately separate from [[Technical/Architecture]] (which still describes the eventual engine-as-source-of-truth design). Added pointers from Architecture and [[Design/Mechanics]] so the current scope and the long-term intent don't get confused.

---

## 2026-06-27 — DM role defined

- **Development approach:** the game will be built by *playing* it — fleshing out systems and content as they come up in actual play, rather than designing everything up front. This is the practical expression of the "dreamt up as you go" design (see [[Design/Overview]]).
- **Defined the DM's role** in [[Design/Dungeon Master]], modelled directly on a tabletop DM: guide the player through the world, describe what they can perceive, present (non-exhaustive) options, and react to choices with interesting-but-reasonable situations. The player only knows what the DM reveals; options never railroad.
- **DM owns world state** — characters met, places seen, events, and the current scene — persisted by the simulation, not the model's context window. The world is revealed progressively and must stay consistent once established. See [[Technical/Game State]].
- **Setting baseline:** a classic D&D fantasy world, chosen deliberately as a loose starting point so play can begin immediately and specifics get filled into [[Design/World]] as they emerge. Recorded the same baseline in [[Design/World]] for consistency.

---

## 2026-06-26 — Project created

- Scaffolded the Stories Yet Unwritten vault, mirroring the structure and conventions of the Delegate project (Codex-governed Obsidian vault: Design / Technical / Dev Log / Meta / Assets).
- **Concept:** a D&D-style RPG whose NPCs are simulated by Claude rather than scripted.
- **Foundational decision:** the language model role-plays and proposes; a deterministic rules engine remains the source of truth for all game state. This was made the first Core Concept because it shapes everything downstream (fairness, debuggability, no hallucinated state). See [[Design/Core Concepts]] and [[Technical/Architecture]].
- Added an "LLM Standards" Codex entry, since runtime model cost/latency is a real engineering constraint not present in Delegate. See [[Technical/Claude Integration]].
- Named the project **Stories Yet Unwritten** (short handle: "Unwritten"), after exploring options around adventure, freedom, and openness; landed on a name evoking emergent, player-authored narrative rather than escapism. The vault was initially scaffolded under the placeholder "Animus" and renamed. No Git remote yet.
- Most notes are stubs with `_To be filled in._` sections — the framework is in place, the content is next.
