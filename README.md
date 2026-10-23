# LLM Routing Research

A curated, practical reading list for routing requests across large language models, with emphasis on quality, cost, latency, cascades, and evaluation.

## Papers

- [FrugalGPT: How to Use Large Language Models While Reducing Cost and Improving Performance](papers/001-frugalgpt.md) — prompt adaptation, model approximation, and LLM cascades.
- [RouterBench: A Benchmark for Multi-LLM Routing System](papers/002-routerbench.md) — a benchmark, dataset, and evaluation framework for multi-LLM routers.
- [Follow the Entities: A Corpus Map for Agentic Search](papers/003-corpusmap.md) — entity-based corpus navigation for agentic search and evidence discovery.
- [Detecting Functional Bugs in Smart Contracts through LLM-Powered and Bug-Oriented Composite Analysis](papers/004-promfuzz.md) — composite LLM analysis and bug-oriented fuzzing for smart contracts.
- [ORACLE: Agentic AI Orchestrator Routing Via Adaptive Verifier Calibration Feedback](papers/005-oracle.md) — adaptive verification, concurrency-aware routing, and queue-aware dispatch.
- [RouteLLM: Learning to Route LLMs with Preference Data](papers/006-routellm.md) — preference-trained routing between stronger and weaker models.
- [Large Language Model Routing with Benchmark Datasets](papers/007-benchmark-routing.md) — foundational benchmark-based model selection and routing.
- [RouterEval: A Comprehensive Benchmark for Routing LLMs](papers/008-routereval.md) — large-scale evaluation across thousands of model candidates.
- [The Workload–Router–Pool Architecture for LLM Inference Optimization](papers/009-workload-router-pool.md) — workload-, router-, and serving-pool-aware production architecture.

## Scope

This repository collects primary papers, implementation links, and short notes useful for building and evaluating model-routing systems. Notes are intentionally concise and distinguish claims made by the papers from practical takeaways.

## Contributing

Add one Markdown file per paper under `papers/`, preserve the numeric order, and include the canonical paper URL, authors, publication metadata, abstract, and implementation links where available.
