# Wake Reader Prompt

Use this when an agent starts a new session.

```text
Read the memory files in this order:

1. handoff.md
2. session_memory.md
3. memory.md
4. shared_journal.md
5. forget_list.md
6. memory_archive.md only if needed

Then report:
- current goal
- stable facts
- open threads
- risks
- next best action

Do not claim memory that is not written in the files.
```
