# BERU — AI Assistant

[![Live Demo](https://img.shields.io/badge/Live_Demo-varun--kumar--ds.github.io-00C853?style=for-the-badge&logo=render&logoColor=white)](https://varun-kumar-ds.github.io)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)]()
[![Flask](https://img.shields.io/badge/Flask-000000?logo=flask&logoColor=white)]()
[![Groq](https://img.shields.io/badge/Groq_API-LLaMA_3.3_70B-FF6B35)]()
[![Deployed](https://img.shields.io/badge/Deployed-Render-46E3B7?logo=render&logoColor=white)]()

---

## What is BERU?

**BERU** (Built Environment Response Unit) is a context-aware AI assistant deployed as part of my [portfolio website](https://varun-kumar-ds.github.io). It answers questions about my projects, skills, experience, and research using LLM-powered conversational AI with memory.

> **Note:** This is a showcase repository. The source code is maintained privately to prevent copying. This README documents the architecture, tech stack, and capabilities.

---

## Key Features

| Feature | Description |
|---------|-------------|
| **Conversational memory** | Maintains context across multi-turn conversations |
| **Context-aware responses** | Uses a curated knowledge base about my projects and experience |
| **Real-time streaming** | Responses stream token-by-token for a natural chat experience |
| **Portfolio integration** | Embedded directly into my portfolio website |
| **Production deployment** | Live on Render with automatic scaling |

---

## Architecture

```
┌─────────────────────┐     ┌──────────────────┐     ┌─────────────────┐
│   Portfolio Website  │────▶│   Flask Backend  │────▶│    Groq API     │
│   (HTML/CSS/JS)      │◀────│   (Python)       │◀────│  LLaMA 3.3 70B │
└─────────────────────┘     └──────────────────┘     └─────────────────┘
        │                          │
        │                    ┌─────┴──────┐
        │                    │  Knowledge  │
        │                    │    Base     │
        │                    │  (JSON)     │
        │                    └────────────┘
        │
  ┌─────┴──────┐
  │   Render   │
  │  (Hosting) │
  └────────────┘
```

**Request flow:**
1. User types a question in the chat widget on the portfolio site
2. Frontend sends the message + conversation history to the Flask API
3. Flask constructs a prompt with system context from the knowledge base
4. Groq API processes the prompt using LLaMA 3.3 70B
5. Response streams back to the user in real-time

---

## Tech Stack

| Component | Technology | Why |
|-----------|-----------|-----|
| LLM | LLaMA 3.3 70B via Groq | Fast inference, strong reasoning, free tier available |
| Backend | Flask (Python) | Lightweight, easy to deploy, good for API services |
| Frontend | Vanilla JavaScript | No framework overhead, direct DOM manipulation |
| Hosting | Render | Free tier, automatic deploys from Git, SSL included |
| Knowledge | JSON knowledge base | Structured data about projects, skills, experience |

---

## What I Learned

- **Prompt engineering for persona-based chatbots** — crafting system prompts that maintain consistent personality while being informative
- **Conversation memory management** — balancing context window limits with conversation continuity
- **Production deployment** — handling CORS, environment variables, error recovery, and cold starts on Render
- **API integration patterns** — streaming responses, retry logic, and graceful degradation

---

## Try It

Visit [varun-kumar-ds.github.io](https://varun-kumar-ds.github.io) and click the chat icon in the bottom-right corner to talk to BERU.

---

## Connect

- **Portfolio:** [varun-kumar-ds.github.io](https://varun-kumar-ds.github.io)
- **LinkedIn:** [Varun Kumar](https://www.linkedin.com/in/varun-kumar-ai)
- **GitHub:** [Varun-Kumar-DS](https://github.com/Varun-Kumar-DS)
