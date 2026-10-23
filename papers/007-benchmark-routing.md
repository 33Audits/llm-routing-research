# Large Language Model Routing with Benchmark Datasets

- **Authors:** Tal Shnitzer, Anthony Ou, Mírian Silva, Kate Soule, Yuekai Sun, Justin Solomon, Neil Thompson, Mikhail Yurochkin
- **Submitted:** 27 September 2023
- **Paper:** https://arxiv.org/abs/2309.15789

## Summary

This paper formulates LLM selection as a routing problem: given a collection of models and a new task, select the model expected to perform best. It repurposes benchmark datasets to train router models and reduces the selection problem to a collection of binary classification tasks.

The authors show that learned routing can improve performance over using any single model for all tasks, while also examining the limitations of learning routers from benchmark data.

## Routing relevance

This is foundational work for benchmark-based routing. It establishes a useful baseline and highlights a central risk: benchmark-derived routing signals may not transfer cleanly to new tasks, datasets, or model pools.

## Canonical sources

- arXiv abstract: https://arxiv.org/abs/2309.15789
- HTML: https://arxiv.org/html/2309.15789v1
- PDF: https://arxiv.org/pdf/2309.15789
