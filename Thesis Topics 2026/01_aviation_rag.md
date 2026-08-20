# Bachelor Thesis Topic 1

## Design and Evaluation of a Retrieval-Augmented Generation System for Grounded Aviation Decision Support

## Background

Large language models can produce fluent responses, but their answers may be unsupported, outdated or inconsistent with domain-specific documents. Retrieval-Augmented Generation (RAG) addresses this problem by retrieving relevant passages from an external knowledge base before generating a response.

This thesis is part of the proposed **AviaReason** research project. AviaReason is envisioned as an on-device decision-support application in which a pilot enters an aviation scenario and receives a concise, grounded and traceable recommendation. Before such an application can be developed, it is necessary to investigate whether a RAG system can reliably retrieve the correct supporting information from controlled aviation documents.

## Aim

The aim is to design, implement and evaluate a RAG pipeline for retrieving relevant information from a controlled collection of publicly available, synthetic or properly licensed aviation training and safety documents.

The main focus is information retrieval and grounding. The prototype is not expected to generate operational aviation decisions.

## Possible Research Questions

1. Which retrieval method provides the most relevant passages for aviation scenario queries?
2. How do chunk size, chunk overlap and document structure affect retrieval quality?
3. Does hybrid retrieval combining keyword and semantic search perform better than vector search alone?
4. Can reranking improve the relevance of retrieved passages?
5. How accurately can the system preserve document title, section, version and source information?

The student may refine these questions with the supervisor.

## Proposed Prototype

The prototype should:

- import a controlled set of aviation-related documents;
- clean and divide the documents into retrievable passages;
- create a searchable knowledge base;
- accept a pilot scenario or question;
- retrieve the most relevant passages;
- display the passage, source, document title and section;
- optionally generate a short answer that is limited to the retrieved evidence;
- clearly indicate when no reliable supporting passage is found.

### Example Query

> Destination weather is deteriorating, additional holding is expected, and the nominated alternate may become congested. What information should be reviewed before making a diversion decision?

### Example Result

The system returns the most relevant passages and their sources. It should not invent a recommendation when the documents do not support one.

## Suggested Technical Areas

- Python
- LlamaIndex, LangChain or a comparable framework
- vector databases such as FAISS or Chroma
- sentence-transformer embedding models
- BM25 or another keyword-retrieval method
- hybrid retrieval
- reranking models
- local or open-source language models
- metadata filtering

The exact tools may be selected according to the student's experience and available computing resources.

## Research Method

A design-science or experimental software-development approach is suitable.

Suggested stages:

1. Conduct a literature review on RAG and grounded generation.
2. Define the document collection and test queries.
3. Build at least two retrieval configurations.
4. Create a reference set in which relevant passages are identified manually.
5. Compare the configurations using quantitative and qualitative measures.
6. Analyse errors, limitations and possible improvements.

## Evaluation

Possible measures include:

- Precision@k;
- Recall@k;
- Mean Reciprocal Rank;
- expert or human relevance ratings;
- source-attribution accuracy;
- retrieval latency;
- frequency of unsupported generated claims;
- ability to abstain when no suitable evidence is available.

## Expected Deliverables

- literature review;
- documented aviation knowledge base;
- working RAG prototype;
- reference query and passage dataset;
- comparative evaluation;
- source code and installation instructions;
- discussion of limitations, data rights and safety considerations;
- recommendations for integration into AviaReason.

## Scope and Limitations

- Use only public, synthetic or properly licensed documents.
- Do not reproduce proprietary aircraft manuals or operator documents without permission.
- Do not claim that the retrieved material is approved for cockpit use.
- Do not connect the prototype to aircraft systems.
- Treat all scenarios and outputs as research or training material only.

## Expected Contribution to AviaReason

This thesis will provide the **grounded aviation knowledge-retrieval component**. Its output should later be usable by other modules through a simple interface containing the retrieved passage, source metadata, relevance information and verification status.

## Suitable Student Profile

This topic is suitable for a student interested in:

- artificial intelligence;
- information retrieval;
- natural language processing;
- embeddings and vector databases;
- open-source language models;
- experimental comparison of technical alternatives.
