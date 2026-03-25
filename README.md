# SWEN566-AI-Systems-Project
Project Plan — Movie Master 
AI-Powered Film Intelligence Platform

1. Overview
Movie Master is an AI-powered application that allows users to explore, understand, and interact with movies through natural language.
Users can:
Search for a movie
View AI-generated summaries from transcripts
Chat with an AI “movie expert”
Translate summaries into other languages
Rate movies and receive recommendations
The system combines structured data (movie DB + ratings) with unstructured data (transcripts) and uses AI to transform that into interactive experiences.

2. Core Features
A. Movie Retrieval + Processing
Search movie by name
Retrieve:
Metadata (title, year, genre)
Transcript (stored or fetched)
Store processed outputs (summary, embeddings)

B. AI Movie Summarization
Input: full movie transcript
Output:
Short summary (1–2 paragraphs)
Optional detailed breakdown
Optional top 3-5 character breakdown 
Cache summaries to avoid recomputation

C. AI Chat (Movie Expert Agent)
Chat interface per movie
Model context includes:
Movie summary
Key extracted facts
Character summaries?
Capabilities:
Answer questions about plot/characters
Explain themes
Discuss scenes

D. Translation
Translate summaries into other languages
Optional: translate user chat input/output

E. Ratings + Recommendations
Users:
Rate movies (1–10 or similar)
System:
Stores ratings
Generates recommendations:
Simple (genre + similarity)
Optional AI-enhanced recommendations

F. Recommendation Engine (Potential Enhancement)
Use:
Embeddings similarity OR
Collaborative filtering
AI explanation:
“You may like this because…”

3. AI Services 
Minimum requirement: 2 AI services
Required (Core)
LLM / Chat Bot
User facing interactions
Manage retrieval of movie data 
Bridge between backend data and frontend UI 
Translation model
Translate model generated summaries/explanations 
Summarization model
Movie summary
Key extracted facts
Character summaries

Optional 
Azure AI Search (with vector search)
Store embeddings of movie summaries
Enable semantic recommendation

4. System Architecture 
Frontend
Web app (React / SvelteKit)
Features:
Search UI
Chat UI
Ratings UI

Backend (API Layer)
ASP.NET / Node / Python
Responsibilities:
Handle requests
Call AI services
Manage DB

Database
Tables:
Movies
Transcripts
Summaries
Users
Ratings

AI Pipeline Flow
User searches movie
Backend retrieves transcript
If no summary exists → call OpenAI
Store summary
Initialize chat context
Serve UI

5. AI Agent Role 
Internal AI Agent Role
Primary Role: Software Developer 
Responsibilities:
Develop user interface 
Generate feature drafts 
Assist with merges 
The team will primarily leverage the AI agent for its code generation abilities. With the vast quantity of sample AI service projects we have created, there is plenty of example code to provide the agent with. By allowing the AI agent to draft features and lay down starter code, we can iterate quickly in development while maintaining control over architecture and quality.
The agent will also assist with prompt design, API integration patterns, and debugging by suggesting fixes or improvements when issues arise. Team members will review, refine, and validate all generated code to ensure correctness, performance, and alignment with project requirements. This approach enables faster prototyping without sacrificing reliability or understanding of the system.


6. Team Roles 
1. Software Developer/Engineer
AI Agent
Howard Kong
API development
AI service integration
DB design
UI/UX
Chat interface
State management
2. Project Planner 
Chase Balmer
Manage GitHub board 
Manage project proposal 
Manage plan updates 
Coordinate group 

3. AI Engineer
Blake Rossi
Prompt design
Model deployment 
Summarization pipeline
Chat tuning
4. Code Reviewer
Oscar Chen
Verify code quality
Verify code correctness
Optimization
Testing

7. Tech Stack
Backend: Python (FastAPI) for API development and AI service integration
Frontend: TBD (likely React or SvelteKit for a lightweight, interactive UI)
Database: SQLite or PostgreSQL for movies, transcripts, and user ratings
AI Services (Azure):
Azure OpenAI (summarization, chat, recommendations)
Azure AI Translator (language translation)
Optional Enhancements:
Azure AI Search (semantic search / embeddings)
Azure Blob Storage (transcript storage)
