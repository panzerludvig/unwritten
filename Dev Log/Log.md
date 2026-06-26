# Dev Log

Chronological record of what was discussed, decided, and *why*. The goal is to preserve reasoning, not just events. See the [[Codex]] for how this is used.

---

## 2026-06-26 — Project created

- Scaffolded the Stories Yet Unwritten vault, mirroring the structure and conventions of the Delegate project (Codex-governed Obsidian vault: Design / Technical / Dev Log / Meta / Assets).
- **Concept:** a D&D-style RPG whose NPCs are simulated by Claude rather than scripted.
- **Foundational decision:** the language model role-plays and proposes; a deterministic rules engine remains the source of truth for all game state. This was made the first Core Concept because it shapes everything downstream (fairness, debuggability, no hallucinated state). See [[Design/Core Concepts]] and [[Technical/Architecture]].
- Added an "LLM Standards" Codex entry, since runtime model cost/latency is a real engineering constraint not present in Delegate. See [[Technical/Claude Integration]].
- Named the project **Stories Yet Unwritten** (short handle: "Unwritten"), after exploring options around adventure, freedom, and openness; landed on a name evoking emergent, player-authored narrative rather than escapism. The vault was initially scaffolded under the placeholder "Animus" and renamed. No Git remote yet.
- Most notes are stubs with `_To be filled in._` sections — the framework is in place, the content is next.
