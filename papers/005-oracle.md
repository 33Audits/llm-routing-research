# ORACLE: Agentic AI Orchestrator Routing Via Adaptive Verifier Calibration Feedback

- **Authors:** Ritik Raj, Souvik Kundu, Dheemanth Joshi, Tushar Krishna
- **Submitted:** 24 July 2026; current arXiv version v4 revised 1 October 2026
- **Paper:** https://arxiv.org/abs/2607.22465
- **Code:** https://github.com/ORACLE-org/ORACLE

## Summary

ORACLE is a concurrency-aware online routing mechanism for heterogeneous agentic workloads. It adds an adaptive feedback loop on top of a model-selection policy: first classifying the task type, then dynamically assigning a task-appropriate verifier. A delayed-feedback strategy reduces verifier latency on the critical dispatch path.

The paper also introduces DISC, a post-routing dispatch scheduler. DISC reserves each task's peak KV-cache footprint at admission and can dispatch to an alternate backend when the expected reward from reduced wait time outweighs the accuracy loss from using a lower-quality backend.

The authors evaluate ORACLE on SWE-bench, tau2-bench, and Terminal-Bench 2.0, reporting up to a 7-point improvement in the accuracy-cost frontier over routing baselines. ORACLE with DISC improves program throughput by up to 1.8x.

## Routing relevance

This is directly relevant to model routing: it combines task-aware verifier selection, delayed feedback, and queue-aware backend scheduling. The distinction between model-selection quality and serving-system throughput is particularly useful for routers operating under concurrency and limited KV-cache capacity.

## Canonical sources

- arXiv abstract: https://arxiv.org/abs/2607.22465
- HTML: https://arxiv.org/html/2607.22465v4
- PDF: https://arxiv.org/pdf/2607.22465
- Code: https://github.com/ORACLE-org/ORACLE
