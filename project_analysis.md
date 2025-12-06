# Project Analysis & Architecture Flow

## 1. Core Objective

**Goal:** Create an AI-Native Textbook for "Physical AI & Humanoid Robotics".
**Platform:** A web-based portal (Docusaurus) that serves as both a textbook and an intelligent learning platform.

## 2. Understanding the "Spec-Kit Plus" & "Claude Code" Requirement

The requirements mention using **Claude Code** and **Spec-Kit Plus**.

- **Context:** These are tools/methodologies for agentic coding.
- **My Role:** As your AI Agent (Antigravity), I am fulfilling the role of "Claude Code".
- **Spec-Kit Plus:** This refers to the **Specification-Driven Development** approach.
  - We are already doing this by maintaining `info.md` (Master Spec) and `tasks.md` (Execution Plan) as our "Source of Truth".
  - Every task is derived from these specs, ensuring we don't deviate from the requirements.

## 3. Architecture Breakdown

### A. Frontend (The "Face")

- **Tech:** Docusaurus (React + TypeScript + Tailwind CSS).
- **Role:**
  - Displays the textbook content (Markdown files).
  - Handles User Auth (Login/Signup).
  - Provides the Chatbot UI.
  - **New Features:**
    - **Personalization:** "Personalize Content" button injects user background (Python/ROS) into the context.
    - **Urdu Translation:** "Translate" button calls the backend to rewrite the chapter in Urdu.

### B. Backend (The "Brain")

- **Tech:** FastAPI (Python).
- **Role:**
  - **API Layer:** Connects Frontend to AI services.
  - **Auth Handler:** Manages user sessions (simulating Better Auth).
  - **RAG Engine:** The core intelligence.

### C. RAG Pipeline (Retrieval-Augmented Generation)

This is how the Chatbot answers questions based _only_ on the book:

1.  **Ingestion (The "Learning" Phase):**
    - We send all Textbook Chapters (Markdown) to the Backend.
    - Backend splits them into small "chunks".
    - **OpenAI Embeddings** convert chunks into "Vectors" (numbers representing meaning).
    - Vectors are stored in **Qdrant Cloud** (Vector DB).
2.  **Retrieval (The "Thinking" Phase):**
    - User asks: "How do I control a robot arm?"
    - Backend converts this question into a Vector.
    - **Qdrant** finds the most similar textbook chunks.
3.  **Generation (The "Speaking" Phase):**
    - Backend sends the User Question + Found Chunks to **OpenAI GPT-4o**.
    - Prompt: "Answer the user using ONLY these chunks."
    - GPT generates the answer.

### D. "Agent Skills" & "Subagents" (Bonus)

- **Concept:** Instead of just "answering", the AI can "do" things.
- **Implementation:**
  - We can create a "Quiz Subagent" that generates a quiz for the current chapter.
  - We can create a "Code Review Subagent" that checks the user's ROS 2 code.
  - These will be specialized prompts/tools within the Chatbot.

## 4. Proposed Workflow (Start to Finish)

If we restart/continue, this is the ideal flow:

1.  **Setup (Done):** Docusaurus + Tailwind + Basic Layout.
2.  **Auth & Personalization (In Progress):**
    - Signup captures "Software/Hardware Background".
    - This data is stored in the User Session.
3.  **Content Creation:**
    - Write Modules 1-4 in Markdown.
    - Add "Personalize" & "Translate" buttons to the layout.
4.  **Backend Setup:**
    - Set up FastAPI.
    - Connect Qdrant & OpenAI.
5.  **RAG Integration:**
    - Create script to "ingest" our Markdown files into Qdrant.
    - Create `/query` endpoint for the Chatbot.
6.  **Frontend Integration:**
    - Connect Chatbot UI to `/query`.
    - Connect "Translate" button to `/translate` endpoint.
7.  **Final Polish:**
    - UI Animations ("Cinematic Feel").
    - Deployment (Vercel + Render).

## 5. Decision Point

You asked to "start from scratch" (shuru se).

- **Option A (Continue):** We keep the current UI (it matches the Cinematic theme) and just refactor the Auth/Content parts to match the new requirements strictly.
- **Option B (Full Restart):** We delete everything and start fresh.

**Recommendation:** **Option A**. The current UI is already good and "Cinematic". We just need to align the _features_ (Auth, RAG) with the new doc.
