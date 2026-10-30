# Hi, I'm Raditya Perdhevi 👋

**Software Engineer · Cloud & Backend Systems · Applied AI / LLM Systems**

I'm a software engineer with experience across backend systems, cloud infrastructure, mobile development, and game development — with a verified track record of 9,000+ hours and $100K+ earned on Upwork.

These days, I'm particularly interested in what happens *around* the LLM — agent architecture, orchestration, retrieval, memory, context management, evaluation, tools, and the infrastructure required to turn AI experiments into reliable software.

---

## 🔭 What I'm working on

I'm experimenting with the engineering patterns behind production AI systems:

- Agent harnesses, ReAct loops and multi-agent orchestration
- Retrieval (RAG), vector search and episodic memory
- Authorization and tenant isolation for AI tools
- Context and token-budget management
- Tool integration and MCP servers
- LLM evaluation, quality gates and benchmarking
- Local LLM inference

I prefer building these systems from first principles where possible, so I can understand why they work — and where they fail. Most projects below are built in stages, one concern per step, so the reasoning stays readable.

---

## 🧪 Featured Projects

### 📄 [pdf-mcp](https://github.com/perdhevi/pdf-mcp)

An MCP server for per-customer document management and RAG over PDFs — text, scanned and chart-heavy — that answers with citations linking back to the original page.

`Python` · `MCP` · `Qdrant` · `PyMuPDF` · `Tesseract` · `Ollama` · `qwen3-vl` · `Docker`

- Text extraction, OCR and a vision model for charts and figures, all on ingest
- Each customer gets its own Qdrant collection, so answers never mix customers
- Answers cite the source and deep-link to the exact PDF page
- Each model role (embeddings, vision, answers) picks its own provider — Ollama or any OpenAI-compatible API
- One `docker compose up` with sample data, plus a "verify it works" checklist and CI tests

### 🔐 [permission-aware-mcp](https://github.com/perdhevi/permission-aware-mcp)

An MCP server for permission-aware retrieval. **The model can't choose who it is acting for:** caller identity comes only from a verified bearer token, and the database decides tenant membership, roles and document access.

`Go` · `MCP` · `PostgreSQL` · `pgvector` · `OAuth / OIDC` · `Keycloak` · `Docker`

- Tenant isolation and per-document permissions applied *before* retrieval, so search only ever sees what the caller may read
- Offline signed-token demo by default; optional Keycloak login (authorization code + PKCE) with the same behavior
- Every access is written to an audit log
- A prompt-injection demo shows that hostile instructions inside retrieved documents can't unlock confidential ones

Built in six documented phases, each with a change record and reproducible validation steps.

### 🗂️ [obsidian-mcp](https://github.com/perdhevi/obsidian-mcp)

An MCP server that lets AI clients search and read an Obsidian vault and save new notes into an inbox. Runs as one local Node daemon over Streamable HTTP, so Claude Code, Claude Desktop and Hermes Agent share one index.

`Node.js` · `MCP` · `LanceDB` · `Ollama` · `nomic-embed-text`

- Notes split by heading and embedded locally; wikilink graph kept in memory
- File watcher re-indexes on edit, with a startup pass for changes made while it was off
- Single write queue, localhost-only binding, create-only writes

Built by hand with a full [build guide](https://github.com/perdhevi/obsidian-mcp/blob/main/docs/BUILD_GUIDE.md) so others can follow along.

---

## 🏋️ Full-stack: Latihan *(in progress)*

An open-core fitness platform — workouts, reusable training plans, planned-versus-done comparison and body measurements — built as three clients of one API contract.

| Repo | What it is | Stack |
| --- | --- | --- |
| [latihanAPI](https://github.com/perdhevi/latihanAPI) | REST backend, modular monolith | `Go` · `PostgreSQL` · `OpenAPI` · `Docker` |
| [latihan-web](https://github.com/perdhevi/latihan-web) | Browser client, online-only | `TypeScript` · `React` · `TanStack Query` · `Vite` · `Playwright` |
| [latihan_mobile](https://github.com/perdhevi/latihan_mobile) | Offline-first iOS/Android app | `Dart` · `Flutter` · `Drift` |

- Pluggable auth — built-in accounts, Firebase, Amazon Cognito or any OIDC issuer — and the record owner always comes from the verified token, never the request
- Idempotency keys and ETag / `If-Match` for safe retries and concurrent edits
- Users can export or erase all their data; changes are audited without copying values
- Rate limiting, Prometheus metrics, OpenTelemetry traces and load tests
- The web client's types are generated from the API's OpenAPI spec, and CI fails if they drift

The web client is documented as an 11-part build log, one question per part.

---

## 🚀 Shipped Software

### 🎮 Strike Shooter

A space shooter built with Unity and C#, published on iOS and Android.

Shipping it involved much more than gameplay code — mobile performance, UI, progression systems, packaging, release management, and maintaining production builds across two mobile ecosystems.

[App Store](https://apps.apple.com/id/app/strike-shooter/id6736962627?l=id) · [Google Play](https://play.google.com/store/apps/details?id=com.perdhevi.shooter1&pli=1)

### 🧮 Calc Quick

A fast-paced mathematics puzzle game for iOS.

[App Store](https://apps.apple.com/id/app/calc-quick/id1558186528?l=id)

---

## 🛠️ Engineering

**Languages:** `C++` · `C#` · `Swift` · `Python` · `JavaScript / TypeScript` · `Go` · `Dart`

**Backend & Cloud:** `Node.js` · `REST APIs` · `PostgreSQL` · `AWS Lambda` · `AWS ECS` · `Docker` · `Linux`

**AI / LLM:** `MCP` · `LangGraph` · `Ollama` · `Qdrant` · `pgvector` · `LanceDB` · `ChromaDB` · `Agent Harnesses` · `RAG`

**Frontend & Mobile:** `React` · `Flutter` · `iOS` · `Unity`

---

## 🔬 The Lab

Not everything needs to become a product. I build small experiments to understand technologies at a deeper level:

- **[harness-loop-graph](https://github.com/perdhevi/harness-loop-graph)** *(being reworked)* — an agent harness that turns a plain-language request into a planned, built and test-checked application, with benchmark replay against a saved baseline
- **[Support Harness](https://github.com/perdhevi/Support-Harness)** — the four-stage teaching harness that harness-loop-graph grew out of: ReAct loop → ChromaDB episodic memory → token budget → LLM-as-judge quality gate, fully local on Ollama
- **[D&D Multi-Agent Simulator](https://github.com/perdhevi/dnd-LangGraph)** — four LangGraph agents (a Dungeon Master and three players) run a full combat encounter with no human input, with a JSONL event log, React dashboard and Three.js replay
- **Self-hosted infrastructure** — containers, virtualization, local AI infrastructure
- **Game systems** — simulation, procedural systems, AI behavior

---

## 🔗 Find me

- 🌐 [perdhevi.com](https://www.perdhevi.com) — portfolio & engineering notes
- 🏅 [Credly](https://www.credly.com/users/raditya-perdhevi) — verified certifications
- ✍️ [X — @perdhevi](https://x.com/perdhevi)

> *Full-time problem solver, part-time human.*
