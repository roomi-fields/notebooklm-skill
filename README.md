<div align="center">

# NotebookLM Skill for Claude Code

**A Claude Code / Agent Skill that lets your AI agent query your Google NotebookLM notebooks — citation-backed, source-grounded answers from your own documents, plus notebook / source / Studio management. Zero hallucinations: answers come only from your sources.**

</div>

---

This skill drives the [`@roomi-fields/notebooklm-mcp`](https://github.com/roomi-fields/notebooklm-mcp) engine — the fastest, most complete NotebookLM automation (dual internal-RPC + browser transport, 33 REST endpoints, full Studio generation, multi-account). It works two ways, whichever your session already has:

- **notebooklm MCP tools** if configured, or
- the engine's **HTTP REST API** via the bundled `scripts/nblm.sh`.

## What it enables

- **Citation-backed Q&A** — ask a notebook a question, get an answer grounded in your sources with the exact cited passages.
- **Studio generation** — audio overview, report, video, infographic, presentation, data table, flashcards, quiz, mind map.
- **Source discovery** — web/Drive research to find and import new sources.
- **Research at scale** — the daily-quota-aware batch-to-cache pattern (ingest once with NotebookLM, then retrieve offline, unlimited).

## Install

**As a plugin** (recommended — gets the skill *and* the MCP server):

```text
/plugin marketplace add roomi-fields/claude-plugins
/plugin install notebooklm@roomi-fields
```

**Or just the skill** — copy `skills/notebooklm/` into your skills folder:

```bash
git clone https://github.com/roomi-fields/notebooklm-skill.git
cp -r notebooklm-skill/skills/notebooklm ~/.claude/skills/
```

Then log in to Google once (a visible Chrome window opens):

```bash
notebooklm-mcp-setup-auth
```

## Use

Just ask your agent things like:

> "Ask my *Thesis* notebook what the main critiques of the framework are, with citations."

The skill handles auth checks, transport selection, citation formatting, and the quota-aware batch pattern. See [`skills/notebooklm/SKILL.md`](./skills/notebooklm/SKILL.md).

## License

MIT — see [LICENSE](./LICENSE). Built by [@roomi-fields](https://github.com/roomi-fields).
