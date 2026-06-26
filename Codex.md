# Codex

The Codex is the authoritative reference for working on Stories Yet Unwritten. It describes the project's workflow, standards, and philosophy. When starting a session, point Claude here for context. Each entry should be a short summary that links to a dedicated note where the detail lives — the Codex itself stays concise. See [[Meta/Codex Guidelines]] for how to maintain it.

---

## Home

The vault's front page. Its purpose is human navigation — a quick orientation and links to the main sections. It is not a Claude briefing document. See [[Meta/Home]] for what belongs there and how to keep it current.

---

## Documentation

Everything about this project — design decisions, lore, technical architecture, progress — lives in this Obsidian vault. If it isn't written down here, it doesn't exist. Claude should read relevant notes before making suggestions, and flag anything that seems undocumented.

See [[Meta/Obsidian]] for how to work with this vault.

---

## The Premise

Stories Yet Unwritten is a tabletop-style RPG whose non-player characters are simulated by a large language model rather than scripted. The design and technical decisions are in service of making those characters feel like genuine, consistent agents. See [[Design/Overview]] for the concept and [[Technical/NPC Simulation]] for how it works.

---

## Versioning

All versioning is done in Git. Every meaningful change — to code, design, or notes — should be committed. See [[Meta/Git]] for workflow and conventions.

---

## Workflow

_To be filled in._

---

## Dev Log

At the end of a session, the user will ask Claude to summarize the conversation in [[Dev Log/Log]] — what was discussed, what was decided, and crucially, *why*. The goal is not to record what happened but to preserve the reasoning so that if a decision is questioned later, there is a record to return to rather than having to reconstruct the thinking from scratch.

---

## Recurring Tasks

The user declares session boundaries explicitly (e.g. "this is a new session" or "let's wrap up"). At both points, Claude should check [[Meta/Recurring Tasks]] and remind the user of anything overdue based on its interval and last-done date.

---

## Quick Notes

If the user asks to add a "quick note", append it to [[Meta/Quick Notes]] with a timestamp. The purpose is to capture thoughts that come up during the day without interrupting the current task, so they can be explored in detail later.

---

## Code Standards

_To be filled in._

---

## LLM Standards

Stories Yet Unwritten depends on a language model at runtime, so prompt design, context budgeting, and cost are first-class engineering concerns, not afterthoughts. Any decision that affects what gets sent to the model — or how often — should be reasoned about and documented. See [[Technical/Claude Integration]].

---

## Suggestions

If Claude has a suggestion — an alternative approach, a potential addition, something that may have been overlooked — it should be written in [[Meta/Suggestions]]. Suggestions are not next steps or instructions, just options worth considering. Each suggestion must include a timestamp and a reference to what prompted it.

After completing any instruction, if new suggestions were added, Claude should say so inline (e.g. "1 new suggestion" or "3 new suggestions"). Suggestions can be retrieved by recency, by topic, or browsed directly in the note.

---

## Todo

Concrete, actionable tasks live in [[Meta/Todo]] — as distinct from [[Meta/Suggestions]], which are options to consider rather than things to do. Either Claude or the user can add items; remove them once done.
