# SharedTree MCP server

SharedTree is one memory for all your AI assistants. Tell one assistant something worth keeping, and every assistant you connect can recall it later. Notes are organized over time into readable articles that you can review, correct, export or delete at [sharedtree.com](https://sharedtree.com).

This repository describes the hosted MCP server. The server itself is operated by SharedTree; there is nothing to install.

## Server

- **URL:** `https://mcp.sharedtree.com/mcp`
- **Transport:** Streamable HTTP (stateless)
- **Auth:** OAuth 2.1 with dynamic client registration and PKCE. Clients discover the authorization server from `https://mcp.sharedtree.com/.well-known/oauth-protected-resource`. Command-line clients can use a personal access token (`st_pat_…`) created at sharedtree.com instead.

## Tools

| Tool | What it does |
| --- | --- |
| `search` | Find articles and recent notes in your Tree |
| `fetch` | Read one article or note in full |
| `remember` | Save new facts as notes |
| `correct` | Record a correction to an article or note |
| `forget` | Permanently delete an article or note (after confirming with you) |
| `curation_status`, `curation_claim`, `curation_submit` | Let an assistant organize saved notes into articles |
| `export` | Export your Tree |
| `ping` | Check the connection |

Full reference: [sharedtree.com/docs/api](https://sharedtree.com/docs/api) · OpenAPI: [sharedtree.com/openapi.json](https://sharedtree.com/openapi.json)

## Plugin and skills

This repository is also an installable plugin: `.mcp.json` connects the server, and `skills/` adds three workflows that call SharedTree's tools:

- **organize-my-tree**: organize saved notes into articles
- **import-my-memories**: copy what an assistant already knows about you into SharedTree
- **keep-a-local-copy**: download your Tree as Markdown with `@sharedtree/cli` and grep it

The skills only orchestrate; the server owns the rules and instructions.

## Set up

Add `https://mcp.sharedtree.com/mcp` as a custom connector in your assistant, then sign in to SharedTree and approve access. Step-by-step guides for Claude, ChatGPT, Grok, Cursor, Claude Code and other clients: [sharedtree.com/connect](https://sharedtree.com/connect).

## Try it

1. Connect the server and sign in. Sign-up is open (Google or an emailed code).
2. In a new chat: "Remember that my test cabin at Bear Lake sleeps eight."
3. In another new chat: "How many people can my cabin sleep?" The assistant should answer eight.

## Local copy

Keep a Markdown copy of your Tree on your computer: `npx @sharedtree/cli login`, then `npx @sharedtree/cli pull`.

## Privacy and support

- Privacy policy: [sharedtree.com/privacy](https://sharedtree.com/privacy)
- Questions or problems: open an issue in this repository.
