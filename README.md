# 🤖 Agentic AI — Engineering Roadmap

A curated, opinionated learning path for engineers moving into agentic AI. Sequenced to build real intuition, not just API familiarity. No math prerequisites — but the rabbit holes are there if you want them.

> 90% of AI projects is just building a good RAG pipeline, prompting and API calls lol. Master that before chasing agents.

---

## 📋 Table of Contents

1. [Python Basics & Data Structures](#01--python-basics--data-structures)
2. [LLM & Embedding Intuition](#02--llm--embedding-intuition)
3. [LangChain & LCEL](#03--langchain--lcel)
4. [Retrieval Augmented Generation (RAG)](#04--retrieval-augmented-generation-rag)
5. [Agentic AI with LangGraph](#05--agentic-ai-with-langgraph)
6. [Beyond Tutorials — Experience Territory](#06--beyond-tutorials--experience-territory)
   - [Multi-Agent Systems](#mod-06--multi-agent-systems)
   - [Token & Rate Limit Management](#mod-07--token--rate-limit-management)
   - [Security](#mod-08--security)
   - [Evaluation](#mod-09--evaluation)
7. [Contributing](#contributing)

---

## Tier 1 — Foundation 

Enough to contribute to most AI projects, this is what I do most of the time. Resources are curated — follow them in order.

---

### 01 — Python Basics & Data Structures

Start here if you're new to Python or need to solidify fundamentals. Covers syntax, data structures, file I/O, and basic libraries — everything you'll lean on when building chains and pipelines.

| Type | Resource |
|------|----------|
| 🎓 Course | [Python for Everybody Specialization — Coursera](https://www.coursera.org/specializations/python) |

> **Skip if:** you can already write a working FastAPI endpoint and aren't scared of list comprehensions.

---

### 02 — LLM & Embedding Intuition

You don't need the math to build production AI systems, seriously I am horrible at math. You do need to understand what an embedding is, what a token is, why context windows matter, and roughly what happens inside a transformer. These three videos give you exactly that.

| Type | Resource |
|------|----------|
| ▶️ Video | [But what is a GPT? — 3Blue1Brown](https://www.youtube.com/watch?v=wjZofJX0v4M) |
| ▶️ Video | [Attention in transformers, visually explained — 3Blue1Brown](https://www.youtube.com/watch?v=eMlx5fFNoYc) |
| ▶️ Video | [How might LLMs store facts — 3Blue1Brown](https://www.youtube.com/watch?v=9-Jl0dxWQs8) |
| ▶️ Optional | [Full Neural Networks playlist — 3Blue1Brown](https://www.youtube.com/playlist?list=PLZoTAELRMXVNjD07iDEHmS9b0-2qe97sM) |

> **Optional:** If you like math and have the time, go through the full playlist. It's worth it.

---

### 03 — Prompt Engineering
 
P.S We use chatgpt to write prompt and the claude to tune it lol. Bad prompt is the reason if you ask model for chakka it will give manga. But jokes aside, this is the section most people skip, and it shows in their output. It doesn't matter how well your chain is structured if you can't reliably get the model to do what you want. Prompt engineering is the interface between your intent and the model's behaviour — and in agentic systems, where LLMs are writing tool calls and routing decisions, a badly written prompt compounds across every step. 
 
**What to learn:**
- [ ] Zero-shot vs few-shot prompting — when each works and why
- [ ] System prompt design — role, context, constraints, output format
- [ ] Chain-of-thought prompting — getting models to reason before answering
- [ ] Output formatting — structured outputs, JSON mode, XML tags
- [ ] Prompt chaining — breaking complex tasks into sequential prompts
- [ ] Common failure modes — hallucination, sycophancy, instruction drift
| Type | Resource |
|------|----------|
| 📄 Docs | [Anthropic Prompt Engineering Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) |
| 🎓 Course | [ChatGPT Prompt Engineering for Developers — DeepLearning.AI](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/) |
| 📄 Docs | [OpenAI Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering) |
 
> **Why both provider guides?** Anthropic and OpenAI have meaningfully different model behaviours. Reading both gives you transferable principles rather than model-specific tricks.
 
> **Milestone:** Before moving to LangChain, write prompts that reliably produce structured JSON output, handle edge cases gracefully, and don't hallucinate on out-of-scope questions. If you can't do this with raw API calls, you'll struggle to debug it inside a chain.
 
---

### 04 — LangChain & LCEL

Understand what LangChain is solving for before you write a single line of it. Then learn LCEL (LangChain Expression Language) — the declarative way to compose chains. Good free resources are sparse here; the two below are the best available.

| Type | Resource |
|------|----------|
| ▶️ YouTube | [LangChain playlist — Krish Naik](https://youtube.com/playlist?list=PLZoTAELRMXVOQPRG7VAuHL--y97opD5GQ) |
| 🎓 Course | [LangChain for LLM Application Development — Coursera](https://www.coursera.org/learn/langchain) |
| 📄 Docs | [LangChain official documentation](https://python.langchain.com/docs/introduction/) |

> **Note:** There are no great free resources for LangChain. Don't waste time hunting — use what's above and supplement with the official docs.

---

### 05 — Retrieval Augmented Generation (RAG)

This is the most critical module. Before building agents, you need to understand how to efficiently feed data to an LLM — context limits, chunking strategies, embeddings, vector retrieval, and reranking. Most production AI projects are RAG projects with a thin agent layer on top.

**What to learn:**
- [ ] Understand context window limits and why they constrain everything
- [ ] Chunking strategies — fixed, semantic, hierarchical
- [ ] Vector stores — pgvector, Chroma, Pinecone (pick one and go deep)
- [ ] Build a working retrieval pipeline before moving on

| Type | Resource |
|------|----------|
| ▶️ YouTube | [Complete RAG playlist — Krish Naik](https://www.youtube.com/playlist?list=PLZoTAELRMXVNpYGFte4UXqtE1Jfg3oRM6) |

> Also partially covered in the LangChain playlist above.

---

### 06 — Agentic AI with LangGraph

This is what separates an LLM wrapper from an actual agent. Learn what makes agentic AI different from a basic API call, then go deep on LangGraph — the best framework for building stateful, controllable agents.

**What to learn:**
- [ ] What agentic AI actually means — the definition, not the buzzword
- [ ] Building a simple graph in LangGraph
- [ ] Tools — what they are, how to bind them to an agent
- [ ] State and state management across nodes
- [ ] Persistence — threads and checkpointers
- [ ] Human-in-the-loop patterns

| Type | Resource |
|------|----------|
| 🏫 Academy | [Intro to LangGraph — LangChain Academy](https://academy.langchain.com/courses/intro-to-langgraph) |

> The only course you need for this module. Go through it fully.

> **Milestone:** If you've reached this point, you can build and ship a real agentic AI system. That puts you ahead of the majority of "AI engineers" on the market.

---

## Tier 2 — Experience Territory

The point of no return, there are no courses — only problems. The resources here are docs. This is where the trouble begins. Good for interview, makes you stand apart from crowd

---

### 07 — Beyond Tutorials & Experience Territory

#### MOD-07 — Multi-Agent Systems

Orchestrator/worker patterns, agent handoffs, conflict resolution, A2A vs MCP, distributed coordination. There's no single course — read the LangGraph multi-agent docs, study production architectures, and build something non-trivial.

| Type | Resource |
|------|----------|
| 📄 Docs | [LangGraph multi-agent concepts](https://langchain-ai.github.io/langgraph/concepts/multi_agent/) |

---

#### MOD-08 — Token & Rate Limit Management

Optimising token usage, managing context budgets across long agent loops, handling provider rate limits gracefully. Learned by running agents in production and watching them fail expensively.

**What to understand:**
- [ ] Context window budget allocation across agent steps
- [ ] Token counting before API calls, not after
- [ ] Exponential backoff and retry strategies
- [ ] Detecting and breaking agent loops

*No single resource. This comes from building, failing, and reading GitHub issues.*

---

#### MOD-09 — Security

The attack surface of agentic systems is qualitatively different from traditional software. Prompt injection, tool hijacking, confused deputy, agent hijacking — these aren't theoretical in production systems with real tools and real data.

| Type | Resource |
|------|----------|
| 🛡️ Reference | [OWASP LLM Top 10](https://owasp.org/www-project-top-10-for-large-language-model-applications/) |

---

#### MOD-10 — Evaluation

You can't improve what you don't measure. RAG evaluation and agent evaluation are distinct problems requiring different frameworks and metrics.

| Type | Resource |
|------|----------|
| 🧪 RAG eval | [RAGAS — RAG evaluation framework](https://docs.ragas.io/) |
| 🧪 Agent eval | [DeepEval — LLM evaluation framework](https://docs.confident-ai.com/) |

> RAGAS covers faithfulness, answer relevancy, context precision/recall. DeepEval covers G-Eval, custom metrics, and CI integration.

---

*Take it at your own pace, this is just a guideline*
