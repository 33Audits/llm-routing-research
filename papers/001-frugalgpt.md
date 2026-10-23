# FrugalGPT: How to Use Large Language Models While Reducing Cost and Improving Performance

- **Authors:** Lingjiao Chen, Matei Zaharia, James Zou
- **Submitted:** 2023
- **Paper:** https://arxiv.org/abs/2305.05176
- **Code/data:** See the paper and its linked project resources.

## Summary

FrugalGPT studies how to reduce the cost of querying collections of large language models while maintaining or improving quality. It organizes the problem around three strategies:

1. Prompt adaptation
2. LLM approximation
3. LLM cascades

The FrugalGPT cascade learns combinations of models and routing decisions for different queries. The paper reports that its approach can match the performance of a strongest individual model with substantially lower cost, or improve accuracy at a comparable cost.

## Routing relevance

The paper is an early and influential framing of routing as a joint quality-and-cost optimization problem. Its cascade perspective is especially relevant to systems that start with a cheaper model and escalate only when a confidence or quality criterion indicates that more capability is needed.

## Canonical sources

- arXiv abstract: https://arxiv.org/abs/2305.05176
- PDF: https://arxiv.org/pdf/2305.05176
