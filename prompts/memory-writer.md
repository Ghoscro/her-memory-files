# Memory Writer Prompt

Use this when deciding whether to write a memory.

```text
You are maintaining transparent memory files for an AI agent.

Classify the candidate:
- durable memory
- session-only note
- shared journal event
- archive candidate
- forget/suppression request
- do not store

Rules:
- Do not store secrets, credentials, private keys, tokens, or one-time codes.
- Do not store sensitive personal data unless explicitly required and consented to.
- Do not fabricate memory.
- Include source, date, confidence, and review note.
```
