# RouterBench: A Benchmark for Multi-LLM Routing System

- **Authors:** Qitian Jason Hu, Jacob Bieker, Xiuyu Li, Nan Jiang, Benjamin Keigwin, Gaurav Ranganath, Kurt Keutzer, Shriyash Kaustubh Upadhyay
- **Submitted:** 18 March 2024; revised 28 March 2024 (v2)
- **Paper:** https://arxiv.org/abs/2403.12031
- **Code and data:** https://github.com/withmartian/routerbench

## Summary

RouterBench presents an evaluation framework for multi-LLM routing systems. It addresses the absence of a standardized benchmark for comparing routers that balance model quality, cost, and other serving constraints.

The paper introduces a dataset containing more than 405,000 inference outcomes from representative LLMs, a theoretical framework for LLM routing, and comparative experiments across routing approaches. The authors position the benchmark as infrastructure for developing and evaluating more economically viable LLM deployments.

## Routing relevance

RouterBench is useful as an evaluation complement to cascade-oriented work such as FrugalGPT. It shifts attention from proposing a routing policy alone to measuring routers consistently across datasets, candidate models, and objective tradeoffs.

## Canonical sources

- arXiv abstract: https://arxiv.org/abs/2403.12031
- HTML: https://arxiv.org/html/2403.12031v2
- PDF: https://arxiv.org/pdf/2403.12031
- Code and data: https://github.com/withmartian/routerbench
