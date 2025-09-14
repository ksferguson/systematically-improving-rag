---
title: Systematically Improving RAG — Intro
description: Course overview and expectations
authors:
  - Jason Liu
date: 2025-01-01
theme: seriph
class: text-left
drawings:
  persist: false
highlighter: shiki
lineNumbers: true
fonts:
  mono: JetBrains Mono
  sans: Inter
  serif: Bitter
download: true
presenter: true
---

# Systematically Improving RAG

Building reliable, production-grade retrieval-augmented generation.

<br>

By Jason Liu

---

## Today’s Plan

- Course overview and syllabus highlights
- What we’ll learn today (foundations + logistics)
- Expected outcomes for this session
- Changes since v1: agents, longer context, workflow shifts
- Inverted classroom: office hours, guests, credits

---

## Outcomes Today

- Understand how the course is structured and assessed
- Identify today’s core learning goals and takeaways
- Learn how agents and longer context affect our approach
- Know when/where to get help (office hours, support)

---

## Overview & Learning Outcomes

### What This Course Covers
- Foundations of retrieval-augmented generation (RAG)
- Systematic evaluation and improvement cycles
- Data pipelines, chunking, and retrieval quality
- Generation quality, citations, and guardrails
- Routing, tools-as-APIs, and architectures that scale

### Learning Outcomes
- Measure retrieval with precision/recall and build evals early
- Turn evaluations into training data and reranker tuning
- Design UX that collects feedback to drive improvements
- Segment queries/users to prioritize work with a roadmap
- Build specialized indices; route queries to the right tools
- Operate RAG in production with cost, latency, reliability in mind

---

## Key Insights

- Good retrieval beats clever prompting
- Similarity is subjective—train for your objective
- Feedback is fuel—design UX to capture signals
- Two-level success: P(right tool) × P(success | tool)
- Local beats global—specialized indices outperform monoliths
- Production matters: cache, monitor, degrade gracefully

---

## What’s Changed Since v1

- Agents/tool use more reliable; planning loops improving
- Agents now practical beyond demos: route, call tools, validate
- Re‑rankers commonplace; embedding choices consolidated
- Prompt caching widespread; costs shift with longer contexts
- Better PDF/diagram extraction; richer citations in UIs
- Stronger eval tooling; more teams run continuous tests

---

## Agents Are Working — How We Adapt

- Treat agents as orchestrators, not magic: tools-as-APIs + metrics
- Constrain tasks; add validation and replayable traces
- Retrieval isn’t always the bottleneck; measure first
- Prefer deterministic tools for critical steps; log decisions
- Update syllabus: routing patterns, dynamic examples, guardrails

---

## Agents: Form Factors

- Chat assistants: task routing, interactive clarification, citations
- Report generators: compile sources → synthesize → validate outputs
- Structured extraction: ETL from PDFs/images/tables with validation
- Workflow automations: search → filter → compare → notify

Key pattern: agents select and compose tools, not just prompts.

---

## Tool Design Matters (Workshops 4–6)

1) Discover the tools you need
- Segment queries; identify recurring intents and capabilities
- Define clear interfaces (inputs/outputs, constraints)

2) Implement specific tools that feel like Search
- Text, image, table, and SQL retrievers with parameters
- Deterministic behavior, good errors, and observability

3) Evaluate routing + retrieval together
- Per-tool recall/precision + confusion matrices
- End‑to‑end task success with traces and guardrails

---

## Evaluations Are Evolving

- Keep precision/recall for retrieval and routing baselines
- Add end‑to‑end evals: task success, citations, validation pass rate
- Introduce LLM‑as‑judge with tight rubrics + spot audits
- Track tool call correctness, retry rates, and constraint violations
- Bring eval design questions to office hours for live critique

---

## Context Is Getting Longer

- Tradeoffs: write-time processing vs read-time expansion
- Summaries + RAPTOR for very long docs; cite spans/boxes
- Prompt caching lowers cost of big few-shot contexts
- Still optimize retrieval: top-K + rerank > dump everything

---

## Syllabus (Sessions 0–3)

- Session 0: Product mindset; RAG as a recommender; improvement flywheel
- Session 1: Synthetic data and retrieval evals; precision/recall; baselines
- Session 2: From evals to training data; reranking; embedding fine-tuning
- Session 3: UX that collects data; streaming; chain of thought; validation

---

## Syllabus (Sessions 4–6)

- Session 4: Topic modeling; query segmentation; prioritization frameworks
- Session 5: Specialized indices; multimodal search (docs, images, tables, SQL)
- Session 6: Query routing; tools-as-APIs; single vs multi-agent; measurement

---

## Case Study: WildChat

- End-to-end RAG assistant with telemetry, evals, and feedback loops
- Incremental upgrades per session mapped to workshop chapters
- Final deliverable: measurable improvement against your eval suite

---

## Inverted Classroom Model

- Pre-reads: short chapters/workshops before live session
- Live: demos, debugging, discussion; fewer slides, more code
- Practice: labs + small weekly deliverables with metrics
- Reflect: office hours to review failures and iterate

---

## Office Hours & Guests

- Multiple office hours weekly across time zones
- Bring queries, logs, evals; we’ll debug together
- Guest lectures from practitioners; Q&A focused on tradeoffs
- Credits/support: contact Marian — support at jxnl.co (support@jxnl.co)

---

## Office Hours: Format & Recordings

- All sessions recorded; notes circulated afterwards
- Some weeks are topic‑focused—come with lots of questions
- Goal: dialogue about course work, current events, and your ideas
- Please attend and bring your own questions; interactive by design
- Scheduling: occasional reschedules (e.g., travel/OpenAI Dev Day); ample notice

