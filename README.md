
<div align="center">
  <h1>🦊 Vulpix: Enterprise AI Data Copilot</h1>
  <p><b>Agentic data workflows, zero-memory-breach orchestration, and constraint-aware synthesis.</b></p>
  <img src="https://img.shields.io/badge/Architecture-Microservices-purple?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Services-17_Active-brightgreen?style=for-the-badge" />
</div>

## System Architecture
Vulpix operates on a strictly separated Microservices architecture orchestrated via Docker Compose, utilizing 17 distinct Python/FastAPI microservices, a Node.js/Next.js frontend, a Node.js backend proxy, PostgreSQL, and a Google Cloud Storage (GCS) emulator for stateless data transfer.

```mermaid
graph TD;
    A[Next.js Frontend] -->|SSE Stream| B[Node.js Proxy Gateway];
    B --> C[FastAPI Orchestrator];
    C --> D[(PostgreSQL Meta)];
    C --> E[Data Parsing Service];
    C --> F[CTGAN / TVAE Generator];
    C --> G[Copula Fallback Engine];
    F -.->|Out of Memory| G;
```

## Features
- **Algorithmic Fallback Mechanisms:** If deep learning models hit OOM, the system autonomously degrades to Copula or Bootstrap modeling to guarantee delivery.
- **Agentic Workflow:** Intelligent LangGraph planner routing data between Imputer, Balancer, and Outlier Detector.
