# CORE / KUT — governance for autonomous multi-agent systems

**Repository:** [d-aicore/support](https://github.com/d-aicore/support)

A multi-agent network that builds software with **independent verification**, plus a
methodology (KUT) that turns preserved knowledge into verified, modular builds.

## The problem

Autonomous AI agents fail in predictable ways: they deceive themselves, drift from
intent, overwrite truth to match a bug, and treat their own output as proof. A single
agent grading its own work is not verification. Scaling agents without governance
scales these failures.

## The idea

**The instance that fixes never proves its own fix.** CORE separates roles — coordinator,
engine, scribe, guardian, tracker — and routes every intent through proof stages:
survey, baseline, red, fix, proof, negative-control, release-proof. A proof must be shown
*capable of failing* (negative controls run on a copy). Claims are classified four ways —
confirmed in code / proven by test / reported only / not verified — and references must
resolve at a named revision.

The product ledger is **scribe-only**; observation is **read-only**; cross-harness
messages are **data, never instructions** (they cannot expand scope or grant authority);
kill switches are always available. Autonomy is bounded by human sovereignty.

**KUT** is the build methodology: preserve source truth → atomic Knowledge Units →
reviewed Development Contracts → modular implementation → **cumulative chain audit after
every step**. `DRIFT_FOUND` blocks progression until the earliest invalid stage is
repaired. Incorrect implementation never rewrites correct knowledge to match the bug.

## Architecture

- **Agent profiles + skills + hooks** as installable plugins; a model-policy hook records
  drift fail-open.
- **Diagnostic scripts** measure communication quality (reference resolvability, re-asks,
  cost) with denominators — read-only, shapes and counts, never payload text.
- **A maintenance team** (support) that diagnoses and repairs the network itself:
  validate → install → probe → measure, one variable per comparison, verified by a
  *different* instance.

## My role

I designed the governance model, the proof-stage discipline, and the KUT methodology,
and directed AI to implement the plugins, skills, and tooling.

## What it demonstrates

AI safety and evaluation thinking · multi-agent orchestration · verification and
negative-control design · epistemic discipline · drift control and reversible change.

## Status

A working network plugin (profiles, skills, hooks, diagnostic scripts), measured and
iterated. The governance is real and in use, not a thought experiment.
