# Physical AI Textbook Engine

**The Future of Robotics Education**

The **Physical AI Textbook Engine** is an AI-native, interactive learning platform designed to teach the next generation of robotics: **Physical AI and Humanoid Robotics**. It combines a structured textbook with an autonomous RAG (Retrieval-Augmented Generation) chatbot to provide a personalized and immersive learning experience.

## 🚀 High-Level Goal

Build a complete robotics learning engine using:

- **Frontend**: Docusaurus (React, TypeScript, Tailwind CSS)
- **Backend**: FastAPI (Python)
- **AI/RAG**: OpenAI Embeddings, Qdrant Cloud (Vector DB), Neon Postgres
- **Agentic Workflow**: Autonomous Codex Agent

## 📚 Course Modules

1.  **The Robotic Nervous System (ROS 2)**: Middleware, Nodes, Topics, URDF.
2.  **The Digital Twin (Gazebo & Unity)**: Physics simulation, rendering, sensors.
3.  **The AI-Robot Brain (NVIDIA Isaac™)**: Isaac Sim, VSLAM, Nav2.
4.  **Vision-Language-Action (VLA)**: LLMs in robotics, Voice-to-Action, Cognitive Planning.

## 🛠️ Tech Stack

- **Framework**: Docusaurus (Classic Preset)
- **Styling**: Infima + Tailwind CSS
- **Database**: Qdrant (Vector), Neon (Relational)
- **Authentication**: Better Auth
- **Deployment**: Vercel (Frontend), Render/Railway (Backend)

## 📦 Installation

### Prerequisites

- Node.js (v18+)
- Python (3.10+)
- Git

### Frontend Setup

```bash
cd frontend
npm install
npm start
```

### Backend Setup

```bash
cd backend
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
pip install -r requirements.txt
uvicorn main:app --reload
```

## 🤖 Autonomous Agent Rules

This project is managed by **Codex**, an autonomous AI agent.

- **Log Everything**: Every interaction is logged in `history/` and `github-commit/`.
- **Spec-Driven**: All changes follow `info.md` and `tasks.md`.
- **Deterministic**: Strict adherence to `instructions.md`.

## 📄 License

Copyright © 2025 Physical AI Textbook Engine. Built with Docusaurus.
