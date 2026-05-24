# RAG and Knowledge Systems

RAG means Retrieval-Augmented Generation. The model answers using retrieved external information instead of relying only on training data.

## Pipeline

1. Ingest documents.
2. Clean and split into chunks.
3. Add metadata.
4. Create embeddings.
5. Store in vector database.
6. Retrieve relevant chunks for a question.
7. Optionally rerank results.
8. Generate answer with citations.
9. Evaluate answer and retrieval quality.

## Key Design Decisions

- Chunk size and overlap.
- Metadata schema.
- Embedding model.
- Vector database.
- Hybrid search vs vector-only search.
- Reranker.
- Citation format.
- Freshness and re-indexing.
- Access control by user/team/document.

## DevOps/SRE Use Cases

- Search Terraform modules and explain usage.
- Query Kubernetes runbooks.
- Answer incident response questions.
- Search postmortems for similar failures.
- Summarize CI/CD pipeline docs.
- Build onboarding assistant for cloud environments.

## Evaluation

- Retrieval precision: did the system fetch the right chunks?
- Faithfulness: is the answer supported by retrieved context?
- Correctness: is the answer actually right?
- Latency: can users tolerate response time?
- Cost: tokens, embedding cost, vector DB cost.

