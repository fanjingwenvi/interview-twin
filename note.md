## Why This Product

**Multiple purposes:**
1. Personal helper for interview preparation  
2. Showcase full end-to-end product development  
3. Networking, self-advertising, and learning in public (LLM Zoomcamp)

---

## What

**System scope**
- Complete cloud-deployed product  
- Built following *LLM ML Zoomcamp* and *LLM Engineer’s Handbook* guidelines

---

## How

**Dataset**
- Behavior question preparation
- personal knowledge base

**Architecture**
- Minimal frontend deployed on Vercel  
- Modular backend with RAG + API layers  
- AWS deployment using Docker for cost optimization

**Tech stack**
forntend: next.js - template usage 
backend: Docker-based, avoids vendor lock-in
cloud: vercel, App Runner or ECS Fargate

**Technical notes**

### frontend: 
Streamlit vs Next JS
Why next js 

### backend 
Langchain try out 

### cloud
- Difficulty: ECS Fargate > App Runner  
- Cost for low usage (10 × 10 min): ECS Fargate $0.0082 < Lambda < App Runner  
- Cost for 24/7 uptime: ECS Fargate $35/month > App Runner > Lambda  
- Ease of start/stop: ECS Fargate > App Runner 


### Reference

**LLM Zoomcamp:**  
[https://github.com/DataTalksClub/llm-zoomcamp](https://github.com/DataTalksClub/llm-zoomcamp)

**Architecture Example:**  
[https://github.com/alexeygrigorev/fitness-assistant](https://github.com/alexeygrigorev/fitness-assistant)

**frontend template**
[https://github.com/vercel/ai-chatbot?tab=readme-ov-file](https://github.com/vercel/ai-chatbot?tab=readme-ov-file)


## To-Do
- Test out App Runner deployment with Terraform  
- Test out Fargate with terraform 
- Get familiar with AWS environment

## To-Do Archive 