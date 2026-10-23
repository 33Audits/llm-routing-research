# Research Agenda

## Objective

Develop an evidence-driven router that selects a model and agent harness per task, minimizes unnecessary spend and latency, and preserves or improves verified outcome quality.

## Core hypotheses

### H1 — Task-conditioned routing beats one-model defaults

A router trained on comparable prior runs will achieve a better quality–cost frontier than sending every task to one fixed model.

### H2 — Harness configuration is part of the route

Selecting prompts, tools, context policies, retries, and verification alongside the model will explain more outcome variance than model selection alone.

### H3 — Selective escalation captures most frontier-model value

Starting with a lower-cost route and escalating only on low confidence or failed verification will preserve most high-end quality while reducing average cost.

### H4 — Verification signals outperform self-confidence alone

Tests, type checks, repository state, tool errors, and independent graders will produce safer stopping decisions than model-reported confidence.

## Baselines

1. Fixed strongest model
2. Fixed cheapest model
3. Rule-based router using task metadata
4. Learned one-shot router
5. Sequential cascade with confidence thresholds
6. Oracle route selected from completed candidate runs

## Evaluation dimensions

- **Quality:** acceptance criteria passed, task-specific grader, human review
- **Cost:** provider charges plus evaluator and retry costs
- **Latency:** end-to-end and time to first useful artifact
- **Reliability:** completion rate, retry rate, tool failure rate
- **Safety:** permission violations, secret exposure, destructive actions
- **Calibration:** confidence versus observed success
- **Stability:** performance under model, prompt, and task-distribution drift

## Minimum event schema

```json
{
  "task_id": "string",
  "task_family": "string",
  "task_features": {},
  "route_id": "string",
  "model": "string",
  "harness": {},
  "started_at": "timestamp",
  "latency_ms": 0,
  "input_tokens": 0,
  "output_tokens": 0,
  "cost_usd": 0.0,
  "retries": 0,
  "escalations": [],
  "verification": {},
  "quality_score": 0.0,
  "success": false,
  "feedback": null
}
```

## Experiment sequence

### Phase 1 — Observability

- Define task taxonomy and route identifiers.
- Capture complete run traces and costs.
- Establish deterministic checks where possible.
- Separate model cost from orchestration/evaluation cost.

### Phase 2 — Offline replay

- Build a dataset of representative completed tasks.
- Replay candidate routes against frozen task inputs.
- Prevent benchmark contamination and evaluator leakage.
- Produce Pareto frontiers by task family.

### Phase 3 — Shadow routing

- Let the candidate router choose routes without controlling production execution.
- Compare its choice with the actual route and oracle post-hoc route.
- Track expected gain, regret, and confidence calibration.

### Phase 4 — Guarded rollout

- Route low-risk task families first.
- Keep deterministic fallback routes.
- Escalate on failed checks, low confidence, or anomalous traces.
- Roll back automatically when quality or reliability crosses a threshold.

## Open questions

- What task features generalize without leaking answer or evaluator information?
- How much data is needed before per-task-family routing beats global routing?
- When is parallel sampling cheaper than sequential escalation after latency is priced in?
- How should delayed human feedback update route selection?
- How do we detect silent provider/model version changes?
- Which verification signals transfer across repositories and languages?
- How should privacy and data residency constrain candidate routes?

## Immediate next experiment

Select 30–50 repeated internal coding tasks across bug fixes, tests, refactors, and repository research. Run at least three accessible routes with a fixed acceptance test and identical task context. Report success rate, median cost, p50/p95 latency, escalation rate, and per-family Pareto winners.
