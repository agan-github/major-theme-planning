# OpenClaw Planning Skill Schema

This document defines the shared schema, interface contract, and orchestration rules for the editorial-planning skills bundled in this package.

## Shared planning object

All skills should reason around a single structured object called `planning_case`.

```json
{
  "meta": {},
  "request_context": {},
  "topic_spine": {},
  "source_grounding": {},
  "audience_entry": {},
  "package_architecture": {},
  "resource_requirements": {},
  "evaluation": {},
  "risk_flags": [],
  "recommendation": {}
}
```

## Core sections

### `topic_spine`
The shared editorial center.

Required for useful downstream planning:
- `theme_restatement`
- `planning_objective`
- `primary_angle`
- `central_question`
- `anchor_case_candidate`
- `core_evidence_logic`

### `source_grounding`
Owned by `practice_origin_topic_designer`.

### `audience_entry`
Owned by `audience_barrier_reframer`.

### `package_architecture`
Owned by `multi_format_amplification_planner`.

### `resource_requirements`
Owned by `collaborative_resource_orchestrator`.

### `evaluation`
Owned by `topic_evaluation_scorecard`.

### `recommendation`
Owned primarily by `major_theme_planning_orchestrator`.

## Common enums

### Maturity level
- `raw`
- `partial`
- `usable`
- `strong`
- `flagship_ready`

### Confidence
- `low`
- `medium`
- `high`

### Planning mode
- `lean`
- `full`
- `comparison`

## Default orchestration order

1. `major_theme_planning_orchestrator`
2. `practice_origin_topic_designer`
3. `audience_barrier_reframer`
4. `multi_format_amplification_planner`
5. `topic_evaluation_scorecard`
6. `collaborative_resource_orchestrator`

## Alternative order

Use a shorter path when the case already exists and only wording or rollout is weak:

1. `audience_barrier_reframer`
2. `practice_origin_topic_designer` for validation
3. `topic_evaluation_scorecard`
4. `multi_format_amplification_planner` if scaling is justified

## Minimum validation before package design

Do not build a large package unless these exist:

- `topic_spine.primary_angle`
- `topic_spine.central_question`
- `source_grounding.source_point.name`
- `audience_entry.best_entry_point.description`

## Minimum validation before execution

Do not recommend scaled execution unless these exist:

- `evaluation.final_verdict`
- `resource_requirements.resource_verdict`

## Writing rule

Every skill in this package should update only the fields it is responsible for. Do not overwrite other sections unless you are explicitly integrating or normalizing the case.
