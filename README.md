# Coca Cola 10 K RAG System

## Project Description
An end-to-end **Retrieval-Augmented Generation (RAG)** pipeline that answers questions from
**Coca-Cola Company 10-K filings** (last decade). The system parses PDFs, retrieves the most
relevant chunks, reranks them, and generates precise, citation-grounded answers.

## Dataset
Official 10-K filings:
https://investors.coca-colacompany.com/filings-reports/annual-filings-10-k

## RAG Pipeline (Overview)
1. **Parsing (Ingestion)**  
   - Use **LlamaParser** to convert 10-K PDFs into structured text/chunks.
2. **Retrieval**  
   - Compare and log performance of:  
     - Sentence Window Retriever  
     - Automerging Retriever  
     - Auto Retriever
3. **Reranking**  
   - Apply rerankers to prioritize the highest-relevance passages.
4. **RAG Query Engine**  
   - Configure standard query engine and **Sub-Question Query Engine** for complex/multi-hop questions.
5. **Evaluation**  
   - Measure retrieval hit-rate and QA quality (precision/recall/F1, answer relevance).

## Tech Stack
- **LlamaIndex** (retrievers, query engines, evaluation)
- **LlamaParser** (PDF → text)
- **Transformers / Embeddings** (encoder models, optional rerankers)
- **Vector Store / FAISS** (chunk indexing & search)
- Python

## Future Work
- Extend to other companies’ 10-K/10-Q filings  
- Add citation rendering in answers  
- Web UI for interactive RAG querying
