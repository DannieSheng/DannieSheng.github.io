---
title: "Retrieval in RAG: From Vector Search to Hybrid Systems"
date: 2026-04-28
tags:
  - rag
  - retrieval
  - genai
  - vector-search
  - hybrid-search
  - dense-retrieval
  - sparse-retrieval
  - bm25
  - semantic-search
  - ann
categories:
  - rag-systems
  - information-retrieval
excerpt: "A practical introduction to retrieval in RAG systems, covering dense vector search, sparse lexical retrieval, hybrid retrieval, and the trade-offs behind real-world retrieval design."
---
* TOC
{:toc}


## Introduction

In a Retrieval-Augmented Generation (RAG) system, retrieval determines what information is actually passed to the language model:

- Chunking defines the unit of retrieval.  
- Embedding defines how text is represented.  
- Retrieval decides which pieces of information are selected.

Even if the language model is strong, it can only reason over the context it receives. If retrieval returns irrelevant, incomplete, or misleading context, the final answer will likely suffer.

> Retrieval is not about finding everything relevant, but finding the right context under constraints.

In this post, I will discuss:
- how vector search works in RAG
- why sparse retrieval such as BM25 still matters
- why hybrid retrieval is useful
- how retrieval design affects recall, precision, and downstream answer quality

---

## Where Retrieval Fits in the RAG Pipeline

A typical RAG pipeline looks like:

Query → Embedding → **Retrieval** → Reranking → LLM

Retrieval sits between representation and reasoning.

- Embedding maps text into a vector space  
- Retrieval selects a small subset of candidates  
- Reranking refines their order  
- The LLM generates answers based on the selected context  

Retrieval sits between representation and reasoning.

Its role is to:
- reduce the search space from millions of documents to a small candidate set  
- maximize recall under latency constraints  

In other words:
> Retrieval is the stage where the system decides what it knows.

---

## Vector Search: The Dense Retrieval Paradigm

Vector search retrieves documents based on semantic similarity in an embedding space.

### How vector search works

At a high level, vector search consists of three steps:

- The query is converted into an embedding vector
- All documents are represented as vectors
- Retrieval is performed by finding the nearest neighbors


Similarity is typically measured using cosine similarity or dot product. This means retrieval is fundamentally a geometric operation:

> documents are ranked based on distance in a learned vector space.

### ANN (Approximate Nearest Neighbor)

In practice, exact nearest neighbor search is infeasible:
- embedding vectors are high-dimensional  
- corpora can contain millions of documents  

Computing exact distances to all vectors would be too slow. To address this, most systems use Approximate Nearest Neighbor (ANN) algorithms.

Common approaches include:

- HNSW (used in vector databases such as Qdrant)  
- IVF (used in libraries such as FAISS)  

These methods trade off a small amount of accuracy for significant gains in speed.

### Strengths of vector search

Vector search works well because it captures semantic similarity:
- it can match paraphrases  
- it is robust to wording variation  
- it generalizes beyond exact keywords  

For example:
- "heart attack" can match "myocardial infarction"  
- "side effects" can match "adverse reactions"  

This makes it especially useful in natural language queries.

### Limitations

However, vector search is not a complete retrieval solution. It relies solely on semantic similarity, which introduces several limitations:

- it may miss exact matches (e.g., numbers, IDs, drug names)  
- it struggles with rare or domain-specific terms  
- embedding biases propagate directly into retrieval results  

More importantly:

> similarity in embedding space is only an approximation of relevance.

As a result, vector search alone can produce results that are semantically related but not actually useful.

This limitation motivates the need for additional retrieval signals, which is discussed next.

---

## Sparse Retrieval: The Lexical Baseline

Before dense retrieval became popular, most search systems relied on sparse (lexical) retrieval methods.

The most widely used approach is BM25, which ranks documents based on keyword matching.

### BM25 intuition

BM25 builds on two simple ideas:

- terms that appear frequently in a document are important  
- rare terms across the corpus are more informative  

In practice, it scores documents based on how well their words match the query, weighted by term frequency and inverse document frequency.

This makes BM25 highly effective for queries where exact wording matters.

### Why sparse retrieval still matters

Despite the rise of vector search, sparse retrieval remains a strong baseline.

It provides signals that dense retrieval often misses:

