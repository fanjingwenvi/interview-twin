## 1113

LLM Engineer's Zoomcap  
https://github.com/immeritos/adhd-therapy-chatbot/blob/main/app/assistant.py

1. Embedding  
   - Generates vector representations of text for retrieval  

2. Retrieval  
   - Queries Qdrant collection twice:  
     - Dense retrieval: uses embedding vectors  
     - Sparse retrieval: uses BM25 keyword matching  
   - Limit results multiplied by 5  
   - Uses Reciprocal Rank Fusion (RRF) to combine results  

3. BM25  
   - Scores document relevance based on:  
     - Term frequency (TF): more matches increase score  
     - Inverse document frequency (IDF): rarer terms weigh more  
     - Document length normalization: favors shorter documents  
   - Implemented in Qdrant  
   - Common in search engines like Elasticsearch  

4. Prompting  
   - Example template for ADHD psychologist responses:  
     ```
     You are a psychologist specialized in ADHD.
     Answer the QUESTION based on the CONTEXT from the reference database.
     Use only the facts from the CONTEXT when answering the QUESTION.

     QUESTION: {question}

     CONTEXT:
     {context}
     ``` 

6. Model Choice 
   - OPENAI_MODELS = ["openai/gpt-4o-mini", "openai/gpt-4o", "openai/gpt-3.5-turbo"]  

7. LLM Eval  
   - Generation: LLM acts as a judge  
   - Retrieval: evaluate accuracy, precision, F1  

8. Monitoring  
   - Track OpenAI usage and calculate costs  

9. Comparing to the production version  
   - OOP vs POP 
   - continuous improvements in all aspects  

## 1111

1. pydantic_settings  
   - src/config.py defines settings as typed classes  
   - Ensures type safety and easy environment variable loading  

2. backend solution  
   - Lambda: minimal setup, zero server maintenance, event-driven, good for low traffic, less flexible  
   - FastAPI: more flexible, better for continuous traffic or complex APIs  

3. Hugging Face model (BAAI/bge-base-en-v1.5)  
   - Token setup for fast embeddings  
   - Powers both dense and sparse embeddings in Qdrant for indexing and querying Substack articles  

4. Jina  
   - Local FastEmbed model (BAAI/bge-base-en)  
   - Configure Jina only if using its embedding API instead of FastEmbed  

5. Opik  
   - Open-source LLM evaluation framework  

6. Security  
   - ALLOWED_ORIGINS controls CORS in src/api/main.py  
   - CORS defines which browser clients can access the API  

7. Mark  
   - Ensure all cloud and local environments are configured to run the project  

8. AI resources  
   - Paul Iusztin  
     - https://substack.com/@pauliusztin  
     - https://www.decodingai.com/  
   - Maxime Labonne  
     - https://mlabonne.github.io/blog/  
     - https://maximelabonne.substack.com/  
   - Podcast: The Data Entrepreneurs  
     - https://www.themasters.ai/episodes  

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
  Airflow in the corporation sss
