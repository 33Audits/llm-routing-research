# Follow the Entities: A Corpus Map for Agentic Search

- **Authors:** Soyeong Jeong, Sujay Kumar Jauhar, Sung Ju Hwang, Andrew Joohun Nam
- **Submitted:** 29 September 2026
- **Paper:** https://arxiv.org/abs/2609.37226
- **Code/data:** No project link is listed on the arXiv record.

## Summary

This paper introduces CorpusMap, a navigation layer for agentic search over large document collections. Instead of exposing a corpus as a flat set of files, CorpusMap organizes recurring entities into Entity Pages that aggregate information about an entity and link to every document that mentions it. The resulting entity-document graph lets an agent traverse related evidence across documents.

The links are constructed offline by resolving mentions of the same entity, so relationships can be reused across queries rather than rediscovered during inference. Across seven models and three benchmark datasets, the authors report improved evidence discovery and answer quality over raw-corpus agentic search while using fewer tokens on average.

## Routing relevance

This is adjacent to model routing rather than a model-router benchmark: it routes *search/navigation steps* through an offline corpus structure. It is relevant to routing systems because better evidence navigation can change which model or capability tier a query needs, reduce repeated retrieval work, and provide a structured signal for escalation decisions.

## Canonical sources

- arXiv abstract: https://arxiv.org/abs/2609.37226
- HTML: https://arxiv.org/html/2609.37226v1
- PDF: https://arxiv.org/pdf/2609.37226
