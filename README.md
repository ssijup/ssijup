<div align="center">

# SPEC-001 · SIJU SURESH

**status** `active` · **version** `4.x` · **environment** `production` · **maintainer** `self`

curiosity-driven engineering — documented

</div>

---

## Abstract

I ask the same question about every system I meet: **why was it built this way?**

It seemed only fair to turn that question on myself. So instead of a profile, this is a spec — architecture, design rationale, known behaviors, changelog. Read it like any good documentation: skim freely, go deep where curious.

---

## 1. System Architecture

```text
                  ┌─────────────────────────────────┐
                  │           INPUT LAYER           │
                  │  unfamiliar systems · problems  │
                  │      the question "why?"        │
                  └────────────────┬────────────────┘
                                   │  no rate limiter (by design)
                                   ▼
                  ┌─────────────────────────────────┐
                  │         PROCESSING CORE         │
                  │  first-principles decomposition │
                  │   read the source · trace the   │
                  │  request · find the constraint  │
                  └────────────────┬────────────────┘
                        ┌──────────┴──────────┐
                        ▼                     ▼
            ┌──────────────────────┐ ┌──────────────────────┐
            │  PERSISTENT STORAGE  │ │     OUTPUT LAYER     │
            │  knowledge domains   │ │   shipped systems    │
            │       (see §3)       │ │       (see §2)       │
            └──────────────────────┘ └──────────────────────┘
```

---

## 2. Production Systems

Every system here started as a question that wouldn't leave me alone.

### `mcp-generator`
**Origin question:** why is wiring LLMs to real-world APIs still manual work?
Turns OpenAPI specifications into production-ready MCP servers — automated code generation with AI-assisted workflows.
`python` `fastapi` `mcp` `codegen`

### `ragboard`
**Origin question:** why can't organizations just talk to their own documents?
A role-aware knowledge platform — query internal docs through retrieval pipelines, vector search, and access-aware answers.
`rag` `vector-search` `langchain` `postgresql`

### `jd-builder`
**Origin question:** why does a hiring document take hours when the intent takes minutes?
Transforms hiring requirements into structured job descriptions and intelligent screening workflows.
`llm-workflows` `fastapi` `structured-generation`

### `iveye`
**Origin question:** why does learning software treat every learner the same?
An adaptive learning platform — AI-assisted education, quiz generation, and personalized pacing.
`adaptive-learning` `llm` `assessment-systems`

---

## 3. Runtime Dependencies

```toml
[core]
language    = "python"
frameworks  = ["fastapi", "django"]
storage     = ["postgresql"]

[ai]
platforms   = ["openai", "langchain"]
patterns    = ["rag", "mcp", "vector-search", "agentic-workflows"]

[infrastructure]
runtime     = ["docker", "linux", "nginx"]
cloud       = ["aws"]

[meta]
disciplines = ["system-design", "distributed-systems", "api-architecture"]
```

---

## 4. Known Behaviors

| ID | Observed behavior | Status |
|----|-------------------|--------|
| `BHV-001` | Recursion on "why?" has unbounded depth | by design |
| `BHV-002` | Cannot use a tool without reading how it works underneath | won't fix |
| `BHV-003` | Treats a REST API as a distributed conversation | documented |
| `BHV-004` | Treats a database schema as compressed business knowledge | documented |
| `BHV-005` | Reads source code before Stack Overflow | escalating |
| `BHV-006` | Considers "it works, don't touch it" an open incident | under review |

---

## 5. Changelog

```text
v4.x   current   AI infrastructure — RAG pipelines, MCP tooling, agentic systems
v3.x             production backend — scalable APIs, multi-service platforms
v2.x             framework depth — Django & FastAPI internals, async, deployment
v1.0             first production deploy; learned the difference between
                 "works on my machine" and "works"
```

---

## 6. Active Branches

```text
research/agentic-workflows       multi-agent coordination patterns
research/distributed-systems     the hard parts, on purpose
feature/mcp-ecosystem            tooling around Model Context Protocol
perf/system-design               architectures that survive scale
```

---

## 7. Telemetry

<p align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=ssijup&show_icons=true&hide_border=true" />
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=ssijup&layout=compact&hide_border=true" />
</p>

---

## 8. API Reference

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | [`/connect`](https://www.linkedin.com/in/siju-suresh-901128200/) | open to conversations about systems, AI infrastructure, and why things work |
| `GET` | [`/repositories`](https://github.com/ssijup?tab=repositories) | the code behind this document |

---

<div align="center">

*Most systems get documented after they stop changing. This one is still in active development.*

`EOF`

</div>
