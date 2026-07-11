# nika-starter

Repeatable AI jobs as files. This template gives you a working setup in
about a minute: one proven workflow, editor wiring, agent instructions,
and CI that re-checks every workflow on every push.

## Use it

1. Click **Use this template** (top right).
2. Install the engine (single binary):

```bash
brew install supernovae-st/tap/nika
```

3. Prove the setup, offline, zero keys:

```bash
nika check daily-brief.nika.yaml
nika run  daily-brief.nika.yaml --model mock/echo
```

4. Real local run (got [Ollama](https://ollama.com)?):

```bash
nika run daily-brief.nika.yaml
```

You get `brief.md`: the top Hacker News stories, briefed by a local
model, with a hash-chained trace in `.nika/traces/`. Verify it:

```bash
nika trace verify .nika/traces/*.ndjson
```

## What's inside

| File | What it does |
|---|---|
| `daily-brief.nika.yaml` | the proven starter workflow: fetch feed, reshape, brief with a local model, save |
| `AGENTS.md` | teaches YOUR coding agent (Claude Code, Cursor, Codex...) how to author and check workflows here |
| `.agents/skills/` | the authoring skill, picked up by agents that read skills |
| `.vscode/` | schema wiring: validation, completion and hover for `*.nika.yaml` |
| `.github/workflows/nika.yml` | CI re-checks every workflow on every push, statically, zero secrets |

Everything except the workflow and this README is written by `nika init`
from the released binary, so it stays current with the engine.

## Make it yours

```bash
nika new                      # guided authoring on the terminal
nika examples                 # 25+ embedded, runnable examples
nika explain my.nika.yaml     # what a file does, before you run it
```

Docs: https://docs.nika.sh · Engine (AGPL-3.0): https://github.com/supernovae-st/nika
