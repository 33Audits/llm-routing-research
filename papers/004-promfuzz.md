# Detecting Functional Bugs in Smart Contracts through LLM-Powered and Bug-Oriented Composite Analysis

- **Authors:** Binbin Zhao, Xingshuang Lin, Yuan Tian, Saman Zonouz, Na Ruan, Jiliang Li, Raheem Beyah, Shouling Ji
- **Submitted:** 31 March 2025
- **Paper:** https://arxiv.org/abs/2503.23718
- **HTML:** https://arxiv.org/html/2503.23718v1
- **System:** PromFuzz

## Summary

This paper presents PromFuzz, an automated and scalable system for detecting functional bugs in smart contracts. It uses an LLM-driven dual-agent prompt-engineering strategy to identify potentially vulnerable functions, generates invariant checkers from extracted business-logic information, and applies bug-oriented fuzzing to the targeted functions.

The paper evaluates PromFuzz across 44 perspectives and 66 ground-truth datasets, reporting 86.96% recall and a 93.02% F1 score. It also reports an analysis of 66 real-world DeFi projects that identified zero-day bugs, including cases involving first deposits and AMM price-oracle manipulation.

## Routing relevance

PromFuzz is adjacent to model routing: it is a composite-analysis pipeline that routes different reasoning and verification stages to specialized components rather than asking one model to perform the entire task. The paper is useful for studying capability routing in security workflows, especially when LLM reasoning must be paired with deterministic invariant checking and targeted dynamic analysis.

## Canonical sources

- arXiv abstract: https://arxiv.org/abs/2503.23718
- HTML: https://arxiv.org/html/2503.23718v1
- PDF: https://arxiv.org/pdf/2503.23718
