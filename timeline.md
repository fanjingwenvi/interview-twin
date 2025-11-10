## 1109 
- Article: "How to Build Production-Ready RAG"  
  https://theneuralmaze.substack.com/p/how-to-build-production-ready-rag  
  Code: https://github.com/benitomartin/substack-newsletters-search-course

- 5 Popular LLM Integration Approaches  
  1. Direct API Integration — simple, reliable (OpenAI, Gemini)  
  2. Multi-Model Router — single API for many models (OpenRouter, Together.ai)  
  3. Open-Source / Local — self-hosted (Ollama, Hugging Face)  
  4. Hybrid Cloud + Open Source — mix control & scalability (Fireworks.ai, Anyscale)  
  5. Agentic / Orchestrated — frameworks with routing & memory (LangChain, Vercel AI SDK)

- Cloud Build File  
  Similar to GitHub Actions; defines automated build/deploy steps.

- Makefile  
  Defines build/run commands and dependencies; acts like a custom CLI for project management.

- Supabase & Qdrant Usage  
  - Example: `from qdrant_client import QdrantClient` → `get_collections()`  
  - Can access via API with key authentication.

- Prefect (Orchestration Tool)  
  - Local use: small teams  
  - Cloud use: large teams, scalable data ingestion.
