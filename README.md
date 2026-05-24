# Synapse — Enterprise AI Platform

A production-grade AI assistant platform combining **Notion + Obsidian + AI Memory + Knowledge Graph + Agent Dashboard**.

![Synapse Platform](https://img.shields.io/badge/Status-Production--Ready-success)
![Tech Stack](https://img.shields.io/badge/Stack-React%20%7C%20TypeScript%20%7C%20Tailwind-blue)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 🌟 Overview

**Synapse** is a complete frontend simulation of an enterprise AI platform that represents:

- **FastAPI backend** (simulated with mock data)
- **PostgreSQL** with **pgvector** for vector storage
- **LangGraph** orchestration for autonomous agents
- **OpenAI / Ollama** integration (represented in UI)
- **Apache AGE** for knowledge graph storage
- **Hybrid retrieval** (dense + sparse + reranking)

---

## 🎯 Core Modules

### 1. **Workspace** (Notion-style)
- Block-based document editor with AI slash commands
- Breadcrumb navigation
- Related memories context panel
- Real-time collaboration indicators

### 2. **Knowledge Graph** (Obsidian-style)
- Interactive node-link visualization
- Cluster filtering (concept, person, project, entity, memory)
- Hover-to-highlight connections
- Live stats overlay (nodes, edges, clusters)

### 3. **Memory Vault** (AI Memory Platform)
- Semantic search with hybrid retrieval
- Memory types: episodic, semantic, procedural
- Embedding visualization (3072-d vectors)
- Similarity scores with progress bars
- Retrieval pipeline breakdown (dense → sparse → RRF → rerank)

### 4. **Agents Dashboard** (LangGraph Orchestration)
- Live agent cards with status indicators
- LangGraph state machine visualization
- Real-time token usage and throughput metrics
- Execution logs with streaming
- Progress bars for running tasks

### 5. **IDE** (AI Code Editor)
- File tree explorer
- Syntax-highlighted code editor
- AI-powered code suggestions with diff view
- Confidence scores and reasoning
- Accept/Reject workflow

### 6. **Flows** (Workflow Builder)
- Node-based visual workflow editor
- 6 node types: trigger, llm, tool, branch, human, output
- Animated data flow visualization
- LangGraph orchestration backend

### 7. **Insights** (Analytics)
- Metric cards with sparklines
- Agent performance leaderboard
- Token spend by model
- Retrieval quality metrics (Hit@5, Hit@10, MRR)
- Time-series charts

---

## 🎨 Design System

### Color Palette
- **Base**: `#0a0b0f` (deep slate)
- **Primary**: Violet-to-Fuchsia gradient (`#8b5cf6` → `#ec4899`)
- **Accent**: Cyan (`#22d3ee`), Emerald (`#10b981`), Amber (`#f59e0b`)
- **Text**: Slate scale (`#e2e8f0` → `#64748b`)

### Typography
- **Body**: Inter (system fallback)
- **Code**: JetBrains Mono (system fallback)
- **Features**: `cv02`, `cv03`, `cv04`, `cv11` for tabular numbers

### UI Patterns
- Glassmorphic panels with backdrop blur
- Subtle glow effects on active elements
- Smooth transitions (300ms ease)
- Custom scrollbars (thin, transparent)

---

## 🚀 Features

### Command Palette (`⌘K`)
- Quick actions (new doc, start agent, search memory)
- Recent items
- Fuzzy search across all content

### AI Assistant (Floating)
- Context-aware chat interface
- Simulated responses based on workspace data
- Persistent conversation history

### Keyboard Shortcuts
- `⌘K` - Command palette
- `⌘N` - New document
- `⌘M` - Search memory
- `⌘G` - Open graph
- `⌘I` - Open IDE
- `Esc` - Close modals

---

## 📦 Tech Stack

### Frontend
- **React 19** with TypeScript
- **Tailwind CSS 4** for styling
- **Vite** for build tooling
- **SVG** for visualizations (graph, charts, workflows)

### Simulated Backend
- **FastAPI** (represented in mock data)
- **PostgreSQL + pgvector** (HNSW indexing)
- **Apache AGE** (knowledge graph)
- **LangGraph** (agent orchestration)
- **OpenAI API** (embeddings, completions)

### Data Layer
- Mock data in `src/data.ts`
- Type-safe with full TypeScript coverage
- Realistic enterprise scenarios

---

## 🏗️ Architecture

```
src/
├── App.tsx              # Main shell, routing, layout
├── components.tsx       # Sidebar, Topbar, CommandPalette, AIChat
├── sections.tsx         # All 7 module views
├── data.ts             # Mock data (docs, agents, memory, etc.)
├── index.css           # Global styles, animations, scrollbar
└── utils/
    └── cn.ts           # Tailwind merge utility
```

---

## 🎭 Mock Data Highlights

### Documents
- Product Strategy Q1 2026
- Agent SDK Design Notes
- Architecture Review (Jan 14)
- Customer: Acme Corp Pilot

### Agents
- **Researcher** - Synthesizes docs into briefs
- **Code Reviewer** - Reviews PRs against conventions
- **Meeting Scribe** - Transcribes and summarizes
- **Customer Success** - Drafts replies
- **Indexer** - Embeds documents into pgvector
- **IDE Companion** - Inline completions

### Memory Items
- Hybrid retrieval benchmarks (0.94 similarity)
- Jan 14 Architecture Review decisions
- Deploy LangGraph agent runbook
- Acme Corp ingestion status

---

## 🔧 Development

### Install
```bash
npm install
```

### Run
```bash
npm run dev
```

### Build
```bash
npm run build
```

### Preview
```bash
npm run preview
```

---

## 📊 Performance

- **Build size**: ~325 KB (gzipped: ~92 KB)
- **Modules**: 35 transformed
- **Build time**: ~1.5s
- **First paint**: < 1s (simulated data)

---

## 🎨 Visual Highlights

### Knowledge Graph
- Clustered layout with 5 node types
- Bezier curve edges with hover highlighting
- Ambient glow effects
- Real-time node/edge stats

### Agents Dashboard
- Live-updating token counters
- Animated progress bars
- LangGraph state visualization
- Streaming execution logs

### Memory Vault
- Embedding dimension visualization (24 bars)
- Retrieval pipeline breakdown
- Similarity score progress rings
- Type-based filtering (episodic, semantic, procedural)

### Flows
- Node-based workflow editor
- Animated data flow (moving dots on edges)
- 6 node types with distinct styling
- Orchestrator metadata panel

---

## 🧠 AI Features (Simulated)

### Hybrid Retrieval Pipeline
1. **Embed query** (12ms)
2. **Dense search** via HNSW (58ms)
3. **Sparse search** via BM25 (34ms)
4. **RRF fusion** k=60 (8ms)
5. **Cross-encoder rerank** (30ms)

**Total p95**: 142ms

### Agent Orchestration
- Checkpointed state machines (PostgreSQL)
- Human-in-the-loop workflows
- Tool routing with conditional edges
- Streaming responses

### Code Suggestions
- Project-aware completions
- Diff view with accept/reject
- Confidence scoring
- Reasoning explanations

---

## 📝 License

MIT

---

## 🙏 Credits

Built with:
- React 19
- Tailwind CSS 4
- Vite
- TypeScript

Design inspiration:
- Notion (workspace)
- Obsidian (knowledge graph)
- Linear (dashboard)
- Cursor (IDE)
- LangChain (agents)

---

## 🚀 Future Enhancements

- [ ] Real FastAPI backend
- [ ] PostgreSQL + pgvector integration
- [ ] Live LangGraph agent execution
- [ ] WebSocket streaming for logs
- [ ] Multi-tenant authentication
- [ ] Real-time collaboration (CRDT)
- [ ] Voice-to-text for meeting scribe
- [ ] Custom model fine-tuning UI

---

**Built for deep work · Saved locally on your device**
