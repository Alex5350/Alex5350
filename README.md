<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/header-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./assets/header-light.svg">
  <img alt="Alex Torres - Senior Software Engineer working across .NET, full-stack systems, and applied AI" src="./assets/header-light.svg" width="100%">
</picture>

<br>

I’m Alex, a U.S. Marine Corps veteran and software engineer focused on .NET, full-stack
development, and applied AI.

Most of my professional work isn’t public, so the projects here are independent examples
based on the kinds of systems and engineering problems I’ve worked on throughout my career.
They don’t contain client code, data, or identifying details, but they do reflect how I
approach architecture, accessibility, edge cases, AI integration, testing, and documentation.

**Résumé:** [View PDF](https://github.com/Alex5350/Alex5350/blob/main/assets/Alexander-Torres-Resume.pdf) · [Download a copy](https://github.com/Alex5350/Alex5350/raw/main/assets/Alexander-Torres-Resume.pdf)

## Selected work

### [Mintmark](https://github.com/Alex5350/mintmark)

<a href="https://github.com/Alex5350/mintmark">
  <img src="https://raw.githubusercontent.com/Alex5350/mintmark/main/docs/assets/architecture.svg" alt="Mintmark architecture showing the Next.js web and Expo mobile clients over one ASP.NET Core API, PostgreSQL 18 with pgvector, S3-compatible storage, spot providers with failover, and the vision identification pipeline" width="100%">
</a>

A precious-metals collection tracker where collectors catalog gold and silver holdings,
photograph a coin's obverse and reverse for grounded AI identification with top-five
candidates they confirm, and watch melt and rules-based collectible valuations against live
spot prices - every number carrying its provenance. Built on ASP.NET Core minimal APIs with
.NET 10, EF Core and PostgreSQL 18 (pgvector + pg_trgm), S3-compatible image storage, Quartz
jobs, a Next.js 16 web client, and an Expo SDK 57 mobile client whose guided two-shot capture
is the reason the product exists on a phone.

**Engineering focus:** Identification is retrieval-grounded - the vision contract demands
per-field confidence and visual evidence (null beats guessing), hybrid search proposes
candidates, and the user's confirmation lands in an append-only audit run. Catalog
specifications carry source URLs or stay null rather than invented; a labeled deterministic
offline evaluator exercises the entire pipeline without API keys; and the committed OpenAPI
document is a CI-diff-gated artifact that generates the TypeScript client both frontends
consume. The 118-test backend includes golden valuations proving low-mintage and common-date
coins diverge from transparent premium factors alone.

---

### [DocSage](https://github.com/Alex5350/docsage)

<a href="https://github.com/Alex5350/docsage">
  <img src="https://raw.githubusercontent.com/Alex5350/docsage/main/docs/assets/architecture.svg" alt="DocSage architecture showing the Next.js interface, FastAPI and ASP.NET Core parity APIs, PostgreSQL with pgvector, and Gemini and OpenAI providers" width="100%">
</a>

A full-stack **Agentic RAG** platform that turns Word, Excel, PDF, image, and text uploads
into verifiable answers with citations back to the source page. Rather than simply chunking
and embedding raw content, its agentic ingestion pipeline generates summaries, keywords,
likely questions, table context, and image captions before indexing-bridging the vocabulary
gap between how documents are written and how people ask questions. Personal, agency, and
admin scopes keep access deliberate, while SME approval gates what becomes shared knowledge.

**Engineering focus:** Provider-qualified vector spaces safely support Gemini’s native
multimodal embeddings and OpenAI’s text embeddings in one pgvector store. Query-time
retrieval remains a single indexed vector search, while FastAPI and ASP.NET Core
implementations share the same API contract, authentication sessions, and deterministic
offline embedding algorithm-allowing ingestion, approvals, retrieval, citations, and chat
to run without API keys and be parity-tested across runtimes.

---

### [FlowInk](https://github.com/Alex5350/flowink)

<a href="https://github.com/Alex5350/flowink">
  <img src="https://raw.githubusercontent.com/Alex5350/flowink/main/docs/diagrams/architecture.svg" alt="FlowInk architecture showing how a JSON specification passes through the CLI and renderer into a committed animated README diagram" width="100%">
</a>

A cross-framework library and CLI that turns JSON specifications into self-contained,
animated SVG architecture diagrams. Its TypeScript and C# renderers are held to byte parity,
with integrations for React, Angular, and Blazor plus a CLI for generating diagrams that can
be committed directly to READMEs.

**Engineering focus:** CSS-only animation makes SMIL structurally impossible, keeping
diagrams reliable inside GitHub’s `<img>` rendering context. Output contains no scripts or
external references, escapes injected content, supports reduced-motion preferences, and is
produced by zero-dependency rendering cores.

---

### [VideoScheduler](https://github.com/Alex5350/videoscheduler)

<a href="https://github.com/Alex5350/videoscheduler">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Alex5350/videoscheduler/main/docs/screenshots/shot-schedule-dark.png">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Alex5350/videoscheduler/main/docs/screenshots/shot-schedule.png">
    <img src="https://raw.githubusercontent.com/Alex5350/videoscheduler/main/docs/screenshots/shot-schedule.png" alt="VideoScheduler day schedule showing equipment availability and reservations" width="100%">
  </picture>
</a>

A full-stack video-equipment scheduling system built with Next.js 16, PostgreSQL, Drizzle
ORM, Tailwind CSS v4, and shadcn/ui. It coordinates studios, portable kits, and rover
stations across regional offices with conflict-free one-off and recurring reservations,
DST-correct time handling, Microsoft Teams integration, and calendar exports.

**Engineering focus:** Pure domain rules handle conflicts, recurrence, and time zones, while
PostgreSQL row locks close last-slot race conditions. Authentication and Teams use swappable
boundaries for Entra ID and Microsoft Graph. Validation includes 35 domain tests and 20
real-HTTP integration suites.

---

### [AssetLite](https://github.com/Alex5350/assetlite)

<a href="https://github.com/Alex5350/assetlite">
  <img src="https://raw.githubusercontent.com/Alex5350/assetlite/main/docs/diagrams/app-flow.svg" alt="AssetLite architecture showing Aspire orchestration across the Angular application, ASP.NET Core API, Clean Architecture layers, SQLite, and telemetry" width="100%">
</a>

A full-stack IT asset and inventory management system built with .NET 10, Angular 21,
Tailwind CSS v4, and .NET Aspire. It handles asset lifecycle states, hierarchical offices,
barcode and QR labels, search, and Excel/PDF exports through a Clean Architecture API and
signals-first SPA.

**Engineering focus:** Typed domain errors flow from lifecycle rules through RFC 9457
responses into the UI, while Aspire orchestrates the API, SPA, telemetry, and health checks.
The suite includes 339 backend and 62 Angular tests covering domain rules, API contracts,
exports, and frontend behavior.

---

### [LeaveLite MCP](https://github.com/Alex5350/leavelite-mcp)

<a href="https://github.com/Alex5350/leavelite-mcp">
  <img src="https://raw.githubusercontent.com/Alex5350/leavelite-mcp/main/docs/diagrams/architecture-flow.svg" alt="LeaveLite MCP architecture showing how a tool call moves from an MCP client through the application and domain" width="100%">
</a>

A .NET 10 Model Context Protocol server for leave and PTO management, built with the official
C# SDK and Clean Architecture. It exposes accrual balances, leave requests, approvals, team
coverage, policy resources, and a review prompt to AI clients while keeping authorization and
business rules in the domain rather than the model.

**Engineering focus:** The 253-test suite includes 27 protocol-level integration tests using
the official MCP client against the real transport. Stable domain error codes, deterministic
time handling, and staffing constraints make tool behavior predictable for AI clients.

---

### [VA OIG FWA Risk Triage & Reporting Portal](https://github.com/Alex5350/USWDS-VA-Demo)

<a href="https://github.com/Alex5350/USWDS-VA-Demo">
  <img src="https://raw.githubusercontent.com/Alex5350/USWDS-VA-Demo/main/docs/diagrams/request-flow.svg" alt="VA OIG FWA Risk Triage and Reporting Portal architecture showing the USWDS client, ASP.NET Core API, SQL Server reporting, offline fallback, and read-only AI assistant" width="100%">
</a>

A synthetic-data public-sector portal for prioritizing claims, providers, complaints, and
case work for human review without treating risk indicators as fraud determinations. It
combines a .NET 10 ASP.NET Core API, SQL Server reporting with EF Core and Dapper, a Section
508/USWDS Next.js interface, and a Gemini case assistant limited to read-only, allowlisted
tools.

**Engineering focus:** Transparent scoring, role-aware workflows, audit events, accessible
reporting, and offline fallback keep the system explainable when services are unavailable.
The AI boundary can summarize synthetic case data but cannot mutate records, execute
arbitrary SQL, or replace analyst judgment.

---

### [LedgerLite Web](https://github.com/Alex5350/ledgerlite-web)

<a href="https://github.com/Alex5350/ledgerlite-web">
  <img src="https://raw.githubusercontent.com/Alex5350/ledgerlite-web/main/docs/diagrams/request-flow.svg" alt="LedgerLite Web architecture showing Interactive Auto across server and WebAssembly rendering, JWT authentication, the API, domain layer, and persistence" width="100%">
</a>

A full-stack .NET 10 reference application built around a double-entry ledger. I used it to
work through Blazor’s Interactive Auto render mode, authentication across server and
WebAssembly boundaries, a hand-built Tailwind component system, and the less-visible states
that make an interface trustworthy. The combined backend and UI suite currently contains
381 tests.

**What I learned:** render modes change service-lifetime assumptions; design systems become
useful when they encode behavior as well as appearance; and browser testing has a way of
finding integration mistakes that unit tests cannot see.

---

### [LedgerLite API](https://github.com/Alex5350/ledgerlite)

A personal-finance API where the domain has real invariants: journal entries must balance,
closed fiscal periods are immutable, account numbers are unique within a period, and budget
alerts fire once per threshold. It uses .NET 10, C# 14, ASP.NET Core, EF Core, Clean
Architecture, and CQRS without a mediator framework.

**What I learned:** architecture earns its keep when it makes business rules easy to locate,
explain, and test. The 262-test suite focuses on those rules and the HTTP/authentication
boundary rather than chasing coverage for its own sake.

## Ideas I keep returning to

- Put important business rules where another engineer can find and defend them.
- Treat loading, empty, error, authorization, and recovery states as part of the feature.
- Prefer explicit dependencies and observable failure modes over framework magic.
- Use tests to protect decisions and invariants-not merely to increase a percentage.
- Add AI where it reduces friction without obscuring sources, permissions, or responsibility.

## Working with

**Languages:** C#, TypeScript, SQL  
**Application platforms:** .NET, ASP.NET Core, Blazor, React, Next.js  
**Data and delivery:** EF Core, Dapper, SQL Server, SQLite, Docker, GitHub Actions  
**Applied AI:** streaming interfaces, tool-backed assistants, and structured validation

## Elsewhere

I keep a more traditional account of my background on
[LinkedIn](https://www.linkedin.com/in/alexander-t-3075203b/).
