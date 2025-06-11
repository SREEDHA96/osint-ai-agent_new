# 🕵️‍♂️ OSINT AI Agent

**LangGraph-based OSINT Intelligence Agent** for investigating public figures, organizations, or topics by retrieving and synthesizing information from multiple open sources using LLMs like Claude, GPT-4o, and Gemini.

---

## 📌 Features

- 🔎 **Query Analysis** — Breaks down natural language queries into structured OSINT tasks  
- 🧭 **Planning Agent** — Chooses relevant sources (news, social, academic, gov, etc.)  
- 📡 **Multi-source Retrieval** — From Google News, LinkedIn (stub), Twitter (stub), OpenCorporates, and more  
- 🔄 **Pivoting Agent** — Extracts related entities and builds a simple entity graph  
- 🧠 **LLM Synthesis** — Uses Gemini or GPT-4o to generate a professional intelligence report  
- 🧾 **Structured Output** — Final report with confidence scoring, retrieval logs, and source links  
- 🗃️ **Persistent Storage** — Saves each investigation with metadata and source traceability  
- 🧪 **Evaluation-ready** — Supports credibility scoring, follow-up queries, and entity mapping  

---

## 🚀 Quickstart

### 1. Clone the Repo

```bash
git clone https://github.com/SREEDHA96/osint-ai-agent_new.git
cd osint-ai-agent_new
```

### 2. Set Up Environment

```bash
python -m venv .venv
.\.venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Add a `.env` File

Create a `.env` file in the root with the following content:

```env
OPENAI_API_KEY=sk-your-openai-key
ANTHROPIC_API_KEY=sk-ant-your-anthropic-key
GOOGLE_API_KEY=your-google-gemini-key
SERPAPI_KEY=your-serpapi-key
```

> ✅ You can use `.env.example` as a template.

### 4. Run an Example Investigation

```bash
python backend/graph.py
```

---

## 🧠 Architecture

```text
+--------------------+
|  Query Analysis    | ← Claude (structured parsing)
+--------------------+
          ↓
+--------------------+
|   Planning Agent   | ← Claude (source selection)
+--------------------+
          ↓
+--------------------+
| Multi-Source Fetch | ← SerpAPI, stubs (Twitter, LinkedIn), OpenCorporates
+--------------------+
          ↓
+--------------------+
|   Pivoting Agent   | ← Claude (related entities, graph)
+--------------------+
          ↓
+--------------------+
|  Synthesis Agent   | ← Gemini 1.5 Pro or GPT-4o
+--------------------+
          ↓
+--------------------+
|  Final Report + DB |
+--------------------+
```

---

## 📦 File Structure

```
osint-ai-agent_new/
├── backend/
│   ├── agents/              # Agent logic (query, planner, retriever, pivot, synthesis)
│   ├── retrieval/           # Retrieval modules (SerpAPI, stubs)
│   ├── database/            # DB schema + persistence logic
│   ├── graph.py             # LangGraph pipeline orchestrator
│   └── test_retrieval_*.py  # Test scripts
├── .gitignore
├── .env.example
├── requirements.txt
└── README.md
```

---

## 📥 Sources Integrated

| Source            | Type            | Status         |
|------------------|------------------|----------------|
| Google News      | News             | ✅ Real (SerpAPI) |
| Twitter/X        | Social Media     | 🔁 Stub         |
| LinkedIn         | Professional Net | 🔁 Stub         |
| OpenCorporates   | Public Records   | 🔁 Stub         |
| Academic Sources | Research         | ⏳ Planned      |

---

## 🔐 Secrets & Safety

- ✅ `.env` is ignored and never committed  
- ✅ `.venv/` removed from history and excluded  
- 🛡️ GitHub push protection enabled  

---

## 📈 Roadmap

- [x] Entity graph + relationship extraction  
- [x] Source credibility scoring  
- [ ] Timeline of key events  
- [ ] Risk scoring system  
- [ ] RAG-based citation-backed answers  

---

## 👨‍💻 Author

**Sreedha Bhakthavalsalan**  
GitHub: [@SREEDHA96](https://github.com/SREEDHA96)

---

## 📄 License

MIT License
