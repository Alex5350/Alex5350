<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/header-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./assets/header-light.svg">
  <img alt="Alex Torres, Senior Software Engineer working across .NET, full-stack systems, and applied AI" src="./assets/header-light.svg" width="100%">
</picture>

<br>

I'm Alex, a U.S. Marine Corps veteran and senior software engineer specializing in .NET,
full-stack development, and applied AI. I build reliable, accessible web applications with
Angular, React.js, Next.js, and Blazor, bringing together clean architecture, intuitive user
experiences, and practical AI integration. My focus is turning complex requirements into
maintainable software that solves real business problems.

Most of my professional work isn't public, so the projects here are independent examples
based on the kinds of systems and engineering problems I've worked on throughout my career.
They don't contain client code, data, or identifying details, but they do reflect how I
approach architecture, accessibility, edge cases, AI integration, testing, and documentation.

**Résumé:** [View PDF](https://github.com/Alex5350/Alex5350/blob/main/assets/Alexander-Torres-Resume.pdf) · [Download a copy](https://github.com/Alex5350/Alex5350/raw/main/assets/Alexander-Torres-Resume.pdf)

## Certifications

The credentials behind the work. Every entry links to its verification page at the issuer:

| Certification | Issuer |
| --- | --- |
| [Claude Certified Architect - Foundations](https://www.credly.com/badges/7d9934b2-72ac-46f6-8566-3183fa815f68) | Anthropic |
| [Azure AI Cloud Developer Associate](https://learn.microsoft.com/en-us/users/alextorres/credentials/c0bff2873ba23cda) | Microsoft |
| [Azure AI Apps and Agents Developer Associate](https://learn.microsoft.com/en-us/users/alextorres/credentials/5041608fbe16de66) | Microsoft |
| [AWS Certified Developer - Associate](https://www.credly.com/badges/8df8ecc7-f87f-48d3-917e-878088dc6e36/public_url) | Amazon Web Services |
| [Accelerate app development by using GitHub Copilot](https://learn.microsoft.com/en-us/users/alextorres/credentials/1f0e41c2afd67c4b) | Microsoft Applied Skills |
| [Build a natural language processing solution with Azure AI Language](https://learn.microsoft.com/en-us/users/alextorres/credentials/7f6727487852b46a) | Microsoft Applied Skills |

> **Reading this page.** Every project below leads with what it does for its users: the
> problem, the pictures, and one business highlight. Not an engineer? Skim the screenshots
> and the bold lines; that's the whole story. Engineer? Open the **Engineering view** in any
> entry, or jump straight to each repository's `TECHNICAL.md`, where the architecture, the
> decision records, and the reasoning that maps every technical choice back to the business
> problem all live.

## Selected work

| Project | What it is | Stack highlights |
|---|---|---|
| [Palisade](https://github.com/Alex5350/palisade) | Installation security fused into one operating picture: incidents that fire immediately, responses the system drives | .NET 10, Redis Streams, SQL Server, Avalonia |
| [Corridor](https://github.com/Alex5350/corridor) | An ADFS-to-Okta identity migration: three apps cross with no downtime | .NET 10, OIDC/SAML/SCIM/XACML, CoreWCF, React |
| [Atelier](https://github.com/Alex5350/atelier) | A creative AI studio that runs with zero API keys: chat with files, review-gated image passes, video, and honest cost accounting | Next.js, Bun, AI SDK, PostgreSQL + pgvector |
| [Pacific Marines](https://github.com/Alex5350/tabs-pacific-marines) | A WWII Marine faction for Totally Accurate Battle Simulator, injected into the live game from C#: airstrikes, mortar crews, and cover troops actually build | C#, .NET Framework 4.7.2, BepInEx, Harmony, Unity |
| [MediFlow](https://github.com/Alex5350/mediflow) | Medicare enrollment and claims done right: nothing half-paid, nothing lost | .NET 10, SQL Server, Blazor, MCP |
| [Mintmark](https://github.com/Alex5350/mintmark) | A serious collector's tracker for gold and silver, where every number carries its provenance | .NET 10, PostgreSQL + pgvector, Next.js, Expo |
| [DocSage](https://github.com/Alex5350/docsage) | Documents that answer questions, with citations and a review chain of command | FastAPI + ASP.NET Core parity, pgvector, Next.js |
| [FlowInk](https://github.com/Alex5350/flowink) | Architecture diagrams that actually animate in GitHub READMEs, from plain JSON | TypeScript + C#, npm and NuGet packages |
| [VideoScheduler](https://github.com/Alex5350/videoscheduler) | Video-gear booking that cannot double-book, across US time zones | Next.js, PostgreSQL, Drizzle |
| [AssetLite](https://github.com/Alex5350/assetlite) | One live equipment register from headquarters down to every site | .NET 10, Aspire, Angular |
| [LeaveLite MCP](https://github.com/Alex5350/leavelite-mcp) | Let your AI assistant answer leave questions; keep the rules on the server | .NET 10, official MCP SDK |
| [VA OIG FWA Portal](https://github.com/Alex5350/USWDS-VA-Demo) | Prioritizes case review for analysts, without accusing anyone | .NET 10, SQL Server, USWDS, Section 508 |
| [LedgerLite Web](https://github.com/Alex5350/ledgerlite-web) | Double-entry bookkeeping with balance visible as you type | Blazor Interactive Auto, Tailwind |
| [LedgerLite API](https://github.com/Alex5350/ledgerlite) | The books must balance: errors have nowhere to hide | .NET 10, EF Core, CQRS |

---

### [Palisade](https://github.com/Alex5350/palisade)

<a href="https://github.com/Alex5350/palisade">
  <img src="https://raw.githubusercontent.com/Alex5350/palisade/main/docs/screenshots/shot-perimeter-breach.png" alt="Palisade operations dashboard: a dark tactical map of Camp Meridian with zones, gates, and sensors; a pulsing red ring marking a perimeter breach in a restricted zone; the incident panel showing the active breach with its response workflow running" width="100%">
</a>

A security force runs its installation on single-purpose systems: badge readers,
cameras, and fence sensors, each with its own console, none of them talking. The
guard watches three feeds and does the correlation in their head, which fails as
noise (false pages until nobody responds) and as silence (the motion blip that
mattered, missed next to the badge data that explained it). Palisade is the other
path, demonstrated end to end on a synthetic installation: every sensor feed lands
on one event bus, six correlation rules turn raw detections into de-duplicated
incidents with severity and a map position, each incident runs a response checklist
(notify, task a camera, lock a gate, wait for the operator's ack, escalate on
timeout), and the whole picture plus every command lives on one screen with an
append-only audit trail. A desktop console and a typed client SDK consume the same
surfaces, and a scripted synthetic feed makes the system perform on demand.

**Business highlight:** a qualifying detection in a restricted area raises the
incident the instant it happens (a legitimate badge-in in the same zone auto-resolves
it; the rule then re-arms), and resolving an incident actually ends it: workflows
cancel, de-duplication re-arms, and nothing acts on a closed incident, a guarantee
that is specified in the architecture contract, pinned by tests, and re-verifiable
live from the runbook.

<details>
<summary><b>Engineering view</b></summary>

Four .NET 10 services over Redis Streams with consumer groups and per-event SET NX
idempotency (the seen-key scope was the repo's hardest-won defect, caught and pinned
by regression test), SQL Server persistence, and SSE fan-out the dashboard parses by
hand over an authorized fetch. The correlation engine is a pure, deterministic state
machine with boundary-pinned thresholds on all six rules, track join and age-out, and
lazy liveness for the degradation rule; the response side is a workflow engine with
definitions as data (notify, command, cameraTask, awaitAck), per-step timeouts,
escalation that continues the checklist, and resolve-as-broadcast semantics across
services. The web COP is a dependency-free canvas client; the desktop console is
Avalonia written in the WPF idiom (axaml, MVVM, headless-tested view models, win-x64
publish). CI proves it on every push: 281 unit tests, 14 Testcontainers integration
tests, a 17-request newman regression against the booted stack, a console publish
check, gitleaks and CodeQL; eight ADRs and a five-story process log (the stream
swallowed by a dedup key, the incident that resurrected after resolve, the console
crash on timestamp offsets, the docker context trap, the blank-map capture) document
how each guarantee was earned.

Full deep dive: [TECHNICAL.md](https://github.com/Alex5350/palisade/blob/main/TECHNICAL.md)

</details>

---

### [Corridor](https://github.com/Alex5350/corridor)

<a href="https://github.com/Alex5350/corridor">
  <img src="https://raw.githubusercontent.com/Alex5350/corridor/main/docs/screenshots/shot-migration-dashboard.png" alt="Corridor migration dashboard mid-cutover: the three applications shown with one in each trust mode (ADFS, dual trust, Okta) and the audit trail of flips below" width="100%">
</a>

Government programs sit on applications tied to aging on-prem identity systems, and moving
them to modern cloud authentication usually means downtime and risk. Corridor walks three
synthetic federal applications (a permits web portal, a field-inspector SPA, and a SOAP case
service) from an ADFS-style SAML login to Okta-style authentication with no downtime window:
a per-app dual-trust cutover, SCIM provisioning so accounts move with the cutover, a
centralized XACML authorization point, and a Postman, SoapUI, and JMeter regression gate run
between every phase.

**Business highlight:** every application crossed to the new identity provider with zero
downtime, and rollback stayed one flip away the whole time.

<details>
<summary><b>Engineering view</b></summary>

Both identity providers are simulated locally with real protocols: actual OIDC code flow with
mandatory PKCE and rotating refresh tokens, signed SAML 2.0 assertions, SCIM 2.0 provisioning
driven from the migration dashboard itself, and a centralized XACML decision point that the
portal actually enforces, fail closed, at its API boundary. The legacy service keeps its SOAP
contract (CoreWCF) and its raw ADO.NET data layer untouched while its identity header swaps
from SAML to JWT behind a SQL-backed trust-mode state machine; the portal proves dual trust
live by accepting either provider mid-cutover. CI runs the whole proof on every push: 231
unit tests, 31 cross-service integration tests, a self-bootstrapping Playwright suite over
all three login paths and the audited flips, and the committed Postman collection (25
requests) executed by newman against a live stack, with gitleaks and CodeQL alongside; a
VB.NET ops CLI covers the cutover weekend's pocket tooling. The debugging stories behind the
eight real defects the suites caught along the way are written up in the process doc.

Full deep dive: [TECHNICAL.md](https://github.com/Alex5350/corridor/blob/main/TECHNICAL.md)

</details>

---

### [Atelier](https://github.com/Alex5350/atelier)

<a href="https://github.com/Alex5350/atelier">
  <img src="https://raw.githubusercontent.com/Alex5350/atelier/main/docs/screenshots/studio.png" alt="Atelier's studio project view: dark-themed pass cards with generated images and review controls, the prompt composer with model and reference pickers, and a lineage graph connecting approved assets to the passes that used them" width="100%">
</a>

Creative teams evaluating AI usually hit a demo wall: everything works with one
hardcoded model and no cost visibility, or you spend a week wiring keys before
you see anything. Atelier is a full creative studio, streaming chat with file
attachments and retrieval, image generation with inpaint/outpaint/upscale
passes, and video jobs, that runs end to end with zero API keys: three built-in
demo models serve every surface with clearly labeled output, and the moment a
real Anthropic, OpenAI, or Google key appears, the same surfaces switch to
frontier models with per-turn prices read from a registry the operator edits.

**Business highlight:** every model call is priced and gated before it happens:
a daily budget cap refuses calls that would overshoot it (naming the numbers in
the refusal), and every completed call writes a usage event that pins the price
it actually ran at, so historical spend stays truthful even after prices change.

<details>
<summary><b>Engineering view</b></summary>

Zero-key operation is not a mock at the route layer: the demo models are
hand-written implementations of the AI SDK's provider interfaces (streaming
chat, image generation), so pricing, the registry, and the admin page exercise
identical code paths for real and demo providers and cannot drift. Models live
in PostgreSQL as rows with effective-dated, append-only prices; only assets an
operator approves can feed later passes or exports, enforced three layers deep
and ending in a database trigger; file chat runs hybrid retrieval (pgvector
cosine fused with full-text search) with citations back to filename and chunk;
regenerating an image supersedes rather than overwrites, and the lineage graph
draws how every asset was made. Bun with Next.js App Router, Tailwind v4 with
the shadcn base-nova kit, better-auth, Drizzle migrations, and a video
provider port with demo, Sora, and Veo implementations. The API boundary is
hardened like it faces the internet: per-user rate limiting on every
cost-bearing endpoint, security headers with a conservative CSP, typed 400s
for malformed bodies, and bounded provider fetches. CI runs typecheck, lint,
71 unit tests, a 14-spec Playwright suite that builds and boots the production
server before testing it, gitleaks over the full history, and CodeQL. The
suite has earned its keep: it caught attachment turns failing on the AI SDK's
URL validation, a type guard that missed URL instances, a retrieval toggle
stranded by a missing field, and a static-linux ffmpeg build that ships
without drawtext; each is fixed and pinned by a regression test.

Full deep dive: [TECHNICAL.md](https://github.com/Alex5350/atelier/blob/main/TECHNICAL.md)

</details>

---

### [Pacific Marines](https://github.com/Alex5350/tabs-pacific-marines)

<a href="https://github.com/Alex5350/tabs-pacific-marines">
  <img src="https://raw.githubusercontent.com/Alex5350/tabs-pacific-marines/main/docs/screenshots/hero-banner.png" alt="Pacific Marines hero: a C# mod adding a WWII Marine faction to Totally Accurate Battle Simulator, with five units, airstrikes, a mortar team, and buildable sandbag cover beside a live in-game capture" width="100%">
</a>

As a Marine veteran I wanted to field a WWII Marine faction in Totally Accurate
Battle Simulator, and the game's Unit Creator cannot make one: no creator option
calls an airstrike, mans a mortar with a real three-person crew, or builds
physical cover in the middle of a battle. Pacific Marines adds all five units as
a C# plugin: it registers the faction into the running game's content database,
patches four AI entry points so the mortar crew holds its emplacement, and runs
the support abilities as battle-scoped effects that clean up on reset. No game
file changes, and vanilla stays one normal Steam launch away.

**Business highlight:** every claim is verified in the real game, not against
mocks: a separate test plugin places units through the game's own APIs, starts
battles through the real UI, sends actual G-key events to the game process, and
retains the PASS/FAIL transcripts, covering damage, cooldowns, sandbag cover
that stops real bullets, death semantics, and reset cleanup.

<details>
<summary><b>Engineering view</b></summary>

A BepInEx 5 plugin targeting .NET Framework 4.7.2 with C# 7.3 pinned to match
the game's Mono runtime, developed and live-tested on Apple Silicon through
Rosetta. Content registration extends exactly two in-memory tables under a
namespaced ID range with a collision guard that refuses to overwrite; blueprints
are cloned, never aliased, and tests assert the stock blueprint is untouched.
Unit behavior comes from Harmony prefixes on the game's movement and attack
entry points (the naive speed-multiplier approach failed live testing; the
failing transcript is retained alongside the fix). Effects own their lifetime
under a battle-scoped root: simulation-time timers that respect pause and slow
motion, occlusion-aware blasts (roughly 80 percent damage reduction behind
sandbags, measured), a 32-shelter cap, and full cleanup on reset and scene
unload. The harness compiles a Swift key-sender so native keyboard events
exercise the production input route, and pairs every blocked measurement with an
open-lane control. Nine defects were reproduced, fixed, and pinned by regression
evidence; CI runs hygiene, documentation-link, diagram-spec, and secret scans.

Full deep dive: [TECHNICAL.md](https://github.com/Alex5350/tabs-pacific-marines/blob/main/TECHNICAL.md)

</details>

---

### [MediFlow](https://github.com/Alex5350/mediflow)

<a href="https://github.com/Alex5350/mediflow">
  <img src="https://raw.githubusercontent.com/Alex5350/mediflow/main/docs/screenshots/dashboard.png" alt="MediFlow operations dashboard showing the enrollment and claims pipeline at a glance" width="100%">
</a>

Medicare operations teams juggle enrollment windows, claim rules, and payment accuracy across
staff, members, and providers. MediFlow checks enrollment eligibility before anything is
saved, runs submitted claims through the real rules (timeliness, coverage, duplicates,
deductibles), and prices each one completely or not at all. Staff get an operations console;
AI assistants get a read-only view of the same facts.

**Business highlight:** a claim is priced and committed in one atomic step, so nothing is
ever half-paid, double-paid, or silently lost.

<details>
<summary><b>Engineering view</b></summary>

Concurrency you can inspect: claims move through a durable outbox whose leasing is an atomic
CTE update under READPAST/UPDLOCK, and the commit procedure guards on the lease, with
integration tests proving two workers never claim the same claim and stale-lease commits are
rejected. The four test tiers (65 unit, 15 Testcontainers integration, 10 bUnit, 8
self-bootstrapping Playwright E2E) caught a real defect where DI-registered rules resolved an
empty pipeline and every claim silently paid; the bug, fix and lesson are committed as ADR
0002. Warnings-as-errors includes NuGet vulnerability data; the pipeline adds CodeQL, Snyk,
gitleaks and SPDX SBOM.

Full deep dive: [TECHNICAL.md](https://github.com/Alex5350/mediflow/blob/main/TECHNICAL.md)

</details>

---

### [Mintmark](https://github.com/Alex5350/mintmark)

<a href="https://github.com/Alex5350/mintmark">
  <img src="https://raw.githubusercontent.com/Alex5350/mintmark/main/docs/assets/dashboard.png" alt="Mintmark dashboard showing a precious metals collection valued against live spot prices" width="100%">
</a>

Serious collectors track gold and silver across scattered sources, and stale prices or
guessed valuations make insurance records and sale decisions unreliable. Mintmark catalogs
holdings, identifies coins from photos (offering grounded candidates the collector confirms,
never auto-accepted), and values the collection against live, source-attributed spot prices,
on the web and on a phone.

**Business highlight:** every number carries its provenance: the dashboard's gain traces to
the same live price the ticker shows, and an identification without catalog evidence says so.

<details>
<summary><b>Engineering view</b></summary>

Identification is retrieval-grounded: the vision contract demands per-field confidence and
visual evidence (null beats guessing), hybrid search proposes candidates, and the user's
confirmation lands in an append-only audit run. Catalog specifications carry source URLs or
stay null rather than invented; a labeled deterministic offline evaluator exercises the
entire pipeline without API keys; and the committed OpenAPI document is a CI-diff-gated
artifact that generates the TypeScript client both frontends consume. The 118-test backend
includes golden valuations proving low-mintage and common-date coins diverge from transparent
premium factors alone.

Full deep dive: [TECHNICAL.md](https://github.com/Alex5350/mintmark/blob/main/TECHNICAL.md)

</details>

---

### [DocSage](https://github.com/Alex5350/docsage)

<a href="https://github.com/Alex5350/docsage">
  <img src="https://raw.githubusercontent.com/Alex5350/docsage/main/docs/assets/screenshots/03-chat-answer-dark.png" alt="DocSage answering a policy question with citations back to the source document" width="100%">
</a>

Agencies and enterprises sit on policy documents nobody can query, and people ask questions
in different words than the documents use. DocSage ingests Word, Excel, PDF, image and text
files, enriches them once so they match how people actually ask, and answers questions with
citations back to the source page. What becomes shared knowledge is decided by a review chain
of command, not by an upload.

**Business highlight:** nothing becomes agency-wide until a subject-matter expert approves
it (and uploaders can't approve their own), and every answer cites the page it came from.

<details>
<summary><b>Engineering view</b></summary>

Agentic ingestion pays model cost once per document instead of per question. Provider-
qualified vector spaces support Gemini's native multimodal embeddings and OpenAI's text
embeddings in one pgvector store without silent degradation. FastAPI and ASP.NET Core
implementations share one API contract, one authentication model, and a deterministic offline
embedding algorithm, so the entire product (ingestion, approvals, retrieval, citations, chat)
runs without API keys and is parity-tested across runtimes by one E2E suite.

Full deep dive: [TECHNICAL.md](https://github.com/Alex5350/docsage/blob/main/TECHNICAL.md)

</details>

---

### [FlowInk](https://github.com/Alex5350/flowink)

<a href="https://github.com/Alex5350/flowink">
  <img src="https://raw.githubusercontent.com/Alex5350/flowink/main/docs/gallery/ci-pipeline.svg" alt="FlowInk gallery example: an animated CI pipeline diagram with gates, failure paths and a riding packet" width="100%">
</a>

Engineering documentation goes stale and unread, and hand-animated diagrams break the moment
they meet GitHub's rendering rules. FlowInk turns a plain JSON description of nodes and edges
into self-contained animated SVG diagrams that render reliably inside READMEs, respect
reduced-motion preferences, and can be regenerated whenever the architecture changes.

**Business highlight:** architecture diagrams that actually animate where engineers read
them, from data anyone on the team can edit.

<details>
<summary><b>Engineering view</b></summary>

CSS-only animation makes SMIL structurally impossible, keeping diagrams reliable inside
GitHub's `<img>` rendering context. Output contains no scripts or external references,
escapes injected content, and is produced by zero-dependency rendering cores in TypeScript
and C# that are held to byte parity by a golden-fixture test, so the npm and NuGet worlds
cannot drift. Integrations ship for React, Angular, and Blazor, plus the CLI that renders
this very diagram.

Full deep dive: [TECHNICAL.md](https://github.com/Alex5350/flowink/blob/main/TECHNICAL.md)

</details>

---

### [VideoScheduler](https://github.com/Alex5350/videoscheduler)

<a href="https://github.com/Alex5350/videoscheduler">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Alex5350/videoscheduler/main/docs/screenshots/shot-schedule-dark.png">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Alex5350/videoscheduler/main/docs/screenshots/shot-schedule.png">
    <img src="https://raw.githubusercontent.com/Alex5350/videoscheduler/main/docs/screenshots/shot-schedule.png" alt="VideoScheduler day schedule showing equipment availability and reservations" width="100%">
  </picture>
</a>

Video teams spread across a headquarters and regional offices share studios, kits, and rover
stations, and spreadsheet scheduling double-books rooms or lands bookings an hour off.
VideoScheduler gives every office its own local calendar over one shared equipment pool and
makes both failures impossible by design.

**Business highlight:** reservations that cannot conflict, correct across four US time zones
and both clock-change days.

<details>
<summary><b>Engineering view</b></summary>

Pure domain rules handle conflicts, recurrence, and time zones, while PostgreSQL row locks
close last-slot race conditions. Time conversion lives in one `Intl`-based module used by
every screen and rule, pinned by DST transition-day test vectors. Authentication and Teams
sit behind swappable boundaries for Entra ID and Microsoft Graph. Validation includes 35
domain tests and 20 real-HTTP integration suites.

Full deep dive: [TECHNICAL.md](https://github.com/Alex5350/videoscheduler/blob/main/TECHNICAL.md)

</details>

---

### [AssetLite](https://github.com/Alex5350/assetlite)

<a href="https://github.com/Alex5350/assetlite">
  <img src="https://raw.githubusercontent.com/Alex5350/assetlite/main/docs/screenshots/shot-dashboard.png" alt="AssetLite dashboard showing the equipment register and asset lifecycle at a glance" width="100%">
</a>

Growing companies lose track of who holds which laptop, monitor, or tablet, and audits turn
into spreadsheet archaeology. AssetLite keeps one live equipment register across an office
hierarchy from headquarters to regions to sites, follows gear through its whole lifecycle
with corrections recorded rather than erased, and prints scannable barcode and QR labels.

**Business highlight:** one registry from HQ to every site, with Excel and PDF exports an
auditor can actually use.

<details>
<summary><b>Engineering view</b></summary>

Typed domain errors flow from lifecycle rules through RFC 9457 responses into the UI, while
.NET Aspire orchestrates the API, Angular SPA, telemetry, and health checks so the whole
system evaluates in one command. The suite includes 339 backend and 62 Angular tests covering
domain rules, API contracts, exports, and frontend behavior.

Full deep dive: [TECHNICAL.md](https://github.com/Alex5350/assetlite/blob/main/TECHNICAL.md)

</details>

---

### [LeaveLite MCP](https://github.com/Alex5350/leavelite-mcp)

<a href="https://github.com/Alex5350/leavelite-mcp">
  <img src="https://raw.githubusercontent.com/Alex5350/leavelite-mcp/main/docs/diagrams/conversation.svg" alt="A manager chatting with an AI assistant that answers who is off next Friday and books leave through tool calls with approval routing" width="100%">
</a>

Leave balances and policies live in HR portals nobody checks, so managers plan staffing blind
and booking leave means re-keying rules the system already knows. LeaveLite gives an AI
assistant a safe way to answer leave questions and book time off, while the tenure gates,
carry-over caps, holiday awareness, approvals, and minimum-staffing rules stay on the server
where the model can't misremember them.

**Business highlight:** "who's off next Friday?" becomes one question, and every booking
still routes through real approval authority.

<details>
<summary><b>Engineering view</b></summary>

A .NET 10 Model Context Protocol server built with the official C# SDK and Clean
Architecture. The 253-test suite includes 27 protocol-level integration tests using the
official MCP client against the real transport. Stable domain error codes, deterministic
time handling, and staffing constraints make tool behavior predictable for AI clients.

Full deep dive: [TECHNICAL.md](https://github.com/Alex5350/leavelite-mcp/blob/main/TECHNICAL.md)

</details>

---

### [VA OIG FWA Risk Triage & Reporting Portal](https://github.com/Alex5350/USWDS-VA-Demo)

<a href="https://github.com/Alex5350/USWDS-VA-Demo">
  <img src="https://raw.githubusercontent.com/Alex5350/USWDS-VA-Demo/main/docs/screenshots/shot-dashboard.png" alt="The VA OIG portal dashboard showing risk triage queues and reporting for analyst review" width="100%">
</a>

OIG analysts face far more Community Care claims, providers, and complaints than they can
review equally, and the risk cuts both ways: missed improper payments on one side, unfair
accusation on the other. This synthetic-data portal surfaces review candidates through
transparent business rules and SQL-backed reporting, accessible by law and by design.

**Business highlight:** it prioritizes human review without ever treating a risk indicator
as a fraud determination.

<details>
<summary><b>Engineering view</b></summary>

A .NET 10 ASP.NET Core API over SQL Server reporting with EF Core and Dapper, a Section
508/USWDS Next.js interface, and an offline fallback so the demo works anywhere. The AI
boundary can summarize case data but cannot mutate records, execute arbitrary SQL, or replace
analyst judgment: the blast radius of a bad generation is a wrong summary that still cites
its case data.

Full deep dive: [TECHNICAL.md](https://github.com/Alex5350/USWDS-VA-Demo/blob/main/TECHNICAL.md)

</details>

---

### [LedgerLite Web](https://github.com/Alex5350/ledgerlite-web)

<a href="https://github.com/Alex5350/ledgerlite-web">
  <img src="https://raw.githubusercontent.com/Alex5350/ledgerlite-web/main/docs/screenshots/shot-overview.png" alt="LedgerLite Web overview showing period totals, balance status, and budgets at risk" width="100%">
</a>

Bookkeeping interfaces usually make it easy to type something unbalanced and hard to notice.
LedgerLite Web is the face of double-entry personal bookkeeping: the journal editor shows
running debit and credit totals while you type, an entry that doesn't balance simply cannot
be posted, and closed periods stay closed.

**Business highlight:** balance is visible as you type; the server re-checks everything, so
the interface can't bypass the rules.

<details>
<summary><b>Engineering view</b></summary>

A .NET 10 Blazor reference application built around Interactive Auto render modes,
authentication across server and WebAssembly boundaries, per-circuit HTTP handler scoping,
and a hand-built Tailwind component system. Render modes change service-lifetime assumptions;
design systems become useful when they encode behavior as well as appearance; and browser
testing finds integration mistakes unit tests cannot see. The combined backend and UI suite
contains 381 tests.

Full deep dive: [TECHNICAL.md](https://github.com/Alex5350/ledgerlite-web/blob/main/TECHNICAL.md)

</details>

---

### [LedgerLite API](https://github.com/Alex5350/ledgerlite)

<a href="https://github.com/Alex5350/ledgerlite">
  <img src="https://raw.githubusercontent.com/Alex5350/ledgerlite/main/docs/diagrams/double-entry.svg" alt="The life of one journal entry: a transaction becomes a debit and a credit, the balancing rule checks them, balanced entries post to the ledger, and the trial balance nets to zero" width="100%">
</a>

Money apps that track only one side of a movement drift silently from reality. This
personal-finance API implements double-entry accounting, the centuries-old answer: every
movement is recorded as both a debit and a credit that must agree, so a mistake breaks the
balance instead of hiding in it.

**Business highlight:** if it doesn't balance, it doesn't post; and closed fiscal periods
stay immutable.

<details>
<summary><b>Engineering view</b></summary>

The domain carries real invariants: journal entries must balance, closed fiscal periods are
immutable, account numbers are unique within a period, and budget alerts fire once per
threshold. .NET 10, C# 14, ASP.NET Core, EF Core, Clean Architecture, and CQRS without a
mediator framework. Architecture earns its keep when it makes business rules easy to locate,
explain, and test; the 262-test suite focuses on those rules and the HTTP boundary rather
than chasing coverage for its own sake.

Full deep dive: [TECHNICAL.md](https://github.com/Alex5350/ledgerlite/blob/main/TECHNICAL.md)

</details>

## Ideas I keep returning to

- Put important business rules where another engineer can find and defend them.
- Treat loading, empty, error, authorization, and recovery states as part of the feature.
- Prefer explicit dependencies and observable failure modes over framework magic.
- Use tests to protect decisions and invariants, not merely to increase a percentage.
- Add AI where it reduces friction without obscuring sources, permissions, or responsibility.

## Working with

**Languages:** C#, TypeScript, SQL
**Application platforms:** .NET, ASP.NET Core, Blazor, React, Next.js, Angular, Expo,
Unity game modding (BepInEx)
**Data and delivery:** EF Core, Dapper, SQL Server, PostgreSQL (pgvector), SQLite, Docker,
.NET Aspire, GitHub Actions
**Applied AI:** streaming interfaces, tool-backed assistants (MCP), retrieval-grounded
generation, structured validation

## Elsewhere

I keep a more traditional account of my background on
[LinkedIn](https://www.linkedin.com/in/alexander-t-3075203b/).
