# AI-Agent-Developer-Instant-x-ODC

A hands-on 5-day intensive training on building AI Agents , from prompt engineering to multi-agent systems, RAG pipelines, and automation workflows. This repo documents everything covered and includes the runnable workflows I built during the program.

**Program:** Instant × Orange Digital Center
**Track:** AI Agent Developer
**Duration:** 5 Days

---

## Concepts Covered

- Prompt Engineering
- Hugging Face
- LangChain & LangGraph
- Flowise AI Chatflows
- n8n Automation
- RAG (Retrieval-Augmented Generation)
- Embeddings & Vector Databases
- AI Agents & Multi-Agent Systems
- AgentOps & Observability
- API Integration & API Testing with Postman
- Building AI Workflows & Real-World Projects

---

## Repo Structure

```
ai-agent-developer-instant-x-odc/
│
├── n8n/            # Exported n8n automation workflows (.json)
├── flowise/        # Exported Flowise chatflows (.json)
├── notebooks/      # Educational notebooks (LangChain, LangGraph, CrewAI)
└── README.md
```

---

## Projects in This Repo

### 1. RAG System - Flowise
A PDF-based Conversational Retrieval QA chatflow built in Flowise: documents are chunked, embedded with HuggingFace Inference Embeddings, and stored in an in-memory vector store, with an OpenRouter-hosted LLM (Gemini 2.5 Flash) generating grounded answers with chat memory.

### 2. Automation Workflows - n8n
n8n workflows automating tasks such as Telegram bot interactions, Google Sheets/Gmail integrations, and web search tool calls (Tavily) routed through an LLM (OpenRouter).

### 3. Educational Notebooks - LangChain, LangGraph & CrewAI
Hands-on Jupyter notebooks from the training covering LangChain fundamentals (chains, tools, LCEL), LangGraph for building agent workflows/state machines, and CrewAI for multi-agent collaboration.

---

## How to Import & Run

### n8n Workflows

1. Open your [n8n](https://n8n.io) instance (cloud or self-hosted).
2. Go to **Workflows → Import from File**.
3. Select any JSON file from the `n8n/` folder.
4. After import, open each node that requires credentials and connect your own:
   - **Google Sheets / Gmail** → OAuth2 (connect via n8n credentials manager)
   - **Telegram** → Bot token (create a bot via [@BotFather](https://t.me/BotFather))
   - **Tavily** → API key from [tavily.com](https://tavily.com)
   - **OpenRouter** → API key from [openrouter.ai](https://openrouter.ai)
5. Activate the workflow.

### Flowise Chatflows

1. Open your [Flowise](https://flowiseai.com) instance.
2. Go to **Chatflows → Import**.
3. Select any JSON file from the `flowise/` folder.
4. Click the credential field on each node that requires one and connect:
   - **HuggingFace Inference Embeddings** → API key from [huggingface.co](https://huggingface.co/settings/tokens)
   - **OpenRouter** → API key from [openrouter.ai](https://openrouter.ai)
5. Save and start chatting.

### Notebooks

1. Open the `notebooks/` folder.
2. Launch with Jupyter Notebook/Lab, or open directly in Google Colab / VS Code.
3. Install any required packages listed at the top of each notebook (e.g. `langchain`, `langgraph`, `crewai`).
4. Add your own API keys where the notebook prompts for them (e.g. OpenRouter, Hugging Face).
5. Run the cells in order.

---

## Tech Stack & Tools

| Category | Tools |
|---|---|
| Agent Frameworks | LangChain, LangGraph, CrewAI |
| No-Code / Low-Code | Flowise AI, n8n |
| Models & Inference | Hugging Face (embeddings), OpenRouter (Gemini 2.5 Flash) |
| Search / Retrieval | Tavily |
| Vector Databases | In-memory vector store (Flowise built-in) |
| API Testing | Postman |
| Observability | AgentOps |

---

## Acknowledgments

This training was delivered by **Instant** in partnership with **Orange Digital Center**. Huge thanks to the trainers and mentors for a packed, hands-on 5 days.

---

## License

This project is licensed under the MIT License.

## Author

Built and documented by Liza Hatem as part of the AI Agent Developer training.
