<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/header-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./assets/header-light.svg">
  <img alt="Alex Torres - Senior Software Engineer working across .NET, full-stack systems, and applied AI" src="./assets/header-light.svg" width="100%">
</picture>

I’m Alex, a software engineer in Texas. I use portfolio projects to study the parts of product
engineering that are easy to flatten into buzzwords: domain boundaries, failure modes,
accessible interfaces, and the tradeoffs behind AI-assisted workflows.

I tend to learn by building a complete slice, testing it hard, and writing down why it ended
up that way. These repositories are less a catalog of technologies than a record of that
process.

## Selected work

### [LedgerLite Web](https://github.com/Alex5350/ledgerlite-web)

<a href="https://github.com/Alex5350/ledgerlite-web">
  <img src="https://raw.githubusercontent.com/Alex5350/ledgerlite-web/main/docs/screenshots/overview.png" alt="LedgerLite Web overview dashboard" width="100%">
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

### [LedgerLite](https://github.com/Alex5350/ledgerlite)

A personal-finance API where the domain has real invariants: journal entries must balance,
closed fiscal periods are immutable, account numbers are unique within a period, and budget
alerts fire once per threshold. It uses .NET 10, C# 14, ASP.NET Core, EF Core, Clean
Architecture, and CQRS without a mediator framework.

**What I learned:** architecture earns its keep when it makes business rules easy to locate,
explain, and test. The 262-test suite focuses on those rules and the HTTP/authentication
boundary rather than chasing coverage for its own sake.

---

### [VA OIG FWA Risk Triage Demo](https://github.com/Alex5350/USWDS-VA-Demo)

A synthetic-data public-sector demo that combines a .NET API, SQL reporting, a
USWDS-oriented React/Next.js interface, and an AI-assisted case workflow. The application
keeps risk scoring explainable and gives the assistant read-only, tool-backed access to case
insights rather than treating generated text as authority.

**What I learned:** accessibility, auditability, and explicit system boundaries are product
features. Applied AI is more useful when it is grounded in the workflow, constrained by the
application, and designed with failure paths in mind.

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

