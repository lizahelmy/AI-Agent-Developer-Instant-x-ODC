# AI Agent Developer - Instant x ODC

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
Hands-on Jupyter notebooks from the training, all running LLM calls through OpenRouter:

| Notebook | Covers |
|---|---|
| `1-langchain_prompt_templates_openrouter_EN.ipynb` | LangChain prompt templates , why raw f-strings don't scale, and how to build reusable templates (e.g. tone/style transformation of customer emails) |
| `2-langchain-output-parsing-openrouter-pydantic.ipynb` | Getting structured (JSON/Pydantic) output from an LLM instead of raw text, using LangChain 1.x |
| `3_langchain_chatbots_memory_openrouter_langgraph.ipynb` | Giving a chatbot memory using LangGraph's `StateGraph` and `thread_id`-based conversation state, replacing the old `ConversationBufferMemory` |
| `4_evaluating_llm_applications_openrouter.ipynb` | Evaluating an LLM application's accuracy: building a document QA chain over a user-uploaded PDF (`InMemoryVectorStore` + retrieval chain) and testing it against data points |
| `5-building_llm_agents_openrouter_gptoss20b_updated.ipynb` | Building a tool-calling LLM agent from scratch with LangChain (custom calculator + Wikipedia tools) using the `gpt-oss-20b` model |
| `crew_openrouter_agentops-Answer.ipynb` | Working version of a 2-agent CrewAI crew (Researcher + Writer) run through OpenRouter's free `gpt-oss-20b:free` model, fully instrumented with AgentOps (session replay, cost tracking, failure detection) |
| `crew_openrouter_agentops-Eror.ipynb` | Same CrewAI + AgentOps setup, kept as a reference for a common integration bug (synchronous `kickoff()` inside a running event loop / deprecated `agentops.end_session()` call) and how it fails |

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
4. Add your own API keys where the notebook prompts for them (e.g. OpenRouter for LLM calls, AgentOps for the CrewAI observability notebook).
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
