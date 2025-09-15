---
title: Systematically Improving RAG — Intro
description: Cohort kickoff — syllabus, logistics, key insights, outcomes
authors:
  - Jason Liu
date: 2025-01-01
tags:
  - rag
  - course
  - intro
  - syllabus
  - agents
  - retrieval
  - evaluation
  - context-engineering
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
exportFilename: systematically-improving-rag-intro
aspectRatio: 16/9
colorSchema: auto
slideNumber: true
---

# Systematically Improving RAG

Building reliable, production-grade retrieval-augmented generation.

<br>

By Jason Liu

---

# Today’s Plan

- Course overview and syllabus highlights
- Goals, outcomes, and key logistics
- Watch the first session, then office hours
- Changes since v1: agents, longer context, workflow shifts

---

# Introduce yourself!

- Where are you calling in from?
- What are you working on?
- What are your goals for the course?

---


# About the Instructor

- University of Waterloo (2012–2017): Computational Mathematics, Mathematical Physics; computational linear algebra → matrix factorization/embedding models → retrieval and deep learning
- Meta (2017): Content policy/moderation, public risk & safety; built dashboards and search tools to surface harmful content
- Stitch Fix (2018–2023): CV + multimodal retrieval; VAEs/GANs for GenAI; ~$50M incremental revenue; led ~$400K/yr data curation for next‑gen models
- Consulting (2023–present): Query understanding, prompts, embedding search, fine‑tuning, MLOps/observability; upgrading legacy workflows to agentic systems
- Clients: HubSpot, Zapier, Limitless, and others across assistants, construction, research
- Personal note: Hand injury (2021–2022) → shifted focus to higher‑leverage teaching and advising

---

# Who’s Here (Cohort)

- ~30% founders/CTOs • ~20% senior engineers • ~50% SWE/DS/PM/SE/consultants
- Companies represented: OpenAI, Anthropic, Google, Microsoft, Amazon; Salesforce, Adobe, Cisco, Shopify; Accenture, McKinsey, Bain, PwC; EA, and many startups
- Ask: share constraints and examples; we’ll tailor office hours
- Success = measurable improvements on your actual problems

---

# Key Insights & Course Outcomes

This course will give you the foundations and practical skills to build, evaluate, and operate retrieval-augmented generation (RAG) systems. Here’s what to keep in mind and what you’ll learn:
### Keep these in mind

- Good retrieval will often beat clever prompting.
- Similarity is subjective, train for your specific goals.
- Feedback is fuel, design your UX to capture useful signals.
- Success is two-level, P(right tool) × P(success | tool).
- Specialized indices often outperform one-size-fits-all solutions (though this is shifting as contexts/tools evolve).
- Segmenting queries and users to prioritize work and build a roadmap.
- Production matters, cache, monitor, and degrade gracefully.

---

# What’s Changed Since v1

- Since Claude 3.5, tools/agents are much more reliable; planning loops keep improving
- Code assistants (e.g., Claude Code) excel at code RAG flows: grep + edit with validation
- Prompt caching widespread; longer contexts change cost/latency tradeoffs
- Better PDF/diagram extraction; richer citations in UIs (bounding boxes)
- Shift from one‑off evals to continuous testing and monitoring over time
- Always a tradeoff: performance × latency × cost; be mindful of pricing impacts
- “Context engineering” is emerging; 2026 update of this course will focus more here

---

# Syllabus (Sessions 0–3)

- Session 0: Product mindset; RAG as a recommender; improvement flywheel
- Session 1: Synthetic data and retrieval evals; precision/recall; baselines
- Session 2: From evals to training data; reranking; embedding fine-tuning
- Session 3: UX that collects data; streaming; chain of thought; validation
  - Pacing note: Week 3 is intentionally lighter—use it to catch up and get ahead
  - Focus on UX patterns; not the most critical week content‑wise

## Main takeaway
- fast retrieval evals (precision/recall on key chunks) 
- rerank/fine‑tune to get a 10-20% improvement
- deploy and collect real data via UX

---

# Syllabus (Sessions 4–6)

- Session 4: Topic modeling; query segmentation; prioritization frameworks
- Session 5: Specialized indices; multimodal search (docs, images, tables, SQL)
- Session 6: Query routing; tools-as-APIs; single vs multi-agent; measurement
  - Week 6 is lighter; focus on routing and preview the context‑engineering direction

## Main takeaway
- Figure out whats important to you and your users
- Build specialized indices for those usecases
- Make sure the Agent is able to use the specialized indices

---

## Format & Office Hours

- Inverted classroom: ~6 hours pre‑recorded lectures + tutorial videos
- Tutorials/Notebooks: Jupyter exercises to tackle between sessions
- Slack: post questions in the cohort channel for async help
- Office hours: 
  - bring your problems
  - treat it like a tech‑lead review
  - cameras on is really appreciated! helps me a lot.
- Guest lectures: 1-2 times a week, practitioners actively building in the space
- Scheduling: occasional reschedules (e.g., OpenAI Dev Day); advance notice
- Credits/support: contact Marian — support at jxnl.co (support@jxnl.co)
---

## Resources & Contributions

- Study notes (work in progress): https://567-labs.github.io/systematically-improving-rag/
- Talks/“greatest hits”: https://567-labs.github.io/systematically-improving-rag/talks/
  - Recommendations
    - Skylar’s RAG anti‑patterns Talk
    - Anton's Text Chunking Strategies Talk
    - Exa's Why Google Search Sucks for AI Talk
    - Colin's Agentic RAG Talk
- Contribute via PRs/issues; add examples; suggest edits

---

## Q&A

Questions, goals, and constraints.