- **exact matching** (e.g., names, IDs, drug names, numbers)  
- **deterministic behavior** (results are predictable and interpretable)  
- **robust baseline performance** across many domains  

For example:

- "Aspirin 100mg" will reliably match documents containing the exact dosage  
- entity-heavy queries benefit from precise keyword matching  

### Failure modes

Sparse retrieval has clear limitations:

- it cannot handle paraphrase (e.g., "heart attack" vs "myocardial infarction")  
- it ignores semantic similarity  
- it fails when query and document use different wording  

---

## Hybrid Retrieval: Combining Dense and Sparse

Neither dense nor sparse retrieval is sufficient on its own. 

Dense retrieval captures semantic similarity, but may miss exact matches.  

Sparse retrieval captures exact matches, but cannot generalize across different expressions.

Hybrid retrieval combines both signals to improve robustness.

### Why hybrid works

Dense and sparse methods model different aspects of relevance:

- **dense → meaning** (semantic similarity)  
- **sparse → exact match** (lexical signals)  

These signals are complementary rather than redundant.

In practice:

- dense retrieval improves recall for paraphrased queries  
- sparse retrieval ensures precision for entities, numbers, and keywords  

> Hybrid retrieval works because it combines semantic generalization with lexical precision.

### Common strategies

There are two common ways to combine dense and sparse retrieval.
#### Score fusion

Combine scores from both systems:

- weighted sum of dense and sparse scores  
- requires normalization (scores are not directly comparable)  

**Challenges:**

- dense and BM25 scores have different distributions  
- requires tuning weights  
- less stable across datasets  

#### Rank fusion

Combine rankings instead of scores. A common approach is **Reciprocal Rank Fusion (RRF)**:

- each system produces a ranked list  
- ranks are combined using a simple formula  

---

### Example (OpenSearch)

In practice, hybrid retrieval is often implemented using search engines such as OpenSearch.

A typical setup includes:

- BM25 for sparse retrieval  
- vector search for dense retrieval  
- a fusion strategy to combine results  

This allows systems to leverage both lexical and semantic signals in a single query.

### When to use hybrid retrieval

Hybrid retrieval is particularly useful when:

- the domain contains precise terminology (e.g., medical, legal)  
- queries include both intent and keywords  
- exact matches (IDs, drug names, numbers) are critical  
- pure vector search produces unstable or noisy results  

### Key takeaway

Hybrid retrieval is not an optimization, but a necessity in many real-world systems.

> Effective retrieval is not about choosing one method, but combining complementary signals.

---

## Retrieval Trade-offs

Retrieval design is fundamentally about trade-offs. There is no single “best” retrieval strategy — only choices that balance competing objectives.

### Recall vs Precision

- **Recall**: retrieving all relevant documents  
- **Precision**: retrieving only relevant documents  

In RAG systems:

- retrieval typically prioritizes **recall**  
- reranking is used to improve **precision**  

**Example:**

- top-3 → high precision, low recall  
- top-20 → high recall, lower precision  

**Key insight:**

> Retrieval should aim to avoid missing important information, even at the cost of introducing noise.

### Latency vs Accuracy

More accurate retrieval often requires more computation:

- exact search → more accurate but slower  
- ANN → faster but approximate  
- hybrid retrieval → more signals but higher cost  

**Trade-off:**

- lower latency improves responsiveness  
- higher accuracy improves answer quality  

### Cost vs Performance

Retrieval design also impacts system cost:

- larger top-k → more tokens → higher LLM cost  
- more complex pipelines → higher infrastructure cost  
- reranking → additional model inference  

**Implication:**

> Better retrieval is not free — it shifts cost across the system.

### Stability vs Flexibility

Different retrieval strategies behave differently:

- sparse retrieval → stable and predictable  
- dense retrieval → flexible but less controllable  
- hybrid → more robust but more complex  

### Putting it together

In practice, modern RAG systems often adopt a multi-stage approach:

- retrieval (high recall)  
- reranking (high precision)  
- generation (final reasoning)  

**Final takeaway:**

> Retrieval is not just a component, but a set of design decisions that balance recall, precision, latency, and cost.

---

## Practical Design Guidelines

Designing retrieval for RAG systems is not about choosing a single method, but about making a sequence of practical decisions.

### 1. Start simple

Begin with a dense vector search baseline:

