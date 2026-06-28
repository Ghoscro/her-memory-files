# Her Memory Files

Transparent memory files for AI agents.

Created by **Micker / Ghoscro** for **HerLove**, as part of the **Micker Method**.

Origin product: **HerLove** ([herlove.ai](https://herlove.ai)).

This is a public-safe version. Examples use mock data; private memory, user data, credentials, deployment details, and full automation loops are intentionally excluded.

## Who This Is For

Use this if you are building an AI agent that needs memory people can actually inspect:

- coding agents that resume long-running work
- customer-support or research agents that need audit trails
- personal assistants that must not fake continuity
- small teams that want memory before adding a database

## Why

Most AI-agent memory systems become opaque very quickly:

- Vector search can retrieve something, but humans cannot easily inspect the memory.
- Session summaries drift.
- Agents may claim to remember things that were never written down.
- Users cannot tell what the agent actually knows.

Her Memory Files uses plain files instead:

```text
memory.md
session_memory.md
shared_journal.md
memory_archive.md
forget_list.md
handoff.md
```

The point is not to replace every database or RAG system. The point is to give the agent and the human a transparent memory floor.

This pairs well with [Her LOOP-SOP](https://github.com/Ghoscro/her-loop-sop): LOOP-SOP keeps the work moving, while Her Memory Files keeps the continuity honest.

## File Roles

| File | Purpose |
| --- | --- |
| `memory.md` | Durable facts, preferences, decisions, and long-term context |
| `session_memory.md` | Current session progress, open threads, and next actions |
| `shared_journal.md` | Relationship or collaboration events that matter over time |
| `memory_archive.md` | Old or compressed memories that should not stay hot |
| `forget_list.md` | User-requested removals and memory suppression notes |
| `handoff.md` | A compact state packet for another agent or future session |

## Core Rules

1. If it was not written down, do not pretend it is remembered.
2. If the user says "remember this", write it with date and source.
3. If the user says "forget this", remove it from hot memory and record the request.
4. Keep current-session work separate from long-term memory.
5. Archive old details before they turn into noise.
6. Use mock data in public demos.

## Minimal Memory Flow

```text
Wake -> Read memory files -> Work -> Write session notes -> Promote durable facts -> Handoff or sleep
```

## Quick Start

Copy the templates:

```text
templates/memory.md
templates/session_memory.md
templates/shared_journal.md
templates/memory_archive.md
templates/forget_list.md
templates/handoff.md
```

Then use the prompts in [`prompts/`](prompts/) to guide agent behavior.

## When To Write Memory

Write memory when:

- A stable user preference appears.
- A project decision is made.
- A repeated mistake is discovered.
- A long-running task reaches a checkpoint.
- The user explicitly asks the agent to remember or forget something.

Do not write memory when:

- The statement is private and not needed later.
- The agent is guessing.
- The content is a secret, token, password, private key, or one-time code.
- The user is venting and has not consented to long-term storage.

## Public-Safe Example

See [`examples/mock-agent-memory/`](examples/mock-agent-memory/) for a fake agent project using the file layout.

## License

MIT
