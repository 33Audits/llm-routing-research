# RouteLLM: Learning to Route LLMs with Preference Data

- **Authors:** Isaac Ong, Amjad Almahairi, Vincent Wu, Wei-Lin Chiang, Tianhao Wu, Joseph E. Gonzalez, M. Waleed Kadous, Ion Stoica
- **Submitted:** 26 June 2024; current arXiv version v4 revised 23 February 2025
- **Paper:** https://arxiv.org/abs/2406.18665
- **Code:** https://github.com/lm-sys/RouteLLM

## Summary

RouteLLM trains routers to dynamically select between a stronger and weaker LLM using human preference data and data augmentation. The goal is to balance response quality against inference cost. The paper reports substantial cost reductions without compromising response quality and shows transfer across different strong/weak model pairings.

## Routing relevance

This is a key preference-supervised routing paper. It demonstrates that a router can learn a quality boundary from preference data instead of relying only on benchmark scores or handcrafted thresholds. Its transfer results are particularly relevant when the underlying model pool changes over time.

## Canonical sources

- arXiv abstract: https://arxiv.org/abs/2406.18665
- HTML: https://arxiv.org/html/2406.18665v4
- PDF: https://arxiv.org/pdf/2406.18665
- Code: https://github.com/lm-sys/RouteLLM
