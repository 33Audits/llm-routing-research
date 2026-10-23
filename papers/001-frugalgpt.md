# FrugalGPT

**Paper:** *FrugalGPT: How to Use Large Language Models While Reducing Cost and Improving Performance*  
**Authors:** Lingjiao Chen, Matei Zaharia, James Zou  
**Submitted:** May 9, 2023  
**Reference:** arXiv:2305.05176

## Research question

How can an application answer natural-language queries with the best attainable task performance while keeping average inference cost within a user-defined budget?[1]

## Main framework

The paper groups cost-reduction techniques into three families:[1]

1. **Prompt adaptation** — shorten or restructure prompts, select fewer demonstrations, or batch compatible queries.
2. **LLM approximation** — reuse cached answers or approximate an expensive model with a cheaper fine-tuned model.
3. **LLM cascade** — query models sequentially and stop when a response is sufficiently reliable.

## Cascade design

The cascade has two key learned components:[1]

- a **generation scoring function** that estimates whether a model's answer is reliable for the query;
- a **router** that chooses the ordered model list and reliability thresholds under a cost constraint.

Conceptually:

```text
answer = cheap_model(query)
if confidence(query, answer) >= threshold_1:
    return answer

answer = stronger_model(query)
if confidence(query, answer) >= threshold_2:
    return answer

return strongest_model(query)
```

The important insight is that routing and stopping are coupled. A cheap first model only saves money when the confidence estimator can identify successful answers without introducing unacceptable false positives.

## Reported results

The authors report that FrugalGPT can match the best individual LLM's performance with up to a 98% inference-cost reduction, or improve accuracy by up to 4% at the same cost.[1] These are paper-specific experimental results, not general guarantees; current models, prices, task distributions, and evaluation methods must be re-benchmarked.

## Relevance to a modern router

### Ideas to retain

- Express route selection as constrained optimization rather than a static preference list.
- Learn from task-level outcomes because models have heterogeneous strengths.
- Make escalation conditional on estimated answer reliability.
- Evaluate cost and quality jointly.

### Extensions needed for agentic coding workflows

FrugalGPT focuses primarily on query answering. A coding or tool-using agent router should expand the state and objective:

- route the complete harness, not only the base model;
- include tool-call correctness, test results, and verification evidence;
- model multi-step cost, retries, and context growth;
- distinguish recoverable failures from silent quality failures;
- account for provider availability, rate limits, privacy, and repository sensitivity;
- evaluate task completion rather than answer similarity alone.

## Risks and failure modes

1. **Miscalibrated confidence:** a cheap model can produce a fluent but wrong answer that prevents escalation.
2. **Distribution drift:** thresholds trained on old tasks or old model versions degrade silently.
3. **Evaluator leakage:** routing can overfit to a benchmark or automated judge.
4. **Tail latency:** sequential escalation can cost more time than selecting a stronger route initially.
5. **Hidden harness differences:** comparing model names while changing prompts or tools confounds results.
6. **Price churn:** an economically optimal route can change without any quality change.

## Experiments derived from the paper

- Compare static routing, learned one-shot routing, and sequential cascades on the same task set.
- Plot quality–cost and quality–latency Pareto frontiers rather than reporting one aggregate winner.
- Calibrate escalation confidence and measure false-accept versus false-escalation rates.
- Retrain routes on rolling windows and test robustness to model/version drift.
- Run shadow evaluations before promoting a new routing policy.
- Add a no-routing baseline using one strong model with an identical harness.

## Sources

[1] https://arxiv.org/abs/2305.05176 — FrugalGPT: How to Use Large Language Models While Reducing Cost and Improving Performance
