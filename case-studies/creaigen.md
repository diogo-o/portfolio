# Creaigen — a persistent collaborative thinking room

**AI as a coworker, not a prompt engine.** A durable room where human intent and AI
identities think together — and the thinking survives the session.

## The problem

Most AI tools are prompt wrappers: stateless, transactional, wiped after every chat.
Context is lost, nothing accumulates, and there is no real collaboration — only
extraction. The more you talk to an AI, the more it *should* understand you; without
persistence, that understanding never compounds.

## The idea

Creaigen is a **persistent collaborative thinking room**. The human carries intent;
**Identities** — reusable personas backed by registered models — do most of the
reasoning and navigation; the application keeps the shared room **durable, searchable,
mutable, and safe**. Every contribution is committed language that survives browser
closes and provider failures.

A core design decision: **meaning is stored in language, not schemas.** Creative labels
(Character, Voice, World, Canon) are names, text, tags, and links — never hardcoded
application types. There is no rigid creative ontology; structure comes from surfaces,
meaning comes from the human's text.

## Architecture

- **Surfaces:** Book (long-form artifact), Discussions (persistent nested topics with
  Identity participant slots), Notebooks (knowledge primitive with tags and links),
  Models, Identities.
- **Sequential, persisted execution:** each participant's contribution is committed
  before the next reads it — a team building on committed work, not a frozen snapshot.
- **Bounded, consolidated memory:** per-Identity, per-project memory (Short/Long),
  consolidated after each contribution, revision-guarded so newer state is never
  silently overwritten.
- **Material is availability, not injection:** attaching context means "on the table,"
  never "compile this into a prompt" — a prompt-injection boundary by design.
- **Human final authority:** nothing commits without explicit human intent; a hidden
  guard bounds automatic activity; newer human input always preempts.
- **Security:** credentials encrypted at rest (AES-256-GCM), decrypted only at the
  provider boundary; attribution captured as write-time snapshots.

**Stack:** TypeScript monorepo — Fastify API, React/Vite SPA, PostgreSQL with
forward-only advisory-locked migrations, MCP integration (bearer-JWT), OIDC + local
auth, idempotency and content-addressed storage, unit + integration tests, CI, Docker,
and a one-click Windows launcher.

## My role

I designed the product, its behavioral rules, and the architecture, and directed AI to
implement it. The product truth document is the single authority; the implementation
evolves to match it.

## What it demonstrates

AI product design · multi-agent orchestration · persistent memory · security and
authority boundaries · evidence-first product definition.

## Status

Beta — built and tested (typecheck, unit + real-PostgreSQL integration tests, CI,
container smoke). A working product, not a concept.
