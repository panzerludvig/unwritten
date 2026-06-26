# NPC Simulation

How a Claude call becomes an in-character NPC response. This is the technical core of Stories Yet Unwritten. The design intent is in [[Design/NPCs]]; this note is the runtime mechanism.

---

## The turn, end to end

1. **Player input** arrives (free text, or a chosen action).
2. **Context assembly** — the simulation builds a prompt for the target NPC from authoritative state: its profile, relevant memories, the current scene, and recent dialogue. The model receives a curated slice, never the raw context window. See [[Technical/Game State]].
3. **Model call** — Claude responds in character. It may speak, and it may *propose actions* via tool use (e.g. `give_item`, `attack`, `move`, `update_relationship`).
4. **Adjudication** — the rules engine validates and resolves any proposed actions and any dice. Illegal proposals are rejected or revised. See [[Design/Mechanics]].
5. **Commit** — legal results are written to state; new memories are recorded.
6. **Narration** — the resolved outcome is presented to the player.

---

## Prompt construction

Each NPC prompt is assembled from parts, kept separate so they can be cached and budgeted:
- **System** — the rules of being an NPC: stay in character, never invent state, use tools to act. Stable across NPCs, so cacheable.
- **NPC profile** — identity, personality, goals, knowledge bounds. See [[Design/NPCs]].
- **World context** — shared lore the NPC can reference. See [[Design/World]].
- **Memory** — a retrieved/summarised slice of this NPC's history relevant to now.
- **Scene** — who is present, where, recent dialogue.

See [[Technical/Claude Integration]] for model choice, prompt caching, and cost.

---

## Memory strategy

Memory is owned by the simulation, not the context window. Open approach:
- Store events as structured records keyed to the NPC.
- Retrieve by recency + relevance into the prompt.
- Periodically summarise old memory into a compact "what this NPC believes" digest.

_To be filled in: retrieval method, summarisation cadence, relationship scoring._

---

## Tool use / action grammar

The model affects the world only through a fixed set of tools the engine defines and validates. This is the guardrail against hallucinated state. The exact tool set is _to be filled in_ — start minimal (speak, give_item, attack, move) and grow.

---

## Open Questions

- One model call per NPC, or one orchestrator that voices several? See [[Design/Dungeon Master]].
- How to keep multiple live NPCs consistent with each other.
- Streaming vs. full responses for latency.
