# Claude Integration

How Stories Yet Unwritten talks to Anthropic's API — model choice, prompt caching, and cost. Runtime LLM cost and latency are first-class engineering concerns here. See [[Technical/NPC Simulation]].

---

## Models

Pick per role rather than using one model everywhere. Current Claude models (verify against the live API docs before committing — the `claude-api` reference is authoritative):

| Role | Candidate | Why |
|------|-----------|-----|
| Lead NPCs / dramatic moments | Claude Opus 4.8 (`claude-opus-4-8`) | Strongest role-play and consistency |
| Everyday NPCs / narration | Claude Sonnet 4.6 (`claude-sonnet-4-6`) | Strong quality at lower cost |
| Background chatter / classification / routing | Claude Haiku 4.5 (`claude-haiku-4-5`) | Cheapest and fastest |

Routing by importance keeps cost down without flattening every character to the same quality.

---

## Prompt caching

NPC prompts share large stable prefixes (the system prompt, world lore, an NPC's static profile). Cache these so only the volatile tail (recent dialogue, current memory slice) is billed at full rate. Design the prompt so the stable parts come first. See [[Technical/NPC Simulation]] (Prompt construction).

---

## Cost & latency budget

- Set a per-turn token budget and a target latency before building, then measure against it.
- Track how many NPCs can be "live" at once — see the open question in [[Design/NPCs]].
- Prefer summarised memory over dumping history into context.

_To be filled in: concrete budgets once a prototype exists._

---

## Tool use

The engine exposes the action grammar to the model as Anthropic tool definitions. See [[Technical/NPC Simulation]] (Tool use / action grammar).

---

## Secrets

API keys never go in the repo. Use a local `.env` (already in [[Meta/Git|.gitignore]]). _To be filled in: config approach._

---

## Reference

When working on anything LLM-related, consult the project's `claude-api` reference for current model IDs, pricing, parameters, caching, and tool-use specifics rather than relying on memory.
