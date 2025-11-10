## 1110
## 1110

1. Virtual Environment  
   - Python version and dependencies specified in config  

   1. venv + pip  
      - Minimal, manual setup  
      - Good for small projects  

   2. Poetry  
      - Full dependency management and publishing  
      - Heavier and slower than uv  

   3. uv + pip  
      - Rust-based, very fast  
      - Auto-manages .venv, uses pyproject.toml  
      - Run without activation: uv run python src/pipelines/flows/rss_ingestion_flow.py  

   4. Notes  
      - Don’t commit .venv to github
      - Commit uv.lock for reproducible builds  

2. Google Cloud Run  
   - Runs containers, auto-scales to zero, pay-per-request  
   - Closest AWS services:  
     - App Runner → same simplicity, auto-scaling  
     - Fargate → similar infrastructure, more setup  
     - Lambda → works for short-lived containers  

## 1109 

1. Article: "How to Build Production-Ready RAG"  
  https://theneuralmaze.substack.com/p/how-to-build-production-ready-rag  
  Code: https://github.com/benitomartin/substack-newsletters-search-course

2. 5 Popular LLM Integration Approaches  
  1. Direct API Integration — simple, reliable (OpenAI, Gemini)  
  2. Multi-Model Router — single API for many models (OpenRouter, Together.ai)  
  3. Open-Source / Local — self-hosted (Ollama, Hugging Face)  
  4. Hybrid Cloud + Open Source — mix control & scalability (Fireworks.ai, Anyscale)  
  5. Agentic / Orchestrated — frameworks with routing & memory (LangChain, Vercel AI SDK)

3. Cloud Build File  
  Similar to GitHub Actions; defines automated build/deploy steps.

4. Makefile  
  Defines build/run commands and dependencies; acts like a custom CLI for project management.

5. Supabase & Qdrant Usage  
  - Example: `from qdrant_client import QdrantClient` → `get_collections()`  
  - Can access via API with key authentication.

6. Prefect (Orchestration Tool)  
  - Local use: small teams  
  - Cloud use: large teams, scalable data ingestion.
