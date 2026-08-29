# Luke Pledger

Maths grad · Technology Developer at Barclays · agent infrastructure on the side.

MMath in Mathematics and Physics, First Class, University of York (2025). One of two London-based tech graduates selected in Barclays' 2025 cohort. Currently engineering a market-risk platform after 8 months in Architecture Governance, where audit-trail and traceability work shaped the security-first discipline visible in my personal projects.

I build production AI systems solo, and I build them by running fleets of agents — that method is its own skill and it is the one I would bring to a team.

### Modyx — AI back-office for UK trades

Live product, ~1,047 commits solo. Multi-tenant PostgreSQL with row-level security, a PSTN voice agent answering inbound calls (Vapi), Stripe usage-metered billing, GDPR Article 17 cascading deletion, PII masking, iOS + web + FastAPI.

The part I would point at first: an **eval harness** — scorer registry, judge council, and a score floor that gates releases. The model assigns BS 7671 observation codes to electrical faults. I am not an electrician and cannot verify those by eye, so correctness had to be measured rather than assumed.

### Pherix — contain the blast radius of your agent

Open source · MIT · [PyPI](https://pypi.org/project/pherix/) · zero dependencies · 213 commits · 891 tests

A Python library (+ TypeScript SDK) giving database-style guarantees — atomicity, isolation, capability enforcement, durability — over the *external side-effects* of an agent's tool calls. Reversible calls roll back against your backend's own state; irreversible ones stage and wait for a human yes; every side-effecting call becomes an entry in one append-only journal.

It does not run your agent or call an LLM — it sits underneath the tool-call layer of the loop you already have. Not observability (which watches) and not durable execution (which replays your code): this transacts your resources. → [pherix.dev](https://pherix.dev)

### How I build

Solo throughput comes from orchestration, not typing. Modyx was built across **49 parallel git worktrees**, each driven by an agent under a hand-written orchestrator/worker protocol, alongside scheduled autonomous agents that pick up work unattended, gate on a known test baseline, and open rolling draft PRs rather than touching main.

Everything those agents need is markdown committed to the repo. The harness depreciates; the prompt and skill library appreciates, so the effort goes into the `.md`.

### Also built

- **Boph** — deterministic tutoring engine. Exam spec atomised into version-controlled YAML with a prerequisite graph, and a per-student model (readiness as stage × freshness, spaced-repetition ladder, misconception tracking) that self-tests offline with no API key and no network.
- **Commis** — autonomy-first meal-planning iOS app. A P0–P4 priority engine surfacing the highest-priority decision on load, with a two-phase commit and audit pipeline.

### Stack

Python · TypeScript · SQL · C++ · Swift · FastAPI · PostgreSQL · Next.js · SwiftUI · Anthropic Claude · MCP · Vapi · Stripe · Railway · Cloud Run · CUDA / MPI / OpenMP

### Contact

[lukepledger2912@icloud.com](mailto:lukepledger2912@icloud.com) · LinkedIn · London, UK
