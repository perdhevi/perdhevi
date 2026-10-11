# Hi, I'm Raditya Perdhevi 👋

**Software Engineer · Cloud & Backend Systems · Applied AI / LLM Systems**

I'm a software engineer with experience across backend systems, cloud infrastructure, mobile development, and game development — including 9,000+ verified hours of freelance engineering on Upwork.

These days, I'm particularly interested in what happens *around* the LLM — agent architecture, orchestration, memory, context management, evaluation, tools, and the infrastructure required to turn AI experiments into reliable software.

---

## 🔭 What I'm working on

I'm experimenting with the engineering patterns behind production AI systems:

- Agent orchestration and ReAct loops
- Multi-agent systems
- Retrieval and episodic memory
- Context and token-budget management
- Tool integration and MCP servers
- LLM evaluation and quality gates
- Local LLM inference

I prefer building these systems from first principles where possible, so I can understand why they work — and where they fail.

---

## 🧪 Featured Projects

### 🗂️ [vault-mcp](https://github.com/perdhevi/obsidian-mcp)

An MCP server that lets AI clients search and read an Obsidian vault, and save new notes into an inbox folder. Runs as a single local Node daemon over Streamable HTTP, so Claude Code, Claude Desktop and Hermes Agent share one index.

`Node.js` · `MCP` · `LanceDB` · `Ollama` · `nomic-embed-text`

- Notes split by heading and embedded locally — no API keys
- LanceDB for vectors; the wikilink graph kept in memory
- File watcher re-indexes on edit, with a startup reconciliation pass for changes made while the server was off
- All index writes go through one queue, so the watcher and tools never conflict
- Localhost-only binding, client path validation, create-only writes into the inbox

Built by hand, step by step, with a full [build guide](https://github.com/perdhevi/obsidian-mcp/blob/main/docs/BUILD_GUIDE.md) so others can follow along.

### 🤖 [Support Harness](https://github.com/perdhevi/Support-Harness)

A progressively-built AI agent harness exploring what's required beyond a basic LLM call. Each stage adds exactly one harness-level concern:

`ReAct loop + KB tools` → `Episodic memory` → `Token budget` → `LLM-as-judge`

- ReAct-style agent loop driven by `finish_reason`
- ChromaDB episodic memory with a relevance threshold
- Token-budget tracking and tool-output trimming
- LLM-as-judge quality gate with bounded retries
- Fully local inference with Ollama — no API keys

The goal isn't just to build an agent, but to understand the engineering decisions required to make one reliable, observable, and maintainable.

### 🎲 [D&D Multi-Agent Simulator](https://github.com/perdhevi/dnd-LangGraph)

An experiment in autonomous multi-agent interaction: four agents (a Dungeon Master and three party members) play out a full combat encounter with no human input, while the system logs a structured event stream that can be inspected and replayed.

`Python` · `LangGraph` · `Ollama` · `Qwen` · `React` · `Three.js`

- Multi-agent orchestration with LangGraph
- Structured LLM output
- JSONL event logging
- React dashboard and Three.js animated replay
- Fully local inference

---

## 🚀 Shipped Software

### 🎮 Strike Shooter

A space shooter built with Unity and C#, published on iOS and Android.

Shipping it involved much more than gameplay code — mobile performance, UI, progression systems, packaging, release management, and maintaining production builds across two mobile ecosystems.

[App Store](https://apps.apple.com/id/app/strike-shooter/id6736962627?l=id) · [Google Play](https://play.google.com/store/apps/details?id=com.perdhevi.shooter1&pli=1)

### 🧮 Calc Quick

A fast-paced mathematics puzzle game for iOS.

[App Store](https://apps.apple.com/id/app/calc-quick/id1558186528?l=id)

These projects are part of my ongoing interest in building software that goes beyond prototypes and reaches actual users.

---

## 🛠️ Engineering

**Languages:** `C++` · `C#` · `Swift` · `Python` · `JavaScript / TypeScript`

**Backend & Cloud:** `Node.js` · `REST APIs` · `AWS Lambda` · `AWS ECS` · `Docker` · `Linux`

**AI / LLM:** `LangGraph` · `Ollama` · `MCP` · `LanceDB` · `ChromaDB` · `Agent Systems`

**Frontend & Mobile:** `React` · `iOS` · `Unity`

---

## ☁️ Cloud & Architecture

I enjoy designing systems as much as implementing them — cloud-native and serverless architecture, API and backend design, infrastructure automation, self-hosted infrastructure, and AI application architecture.

→ [Verified credentials on Credly](https://www.credly.com/users/raditya-perdhevi)

---

## 🔬 The Lab

Not everything needs to become a product. I build small experiments to understand technologies at a deeper level:

- **[harness-loop-graph](https://github.com/perdhevi/harness-loop-graph)** *(in progress)* — a harness that takes a plain-language request and builds the application it asks for: plans, writes, runs, fixes and verifies it. Standard-library Python, built in stages like Support Harness.
- **Self-hosted infrastructure** — containers, virtualization, local AI infrastructure
- **Game systems** — simulation, procedural systems, AI behavior

---

## 🔗 Find me

- 🌐 [perdhevi.com](https://www.perdhevi.com) — portfolio & engineering notes
- 🏅 [Credly](https://www.credly.com/users/raditya-perdhevi) — verified certifications
- ✍️ [X — @perdhevi](https://x.com/perdhevi)

> *Full-time problem solver, part-time human.*