---

## Align With Your Work

- Designed to complement your day job or current project
- Take each week as it comes—apply concepts where they fit
- Share constraints; we’ll tailor examples in office hours
- Deliverables focus on measurable deltas; scope is flexible

---

## Coding Exercises Are Optional

- Exercises provided for practice and reference
- You can skip coding and still succeed via metrics + analysis
- Bring questions, logs, and evals instead of code if needed
- Goal: outcomes over checklists

---

## From RAG To Context Engineering

- Agents are reliable enough to shift focus
- Emphasis on context design, routing, validation, guardrails
- Larger contexts change prompt + retrieval strategies
- We’ll gradually blend RAG and context engineering patterns

---

## Course Roadmap & Cohorts

- November: 3‑week sprint version to create more focused time
- February: context engineering edition (agents‑first workflows)
- Too much material in 6 weeks? You’re not alone—common feedback
- Leave us a good review and we’ll invite you to November sprint

---

## What You’ll Learn

- Problem framing for RAG systems
- Data pipelines and chunking strategies
- Indexing, retrieval, and ranking
- Generation prompts and guardrails
- Evaluation, telemetry, and iteration

---

## Course Structure

- Case study: WildChat (end-to-end)
- Labs: focused exercises per module
- Workshops: deeper dives with take-home tasks

---

## Logistics & Tools

- Language/runtime: Python 3.11
- Repo tasks: `uv run ruff check --fix`, `uv run ruff format`, `uv run pytest -q`
- Docs: `mkdocs serve` (local) / `mkdocs build` (CI)
- Optional book build: `bash build_book.sh` (pandoc + mermaid CLI)
- Slides: Slidev in `intro-slides/`

---

## Expectations

- Use Python 3.11, type hints, tests
- Keep secrets in `.env` (never in Git)
- Prefer config via environment variables

---

## Repo Tour

- `latest/`: current course code and case study
- `docs/`: MkDocs sources; build/serve docs
- `md/`: notebook exports and images

---

## Tooling

- Ruff for lint/format
- Pytest (with asyncio)
- MkDocs for docs

---

## Weekly Rhythm

- Early week: Lecture + demo
- Midweek: Lab time; office hours; PR feedback
- End of week: Small deliverable against stated objectives
- Standing rule: show metrics, diffs, or UX proof (not vibes)

---

## Assessment & Deliverables

- Weekly: targeted improvement with before/after metrics
- Mid-course: retrieval eval pack + reranker experiment
- Final: end-to-end improvement of WildChat or your own dataset
- Evidence: dashboards/reports, reproducible scripts, short write-up

---

## Evaluation Philosophy

- Prefer objective retrieval metrics early (precision/recall)
- Track P(success) = P(right tool) × P(success | tool)
- Bootstrap with synthetic data; replace with real signals over time
- Keep experiments small, hypotheses explicit, artifacts checked in

---

## Feedback & Office Hours

- Signals: thumbs, citation actions, query refinements, dwell time
- Enterprise loop: Slack negative feedback → evals + changelogs
- Office hours: bring failures, logs, and hypotheses; debug live

---

## Policies & Norms

- No secrets in Git; `.env` + `python-dotenv`
- Respect production constraints: cost, latency, reliability
- Prefer small PRs; describe problem, change, and measurement
- Help each other: code review > private DMs

---

## How to Succeed

- Start logging early; evals before features
- Instrument everything; automate the boring bits
- Design UX that turns clicks into labels
- Local maxima first: specialized indices for top segments
- Communicate with numbers: deltas per change

---

## Tech Setup Checklist

- Python 3.11 ready; `uv install` completes
- Lint/format: `uv run ruff check --fix` + `uv run ruff format`
- Tests: `uv run pytest -q`
- Docs: `mkdocs serve` runs locally
- Slides: `pnpm install` in `intro-slides/` (optional)

---

## Suggested Project Tracks

- Documentation QA (internal or OSS docs)
- Support assistant with hybrid + reranker
- Image/table-heavy retrieval with synthetic descriptions
- Structured extraction + text-to-SQL with validation

---

## Reading & Resources

- Workshops under `docs/workshops/`
- RAPTOR for long docs; dynamic few-shot for routers
- Monitor: latency (p95), cost/query, recall@K, cache hit rates
- Anti-patterns list in slides + docs

---

## Risks & Anti-Patterns

- Vibes-based evals; no test data; prompt overfitting
- One monolithic index for everything
- Thresholding by score vs always returning top-K
- No streaming; hidden feedback; no citations

---

## Today’s Agenda

1. RAG overview and pitfalls
2. Case study walkthrough
3. Baseline evaluation
4. Iteration plan

---

## Links

- Course docs in this repo
- Workshop materials under `docs/workshops/`

---

## FAQ

- Can I use my own dataset? Yes—keep it reproducible and anonymized.
- Do I need GPUs? No; cloud notebooks optional for fine-tuning.
- How are we graded? You’ll self-assess via metrics and present deltas.
- What if data is private? Use synthetic proxies + local evals.

---

## Next Steps

- Clone repo and set up environment
- Skim `docs/workshops/index.md` for the roadmap
- Pick a project track and define a baseline eval by EOW
- Book office hours slot if blocked

---

## Q&A

Questions, goals, and constraints.

---

layout: center
class: text-center

# Thanks!

Slides built with Slidev.

---

notes: |
  Presenter notes appear here. Use `s` to open presenter view.
  - Timebox intro to 10 minutes
  - Poll the audience for tooling familiarity