- use a strong embedding model  
- retrieve top-k candidates (e.g., k = 10–20)  
- manually inspect results  

This provides a quick signal of whether your data and queries are aligned.

### 2. Add sparse retrieval when precision matters

Introduce BM25 or keyword search if you observe:

- missed exact matches (e.g., names, IDs, dosages)  
- domain-specific terminology  
- unstable or noisy results  

Hybrid retrieval is often a low-cost way to improve robustness.

### 3. Tune top-k based on task needs

Top-k controls the recall–precision balance:

- smaller k → higher precision, lower recall  
- larger k → higher recall, more noise  

In practice:

- choose k large enough to avoid missing key context  
- rely on reranking or the LLM to filter noise  

### 4. Keep retrieval and scoring consistent

Ensure alignment between:

- embedding model  
- similarity metric (cosine vs dot product)  
- normalization strategy  

Inconsistencies here can silently degrade ranking quality.

### 5. Evaluate with real queries

Use realistic queries to test retrieval:

- domain-specific questions  
- edge cases (numbers, entities)  
- ambiguous phrasing  

Avoid relying only on synthetic examples.

### 6. Inspect results regularly

Quantitative metrics are useful, but manual inspection is essential:

- check top-k results  
- identify recurring failure patterns  
- verify that retrieved context is actually usable  

### 7. Plan for multi-stage retrieval

In most production systems:

- retrieval → maximize recall  
- reranking → improve precision  

Design retrieval with this pipeline in mind, rather than expecting a single method to solve everything.


**Key takeaway:**

> Good retrieval systems are not built by choosing a method, but by iteratively refining decisions based on observed behavior.

---

## Common Failure Modes

Retrieval failures are rarely random. They are usually systematic and reproducible. Understanding these patterns is critical for debugging and improving RAG systems.

### 1. Missing obvious matches

Relevant documents exist but are not retrieved. Common causes:

- embedding model mismatch  
- insufficient top-k  
- missing keyword signals  

### 2. Semantically related but irrelevant results

Retrieved documents are “close” in meaning but not useful. Typical in dense retrieval when:

- queries are broad or ambiguous  
- embedding space is too smooth  

### 3. Over-reliance on keywords

Sparse retrieval dominates results, leading to:

- exact matches without context  
- poor handling of paraphrase  

### 4. Domain mismatch

Retrieval fails on:

- rare entities  
- domain-specific terminology  
- new or unseen concepts  

### 5. Noisy candidate sets

Too many partially relevant results:

- large top-k without filtering  
- hybrid retrieval without proper fusion  
- lack of reranking  

### 6. Inconsistent behavior across queries

Same system performs well on some queries but poorly on others. Often caused by:

- uneven data distribution  
- query–document mismatch  
- sensitivity to phrasing  

### Key insight

> Retrieval failures reflect mismatches between signals, data, and task requirements — not just model weaknesses.

In practice, improving retrieval is less about replacing components, and more about understanding these failure patterns and addressing them systematically.

## Conclusion

Retrieval is a foundational component of RAG systems, but it is often oversimplified.

Vector search enables semantic matching, while sparse retrieval provides precise lexical signals. In practice, effective systems combine both, and further refine results through multi-stage pipelines.

The key challenge is not choosing a single method, but balancing trade-offs:

- recall vs precision  
- latency vs accuracy  
- cost vs performance  

**Final takeaway:**

> Retrieval determines what your system knows.  
> Designing it well is essential for building reliable RAG applications.

## References
- [Dense Passage Retrieval for Open-Domain Question Answering](https://arxiv.org/abs/2004.04906) 
- [What is BM25 (Best Matching 25) Algorithm](https://www.geeksforgeeks.org/nlp/what-is-bm25-best-matching-25-algorithm/)
- [Hybrid search](https://docs.opensearch.org/latest/vector-search/ai-search/hybrid-search/index/)
- [Reciprocal Rank Fusion (RRF) explained in 4 mins — How to score results form multiple retrieval methods in RAG](https://medium.com/@devalshah1619/mathematical-intuition-behind-reciprocal-rank-fusion-rrf-explained-in-2-mins-002df0cc5e2a)
- [HNSW Indexing Fundamentals](https://qdrant.tech/course/essentials/day-2/what-is-hnsw/)

