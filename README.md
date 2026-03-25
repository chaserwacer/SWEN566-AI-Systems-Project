# SWEN566-AI-Systems-Project
# Project Plan — Movie Master  
### AI-Powered Film Intelligence Platform

---

## 1. Overview
Movie Master is an AI-powered application that allows users to explore, understand, and interact with movies through natural language.

Users can:
- Search for a movie  
- View AI-generated summaries from transcripts  
- Chat with an AI “movie expert”  
- Translate summaries into other languages  
- Rate movies and receive recommendations  

The system combines structured data (movie database + ratings) with unstructured data (transcripts) and uses AI to transform that into interactive experiences.

---

## 2. Core Features

### A. Movie Retrieval + Processing
- Search movie by name  
- Retrieve:
  - Metadata (title, year, genre)
  - Transcript (stored or fetched)
- Store processed outputs (summary, embeddings)

### B. AI Movie Summarization
**Input:** Full movie transcript  

**Output:**
- Short summary (1–2 paragraphs)
- Optional detailed breakdown
- Optional top 3–5 character breakdown  

- Cache summaries to avoid recomputation

### C. AI Chat (Movie Expert Agent)
- Chat interface per movie  

**Model context includes:**
- Movie summary  
- Key extracted facts  
- Character summaries (optional)

**Capabilities:**
- Answer questions about plot/characters  
- Explain themes  
- Discuss scenes  

### D. Translation
- Translate summaries into other languages  
- Optional: translate user chat input/output  

### E. Ratings + Recommendations
**Users:**
- Rate movies (1–10 scale)

**System:**
- Stores ratings  
- Generates recommendations:
  - Simple (genre + similarity)
  - Optional AI-enhanced recommendations  

### F. Recommendation Engine (Potential Enhancement)
- Use:
  - Embedding similarity **OR**
  - Collaborative filtering  

- AI explanation:
  - _“You may like this because…”_

---

## 3. AI Services

**Minimum Requirement:** 2 AI services  

### Core Services
- **LLM / Chat Model**
  - User-facing interactions  
  - Retrieval and reasoning over movie data  
  - Bridge between backend and UI  

- **Summarization Model**
  - Generate movie summaries  
  - Extract key facts  
  - Generate character breakdowns  

- **Translation Model**
  - Translate summaries and explanations  

### Optional Services
- **Azure AI Search (Vector Search)**
  - Store embeddings of summaries  
  - Enable semantic recommendations  

---

## 4. System Architecture

### Frontend
**Web App (React or SvelteKit)**

Features:
- Search UI  
- Chat UI  
- Ratings UI  

### Backend (API Layer)
**ASP.NET / Node / Python**

Responsibilities:
- Handle requests  
- Call AI services  
- Manage database  

### Database
Tables:
- Movies  
- Transcripts  
- Summaries  
- Users  
- Ratings  

### AI Pipeline Flow
1. User searches for a movie  
2. Backend retrieves transcript  
3. If no summary exists → call AI service  
4. Store generated summary  
5. Initialize chat context  
6. Serve data to UI  

---

## 5. AI Agent Role

### Internal AI Agent Role
**Primary Role:** Software Developer  

**Responsibilities:**
- Develop user interface  
- Generate feature drafts  
- Assist with merges  

The team will leverage the AI agent primarily for code generation. With a large set of existing AI service examples, the agent can draft features and generate starter code, enabling rapid iteration while maintaining control over architecture and quality.

The agent will also assist with:
- Prompt design  
- API integration patterns  
- Debugging and issue resolution  

All generated code will be reviewed, refined, and validated by team members to ensure correctness, performance, and alignment with project requirements.

---

## 6. Team Roles

### 1. Software Developer / Engineer
- AI Agent  
- Howard Kong  

**Responsibilities:**
- API development  
- AI service integration  
- Database design  
- UI/UX  
- Chat interface  
- State management  

### 2. Project Planner
- Chase Balmer  

**Responsibilities:**
- Manage GitHub board  
- Manage project proposal  
- Maintain plan updates  
- Coordinate team  

### 3. AI Engineer
- Blake Rossi  

**Responsibilities:**
- Prompt design  
- Model deployment  
- Summarization pipeline  
- Chat tuning  

### 4. Code Reviewer
- Oscar Chen  

**Responsibilities:**
- Verify code quality  
- Verify correctness  
- Optimization  
- Testing  

---

## 7. Tech Stack

### Backend
- Python (FastAPI) — API development and AI service integration  

### Frontend
- TBD (React or SvelteKit for a lightweight, interactive UI)  

### Database
- SQLite or PostgreSQL — movies, transcripts, user ratings  

### AI Services (Azure)
- Azure OpenAI — summarization, chat, recommendations  
- Azure AI Translator — language translation  

### Optional Enhancements
- Azure AI Search — semantic search / embeddings  
- Azure Blob Storage — transcript storage  
