---
name: organize-my-tree
description: Organize the user's SharedTree notes into articles. Use when the user asks to organize, curate, tidy or clean up their SharedTree memory, or when curation_status shows notes waiting.
---

# Organize my Tree

SharedTree's server owns the curation rules (article size, linking, what goes where). This skill only starts the run; follow the instructions the server returns.

1. Call `curation_status` and tell the user how many notes are waiting. If none, stop.
2. If your client supports MCP prompts, run the `organize-my-tree` prompt. Otherwise call `curation_claim` and follow the instructions it returns exactly.
3. Organize the claimed notes into articles, then call `curation_submit` with the same `leaseId`.
4. On a `version_conflict` or validation error, fix what the error names and resubmit with the same `leaseId`.
5. Repeat while notes remain and the user wants to continue. Finish with a one-line summary of what changed.
