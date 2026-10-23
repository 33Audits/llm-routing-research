# LLM Routing Research

Open research notes, experiments, and design guidance for routing tasks across language models under quality, cost, and latency constraints.

## Why this repository exists

A production router should not default every task to one frontier model. It should select a route using evidence from comparable prior runs, escalate when confidence is low, and continuously measure whether routing decisions improve outcomes.

The initial research anchor is **FrugalGPT**, which formulates model selection as a budget-aware optimization problem and studies prompt adaptation, model approximation, and sequential model cascades. Its reported experiments show that a learned cascade can match the best individual model at substantially lower cost, or improve accuracy under the same budget.[1]

## Research principles

1. **Route by task evidence, not provider reputation.** Compare candidate routes on representative task families.
2. **Optimize a vector, not a single score.** Track quality, cost, latency, reliability, and privacy constraints.
3. **Escalate selectively.** Start with the cheapest route likely to succeed, then escalate only when confidence or verification fails.
4. **Measure the whole harness.** Prompts, tools, context, retries, verification, and orchestration are part of the route.
5. **Log every decision.** Preserve inputs, selected route, model/harness configuration, trace, cost, latency, result, and evaluator outcome.
6. **Promote through evaluation.** Shadow-test route changes before they affect production traffic.

## Repository layout

- [`papers/001-frugalgpt.md`](papers/001-frugalgpt.md) — budget-aware model cascades, confidence scoring, and escalation
- [`papers/002-routerbench.md`](papers/002-routerbench.md) — benchmark and evaluation framework for multi-LLM routers
- [`research-agenda.md`](research-agenda.md) — hypotheses, baselines, metrics, rollout phases, and open questions
- [`bibliography.bib`](bibliography.bib) — citation metadata

## Working definition of routing

A route is more than a model name:

```text
route = model
      + system/prompt strategy
      + context policy
      + tools and permissions
      + orchestration pattern
      + retry/escalation policy
      + verification policy
```

The router maps a task and operating constraints to a route, observes the result, and records feedback for future decisions.

## Initial evaluation schema

For every run, capture:

- task family and difficulty signals
- route and model selected
- prompt/context/tool configuration
- execution trace and retries
- wall-clock latency
- input/output tokens and monetary cost
- automated checks and human quality score
- route success/failure and escalation reason

## Contributing

Add new paper notes under `papers/`, include primary-source links, distinguish reported results from our interpretation, and translate each paper into falsifiable experiments.

## License

MIT. See [`LICENSE`](LICENSE).

## Sources

[1] https://arxiv.org/abs/2305.05176 — FrugalGPT: How to Use Large Language Models While Reducing Cost and Improving Performance
