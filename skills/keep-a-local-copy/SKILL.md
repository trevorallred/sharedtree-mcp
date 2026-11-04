---
name: keep-a-local-copy
description: Download the user's SharedTree articles as local Markdown files and search them with grep. Use when the user wants a local copy, offline access, or to grep or search their SharedTree from the command line.
---

# Keep a local copy

Requires a shell and Node.js. Use the published CLI; never hand-roll API calls.

1. Check sign-in: `npx @sharedtree/cli status`. If it reports no login, ask the user to run `npx @sharedtree/cli login` (it opens a browser to approve access). On a machine without a browser, the user can set `SHAREDTREE_TOKEN` to an access token created at sharedtree.com instead.
2. Pull: `npx @sharedtree/cli pull ~/sharedtree` (or the folder the user prefers). Run inside an existing copy, `pull` updates that copy in place. Add `--notes` to include notes not yet organized.
3. Search the copy with `grep -ri "<term>" ~/sharedtree` (or `rg`). Files are Markdown with links between articles.
4. Pull again any time; only changes download, and anything forgotten in SharedTree is removed locally.

Exit codes: 3 means sign in again, 6 means retry later.
