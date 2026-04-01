# OpenClaw Media Planning System

This package is a ready-to-use OpenClaw workspace set for major-theme editorial planning in international communication.

## Included

- `workspace-planner/` — main planner workspace
- `workspace-planner/skills/` — six custom planning skills
- `optional-workspaces/research/` — optional evidence and source support workspace
- `optional-workspaces/ops/` — optional feasibility and rollout workspace
- `docs/openclaw-planning-skill-schema.md` — shared planning object schema
- `docs/install-and-routing.md` — install, routing, and activation notes
- `openclaw.single-agent.example.json5` — simplest single-agent config example
- `openclaw.multi-agent.example.json5` — optional multi-agent config example

## What this system does

The main planner workspace is designed to:

1. diagnose the planning state
2. identify a source-grounded topic spine
3. reframe the topic for target audiences
4. design a multi-format package
5. check resource and coordination feasibility
6. score and prioritize the topic

## Skills included

1. `major_theme_planning_orchestrator`
2. `practice_origin_topic_designer`
3. `audience_barrier_reframer`
4. `multi_format_amplification_planner`
5. `collaborative_resource_orchestrator`
6. `topic_evaluation_scorecard`

## Recommended install

### Option A: single agent

Copy `workspace-planner/` to your target workspace path:

```bash
mkdir -p ~/.openclaw
cp -R workspace-planner ~/.openclaw/workspace-media-planner
```

Then use `openclaw.single-agent.example.json5` as the basis for your OpenClaw config.

### Option B: multi-agent

Copy all three workspaces:

```bash
mkdir -p ~/.openclaw
cp -R workspace-planner ~/.openclaw/workspace-media-planner
cp -R optional-workspaces/research ~/.openclaw/workspace-media-research
cp -R optional-workspaces/ops ~/.openclaw/workspace-media-ops
```

Then use `openclaw.multi-agent.example.json5` as the basis for your config and add channel bindings with the CLI.

## Workspace notes

- The main working workspace is `workspace-planner/`.
- The optional workspaces are intentionally lighter and can be used only when you want isolated roles.
- `BOOTSTRAP.md` is included so the first run can confirm identity and usage rules. After the ritual, it can be removed.
- `MEMORY.md` is included as curated long-term memory. Keep it concise.

## Suggested first-run sequence

1. install the main workspace
2. start OpenClaw with the single-agent config
3. complete the short bootstrap ritual
4. test one real planning prompt
5. only then add the optional research and ops workspaces if you want role isolation
