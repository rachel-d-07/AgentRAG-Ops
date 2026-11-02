# AgentRAG-Ops

MCP-inspired governance and observability for Retrieval-Augmented Generation (RAG).

![AgentRAG-Ops system architecture](docs/architecture.png)

## Project overview

AgentRAG-Ops is a research prototype exploring how governance, ranking, and observability can be brought together in a Retrieval-Augmented Generation workflow.

The project focuses on an offline retrieval pipeline, document re-ranking, an MCP-inspired governance layer for tool interactions, and trace-based monitoring. Its architecture is designed to make key stages of a RAG workflow easier to inspect, evaluate, and extend.

The current repository documents the system architecture and research direction. The implementation is being developed iteratively alongside the accompanying research work.

## Research objectives

- Governed tool interactions: Define a controlled path for tool calls using JSON-RPC-style messages, input validation, access allowlists, and audit records.
- Retrieval and ranking: Explore TF-IDF and FAISS-based candidate retrieval, with a static re-ranking baseline and an adaptive re-ranking approach.
- Execution observability: Record execution traces and examine interactions between agent roles.
- Evaluation: Compare ranking approaches and inspect system behaviour through measurable evaluation results.

## System architecture

The architecture is organised into three connected areas:

### 1. Retrieval and ranking pipeline

A user query enters the offline retrieval stage, where TF-IDF and FAISS indexes are used to identify candidate documents. Retrieved candidates are passed to a static re-ranking baseline. An adaptive re-ranking path is being explored as an alternative before answer generation.

### 2. MCP-inspired governance layer

The governance layer provides a structured approach to tool interactions. The design includes:

- JSON-RPC-style tool calls
- Tool input validation
- Allowlist-based access control
- Audit logging

This layer is inspired by concepts from the Model Context Protocol (MCP) and is intended as a focused governance prototype.

### 3. Observability and monitoring

The observability area focuses on execution tracing, inter-agent monitoring, and a SQLite store for trace and audit records. These records support inspection of system behaviour across workflow stages.

## Research and development status

| Area | Current direction |
|---|---|
| Offline retrieval | TF-IDF and FAISS-based candidate retrieval |
| Static re-ranking | Similarity and age-penalty baseline |
| Adaptive re-ranking | Experimental approach under active development |
| Governance | MCP-inspired JSON-RPC-style calls, validation, allowlists, and audit logging |
| Observability | Execution tracing, inter-agent monitoring, and SQLite-backed records |
| Evaluation | Static and adaptive ranking comparison |

The architecture and research scope will evolve as implementation and evaluation progress.

## Technology focus

- Python
- TF-IDF
- FAISS
- SQLite
- JSON-RPC-style tool interactions

## Roadmap

- Develop and document the offline retrieval workflow.
- Integrate and evaluate the static re-ranking baseline.
- Extend the adaptive re-ranking approach.
- Develop governance checks and corresponding tests.
- Expand execution tracing and SQLite-backed observability.
- Document agent responsibilities and interaction flows.
- Add reproducible evaluation scripts and a runnable demonstration.

## Research context

This project is accompanied by research work on governance and observability for RAG systems. Further paper details and evaluation materials will be linked here as they are prepared for public release.

## Author

Rachel D'Souza  
MSc Artificial Intelligence and Machine Learning  
MIT-ADT University, Pune  

GitHub: [@rachel-d-07](https://github.com/rachel-d-07)
