# Architecture Overview

AI Influencer Studio is an AI character and interaction system organized around deterministic workflow boundaries, human approval, and strict separation between reasoning, routing, execution, and private source data.

## Core Roles

- ChatGPT, Claude, and Codex: reasoning, planning, code review, documentation, and controlled implementation support.
- n8n: workflow routing, state transitions, timing, webhook handling, and phase-one n8n-native persistence operations.
- OpenAI: text response generation when called by approved workflow nodes.
- ComfyUI: image execution only. It is not the reasoning brain and is not part of Workflow A.
- Mission Control: prototype/control-plane surface. It is not runtime authority and does not prove that runtime workflows are live.

## Runtime Principles

- `character_id` is first-class in payloads, keys, logs, prompts, and workflow contracts.
- Workflows should be deterministic wherever possible.
- Runtime artifacts must be versioned and rollbackable.
- No agent or workflow should auto-execute sensitive actions without explicit approval.
- SFW and private policy domains must remain separated.
- Workbook-style data must be append-safe and must not be directly rewritten by agents.

## Phase-One Data Boundary

Phase one keeps text DM runtime state in n8n-native persistence. Workflow A local validation used a Data Table-compatible local runtime for:

- `users` persistence for user state and interaction counters
- `logs` persistence for interaction history

No public context file should expose private workbook rows, character source files, or live credentials.
