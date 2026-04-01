# Install and Routing Notes

This note is designed to help you install the package cleanly and activate it in OpenClaw.

## Single-agent setup

1. Copy `workspace-planner/` into your desired OpenClaw workspace path.
2. Point `agents.defaults.workspace` to that location.
3. Start OpenClaw and complete the bootstrap ritual.
4. Run one test prompt to verify the six skills are visible from `<workspace>/skills`.

## Multi-agent setup

Use separate workspaces when you want isolated personas and sessions.

Suggested mapping:

- `planner` -> `~/.openclaw/workspace-media-planner`
- `research` -> `~/.openclaw/workspace-media-research`
- `ops` -> `~/.openclaw/workspace-media-ops`

Suggested role split:

- `planner`: final user-facing integrated planner
- `research`: source, archive, evidence, and comparison support
- `ops`: feasibility, rollout, resource, and coordination checks

## CLI workflow

Create isolated agents with the CLI if you prefer that flow:

```bash
openclaw agents add planner --workspace ~/.openclaw/workspace-media-planner
openclaw agents add research --workspace ~/.openclaw/workspace-media-research
openclaw agents add ops --workspace ~/.openclaw/workspace-media-ops
```

Then add bindings as needed, for example:

```bash
openclaw agents bind --agent planner --bind telegram:editorial
openclaw agents bind --agent research --bind telegram:research
openclaw agents bind --agent ops --bind telegram:ops
```

Inspect bindings with:

```bash
openclaw agents bindings --json
```

## Workspace files

The core workspace files expected by this package are:

- `AGENTS.md`
- `SOUL.md`
- `USER.md`
- `IDENTITY.md`
- `TOOLS.md`
- `HEARTBEAT.md`
- `BOOTSTRAP.md`
- `MEMORY.md`

The `skills/` folder inside the workspace contains the custom planning skills.

## Practical advice

- Start with the single-agent workspace first.
- Only split into multiple agents when you need isolation of persona, memory, or channel routing.
- Keep `AGENTS.md`, `SOUL.md`, and `TOOLS.md` concise because they are injected frequently.
- Keep `BOOTSTRAP.md` short. Remove it after the first-run ritual if you do not want it to continue appearing.
