---
label: Bill Sentiment Analysis
icon: graph
description: "AI-powered dashboard for analyzing public sentiment on draft legislations using NLP, RAG, and Milvus."
order: 81
tags: [Next.js, FastAPI, NLP, RAG, Milvus]
---

# :icon-file: AI-Powered Bill Sentiment Analysis

![Next.js](https://img.shields.io/badge/Next.js-black?style=flat-square&logo=next.js&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![NLP](https://img.shields.io/badge/NLP-RAG-blue?style=flat-square) ![License](https://img.shields.io/github/license/0xarchit/BillsSentiments?style=flat-square)    
![Stars](https://img.shields.io/github/stars/0xarchit/BillsSentiments?style=flat-square) ![Repo Size](https://img.shields.io/github/repo-size/0xarchit/BillsSentiments?style=flat-square) ![Forks](https://img.shields.io/github/forks/0xarchit/BillsSentiments?style=flat-square)

**BillsSentiments** is an advanced AI-driven analytical dashboard built to tackle the challenge of manually analyzing thousands of public stakeholder comments on draft legislations.

**:icon-mark-github: GitHub:** [https://github.com/0xarchit/BillsSentiments](https://github.com/0xarchit/BillsSentiments){target="_blank"}

## :icon-rocket: Overview {#overview}

By leveraging **Natural Language Processing (NLP)**, **Large Language Models (LLMs)**, and **Retrieval-Augmented Generation (RAG)**, this platform automates:

- :icon-smiley: **Sentiment Analysis**: Classifying feedback as Positive, Neutral, or Negative.
- :icon-book: **Contextual Summarization**: Generating concise summaries of lengthy legal texts.
- :icon-comment-discussion: **Semantic Search**: Enabling "Chat to Document" functionality via Vector search.
- :icon-graph: **Visual Analytics**: Providing word clouds and statistical breakdowns for policy makers.

### Input Data Example
The system analyzes complex legislative texts and diverse public comments.
![Sample Act](/public/SentimentComments/sampleactofbudget.png)

## :icon-organization: System Architecture {#architecture}

The system is built on a **Microservices-inspired architecture**, containerized with Docker for easy deployment. It features a **FastAPI** backend for heavy ML lifting and a sleek **Next.js** frontend for an immersive user experience.

![System Diagram](/public/SentimentComments/systemdiagram.png)

### Core Workflow
1.  **:icon-upload: Ingestion**: Comments are uploaded (CSV) or fetched via API.
2.  **:icon-cpu: Processing**:
    *   **Sentiment Engine**: BERT-based model predicts sentiment scores.
    *   **Vectorization**: Embeddings are generated and stored in **Milvus (Zilliz)** for RAG.
    *   **Vector Storage**: The Milvus vector database efficiently indexes these embeddings for rapid similarity search.
      ![Milvus DB](/public/SentimentComments/milvusvectordb.png)
3.  **:icon-search: Analysis**: **Gemini 2.5 Flash** (via LangChain) generates summaries and answers RAG queries.
4.  **:icon-browser: Presentation**: Results are displayed on a real-time Interactive Dashboard.

![RAG Workflow](/public/SentimentComments/ragsystemworkflow.png)

## :icon-star: Key Features {#features}

### 1. Interactive Dashboard {#dashboard}
A modern, responsive UI showing real-time statistics, sentiment distribution, and recent activities.
![Landing Page](/public/SentimentComments/landingpage.png)

### 2. RAG-Powered Chatbot {#chatbot}
Ask questions about specific legislative acts. The bot retrieves context from the official document PDFs and stakeholder comments to provide evidence-backed answers.
![Chatbot](/public/SentimentComments/chatbot.png)

### 3. Automated Insight Generation {#insights}
View overall sentiment trends and word clouds highlighting key topics of discussion for each act.
![Acts Overview](/public/SentimentComments/acts.png)

### 4. Detailed Comment Analysis {#comment-analysis}
Drill down into individual comments with granular sentiment scoring and metadata.
![Comment Drilldown](/public/SentimentComments/actscomments.png)

### 5. Secure Authentication {#authentication}
Robust user management and authentication system powered by Supabase.
![Account Verification](/public/SentimentComments/accountverification.png)

### 6. Admin & System Health {#admin-health}
Role-based access control (RBAC). Admins can manage acts, trigger model updates, and monitor the health of all system components.
![Admin Panel](/public/SentimentComments/adminpanel.png)

**System Health Monitoring:**
![Health Tab](/public/SentimentComments/healthtab.png)

## :icon-tools: Tech Stack {#tech-stack}

![Tech Stack](/public/SentimentComments/techstack.png)

| Layer | Technologies |
| :--- | :--- |
| **Frontend** | Next.js 15 (React), TailwindCSS, ShadCN UI, Recharts, Framer Motion |
| **Backend** | Python FastAPI, LangChain, PyTorch (Sentiment Model) |
| **Database** | PostgreSQL (Structured), Milvus/Zilliz (Vector), Supabase (Auth & DB) |
| **AI/ML** | OpenAI/Gemini APIs, Sentence-Transformers (Embeddings) |
| **DevOps** | Docker, Docker Compose, GitHub Actions |

## :icon-plug: API & Database {#api-database}

The backend exposes a comprehensive REST API documented via Swagger UI.
![FastAPI Swagger](/public/SentimentComments/fastapiendpoints.png)

### Database Schema
A robust relational schema handles Users, Acts, Comments, and Authentication states.
![DB Schema](/public/SentimentComments/pgdbschema.png)

## :icon-rocket: Getting Started {#getting-started}

### Option A: Docker (Recommended)
Deploy the entire stack (Frontend + Backend) with a single command. The backend is isolated internally, exposing only the frontend.

```bash
# 1. Clone the repository
git clone https://github.com/0xarchit/BillsSentiments.git
cd BillsSentiments

# 2. Setup Environment Variables
# Populate .docker-env with your API keys (Supabase, Gemini, etc.)

# 3. Launch
docker-compose up --build
```
Access the app at `http://localhost:3000`.

### Option B: Manual Setup

#### Backend
```bash
# Setup Python Environment
python -m venv venv
.\venv\Scripts\activate
pip install -r requirements.txt

# Run Server
uvicorn app:app --reload --port 8000
```

#### Frontend
```bash
cd Frontend
npm install
npm run dev
# App runs at http://localhost:3000
```

## :icon-beaker: Testing & Performance {#testing}

We maintain rigorous testing standards including unit tests for API endpoints and consistency checks for the ML models.

| Metric | Status |
| :--- | :--- |
| **Sentiment Accuracy** | 92% (F1 Score) |
| **API Latency** | < 200ms (Average) |
| **RAG Retrieval** | Top-5 Context Precision |

### Model Evaluation
![Model Evaluation](/public/SentimentComments/confusionmatrix.png)

### Test Coverage
![Test Coverage](/public/SentimentComments/localtestingresult.png)
