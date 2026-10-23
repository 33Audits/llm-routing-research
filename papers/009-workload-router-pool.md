# The Workload–Router–Pool Architecture for LLM Inference Optimization

- **Authors:** Huamin Chen, Xunzhuo Liu, Bowei He, Fuyuan Lyu, Yankai Chen, Xue Liu, Yuhan Liu, Junchen Jiang
- **Submitted:** March 2026; current arXiv version v2 dated 8 April 2026
- **Paper:** https://arxiv.org/abs/2603.21354
- **HTML:** https://arxiv.org/html/2603.21354v2

## Summary

This vision paper proposes the Workload–Router–Pool (WRP) architecture for reasoning about production LLM inference. It separates three interacting dimensions:

- **Workload:** what the system serves, such as chat, agents, single-turn, multi-turn, warm, cold, prefill-heavy, or decode-heavy traffic.
- **Router:** how requests are dispatched, including semantic rules, online adaptation, reinforcement learning, and quality-aware cascades.
- **Pool:** where inference runs, including heterogeneous GPUs, disaggregated prefill/decode, and KV-cache topologies.

The paper maps prior vLLM Semantic Router work onto a 3×3×3 interaction matrix and proposes research directions at the intersections.

## Routing relevance

WRP is useful because it treats routing as a systems problem rather than an isolated model-selection classifier. It makes workload characteristics and backend constraints first-class routing inputs, which is important for latency, throughput, KV-cache capacity, and cost-aware production routing.

## Canonical sources

- arXiv abstract: https://arxiv.org/abs/2603.21354
- HTML: https://arxiv.org/html/2603.21354v2
- PDF: https://arxiv.org/pdf/2603.21354
