---
name: import-my-memories
description: Copy what this assistant already knows about the user into SharedTree. Use when the user asks to import, move, sync or back up their memories or profile into SharedTree.
---

# Import my memories

1. Gather the durable facts you already know about the user from your own memory and this conversation: people and how they relate to the user, places, work and projects, preferences, routines, important dates and past decisions.
2. Leave out secrets, credentials, financial or government identifiers, and anything the user has asked you not to keep. When unsure whether something is sensitive, ask.
3. Write each fact as a self-contained statement that uses names, not pronouns. Add `observedAt` (an EDTF date such as 2026 or 2026-11) when you know when it was true, and `subjects` naming who or what it is about.
4. Call `search` first for anything that may already be saved, to avoid duplicates.
5. Save with `remember`, batching up to 50 observations per call, each with a stable `idempotencyKey` so a retry never duplicates it.
6. Tell the user how many facts you saved and suggest running the organize-my-tree skill afterwards.
