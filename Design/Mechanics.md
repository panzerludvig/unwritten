# Mechanics

The rules of play — what the deterministic engine adjudicates, independent of the language model. See [[Design/Core Concepts]] for why this separation matters.

> Not in the current build. The first playable version has **no dice and no mechanical resolution** — the DM decides outcomes by judgement. See [[Technical/Current Stage]]. This note describes mechanics as they will be added once play shows they're needed.

---

## Ruleset Basis

_To be decided: custom system vs. SRD 5e (Open Game License)._ Starting assumption is the D&D 5e SRD as a familiar, well-documented baseline.

## Core Resolution

- Ability checks, saving throws, attack rolls — d20 + modifiers vs. a DC or AC
- Advantage / disadvantage
- _To be filled in._

## Character Stats

_To be filled in._ See [[Design/Characters]].

## Combat

_To be filled in._ See [[Design/Encounters]].

## Skills & Checks

_To be filled in._

## How the LLM interacts with mechanics

The model proposes an action in natural language; the engine maps it to a mechanical resolution, rolls, and returns the outcome for the model to narrate. The model never rolls its own dice. See [[Technical/NPC Simulation]].
