---
title: "Embedding in RAG: Why Representation Matters More Than You Think"
date: 2026-04-21

tags:
  - rag
  - embedding
  - retrieval
  - genai
categories:
  - rag-systems

draft: true
---
* TOC
{:toc}

## Introduction

In Retrieval-Augmented Generation (RAG) systems, embeddings are often treated as a black box: text goes in, vectors come out.

However, embedding quality fundamentally determines what “semantic similarity” means in your system.

Even with perfect chunking and a well-tuned vector database, poor embeddings will lead to irrelevant retrieval results.

This post explores how embeddings work in practice, what design choices matter, and how to reason about embedding quality in real-world systems.

---

## Where embedding fits in a RAG pipeline

A typical RAG pipeline consists of:

1. Document ingestion  
2. Chunking  
3. **Embedding**  
4. Vector storage  
5. Retrieval  
6. LLM generation  

Embedding is the step that converts text into a numerical representation that enables similarity search.

Key implication:

- Retrieval operates on vectors, not text  
- Therefore, embedding defines what “similar” means  

---

## What is an embedding (intuitive view)

An embedding maps text into a high-dimensional vector space:

- Similar meaning → vectors close together  
- Different meaning → vectors far apart  

At a high level:

- Sentence → vector (e.g., 768 / 1536 dimensions)  
- Similarity → cosine similarity / dot product  

---

## What makes a “good” embedding?

A useful embedding should:

- Capture semantic similarity  
- Be robust to wording variation  
- Preserve task-relevant distinctions  

However, “good” is always **task-dependent**.

---

## Types of embedding models

### 1. General-purpose embeddings

- Trained on broad corpora  
- Good default for most use cases  

Examples:
- OpenAI text embeddings  
- BGE (BAAI) models  

---

### 2. Domain-specific embeddings

- Trained on specialized data (e.g., medical, legal)  
- Capture domain terminology better  

Use when:
- Vocabulary is highly specialized  
- General embeddings fail to distinguish concepts  

---

### 3. Instruction-tuned embeddings

- Optimized for retrieval tasks  
- Often require query/document prefixes  

Example:

- `"query: ..."` vs `"document: ..."`

---

### 4. Multilingual embeddings

- Support cross-language retrieval  
- Useful for global or multi-region systems  

---

## Embedding space and similarity metrics

Common similarity measures:

- Cosine similarity  
- Dot product  
- Euclidean distance  

In practice:

- Cosine similarity is most widely used  
- Choice of metric should align with model training  

---

## Key design decisions in embedding

### 1. Query vs document embeddings

- Should you use the same model?  
- Should you use different prompts?  

---

### 2. Text normalization

- Lowercasing  
- Removing noise  
- Handling structured fields  

---

### 3. Chunk size interaction

Embedding quality depends on chunking:

- Too large → diluted semantics  
- Too small → incomplete meaning  

---

### 4. Metadata-aware embeddings (optional)

- Combining text + metadata  
- Using structured fields  

---

## The core trade-off: generalization vs specificity

Embedding design often balances:

- Generalization → robust across queries  
- Specificity → precise domain understanding  

---

## Practical considerations (from real-world systems)

### 1. Embedding is often the hidden bottleneck

Poor retrieval is frequently due to:

- embedding mismatch  
- not vector DB or LLM  

---

### 2. Model choice matters less than alignment

A smaller, well-aligned embedding model can outperform a larger one.

---

### 3. Evaluation is essential

You should not assume embeddings work — you should test them.

---

## How to evaluate embedding quality

### Offline evaluation

- Top-k recall  
- MRR / nDCG  

---

### Qualitative inspection

- Inspect retrieved chunks  
- Check semantic alignment  

---

### A/B testing

- Compare models or configurations  

---

## Embedding design checklist

### 1. What is your domain?

- General vs specialized  

---

### 2. What type of queries?

- Keyword-like vs semantic  

---

### 3. What is your data structure?

- Clean vs noisy  
- Structured vs unstructured  

---

### 4. Do you need multilingual support?

---

### 5. Are you using instruction-based models correctly?

---

### 6. How will you evaluate performance?

---

## Common anti-patterns

- Treating embedding as a black box  
- Ignoring query/document asymmetry  
- Using overly large chunks  
- Not evaluating retrieval quality  

---

## Conclusion

Embeddings define the semantic foundation of RAG systems.

Before optimizing retrieval pipelines or LLM prompts, it is often worth revisiting how text is represented.

---

## References

- Sentence Transformers documentation  
- BGE embedding models  
- OpenAI embedding guide  
- IR evaluation metrics (MRR, nDCG)  