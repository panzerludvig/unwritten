# Architecture

The high-level technical shape of Stories Yet Unwritten — the *eventual* architecture. The defining constraint: a language model drives the NPCs at runtime, but it must never be the source of truth for game state. See [[Design/Core Concepts]].

> For what is actually built and in scope right now, see [[Technical/Current Stage]]. The first playable version is narration-only text with no rules engine yet; everything below is the direction it grows toward.

## Tech Stack
- **Engine / Language:** _To be decided._
- **Platform(s):** _To be decided._
- **LLM provider:** Anthropic Claude — see [[Technical/Claude Integration]].

## The two halves

| Half | Role | Source of truth? |
|------|------|------------------|
| Rules engine | Deterministic game state, dice, combat, inventory | Yes |
| LLM layer | NPC voice, narration, intent interpretation | No |

The engine owns state and validates every change. The model only ever reads a curated slice of state and proposes actions. See [[Technical/NPC Simulation]].

## Key Systems

- [[Technical/NPC Simulation]] — how a Claude call becomes an in-character NPC response
- [[Technical/Game State]] — the authoritative model of the world
- [[Technical/Claude Integration]] — provider, models, prompt construction, cost

## External Tools & Libraries

- Anthropic SDK — _To be filled in._

## Open Questions

- Local-first single player, or server-authoritative?
- How is the rules engine exposed to the model — tool use, or a parsed action grammar?
- Latency budget per NPC turn?
