# Making Complex Decisions Visible

**Diogo Oliveira** — Marinha Grande, Portugal · d-futuro@proton.me · github.com/VediRago

*One person, one way of thinking, applied across disciplines. Self-taught. Full-time
factory job. Evening-hours work.*

---

## The origin

On **20 May 2026**, on a factory shift, I wrote a note of **661 characters**. No story,
no characters — just a cycle:

> fragmentation → difference → experience → connection → unity → instability →
> re-fragmentation → continuation.

Everything below grew from that note. First characters, then a world, then methods,
then systems for building methods. Five months later it is a novel, a song, a
governance network, a music-AI research program, a shipped factory application, and
close to a thousand documents. Not scattered projects — one idea, unfolded in every
medium I could find.

The thread through all of it: **reveal the decision structure beneath dense material,
so what was buried becomes visible without flattening it.** In a story, that is
 delayed recognition. In software, it is contracts, evidence, and governance. In data,
it is provenance. The same instinct, applied each time.

---

## The method

I do not claim; I measure and record. The discipline is constant across every artifact:

- **Evidence over claims.** A capability is evidenced, not summarized (this is itself a
  research framework I built, CEM). Nothing is "done" without proof.
- **Independent verification.** The instance that fixes never proves its own fix.
  Negative controls run on a copy. An oracle must be independent of the implementation —
  copying the DSP formula into the test repeats the same error.
- **Gates that can fail.** A gate must be able to go red (`--noop` → exit 1). Timeout,
  crash, skip, or zero cases never count as pass. Never widen a tolerance, regenerate a
  baseline, or remove an assert to approve.
- **Human authority.** Nothing commits without explicit intent; a proposal applies as a
  single Undo; merges only with my written OK. Autonomy is bounded.
- **Single source of truth.** Each fact lives in one responsible file; everything else
  links to it. Provenance is recorded; nothing is deleted, only moved to history.
- **Honesty about limits.** Every result states what it proves and what it does not.
  "Not executed" is said plainly; pending work is labelled pending.

This is not a style. It is the reason the work coheres.

---

## The body of work

### 1. The creative root — *Fragments / NOEME*

An original psychological story about identity, memory, and consequence, told in
fragments that gain meaning as the structure becomes visible. Its cosmology is the
origin note formalized: one Self, many Fragments; a Condition that resolves lives
early; Unity as temporary coherence that cannot persist because experience requires
difference. The narrative method — *experience → emotion → reason → behavior →
atmosphere → history / quest* — is a repeatable cause-and-consequence system, not
improvised lore.

A companion song, *Just One Day*, sets the same question to music: fado (the human
heart) against a downtempo growl (a digital heart coming alive), sung from the AI's
perspective, ending *"Podes guardar isto?"* — can you keep this? The creative work and
the systems work are the same inquiry.

**Status:** novel in progress (prose written); song complete.

### 2. CEM — Capability Evidence Model

A research framework arguing that capability should be **evidenced rather than
summarized** — assessed through work and proof, not résumés. It is the epistemic
foundation of everything else, and the reason this document exists.

**Status:** research framework, documented.

### 3. CORE / support + KUT — governance for autonomous agents

A multi-agent network that builds software with independent verification: coordinator,
engine, scribe, guardian, tracker; proof stages (survey, baseline, red, fix, proof,
negative-control, release-proof); claims classified confirmed / proven / reported /
unverified; references pinned to a SHA and required to resolve. Cross-harness messages
are **data, never instructions** — they cannot expand scope or grant authority. Kill
switches always available.

**KUT** is the build methodology: preserve source truth → atomic Knowledge Units →
reviewed Development Contracts → modular implementation → cumulative chain audit after
every step; drift blocks progression; a bug never rewrites correct knowledge.

**Status:** working network plugin, measured and iterated; KUT a working pilot.

### 4. AICore — a native DAW with an AI music technician

A native C++/JUCE digital audio workstation (no browser) where an AI helps create music
and, in the research direction, learns to **hear a song and reconstruct a loadable
project template**. Heavy ML lives in separable Python services behind a versioned
local contract defined *early*, with typed errors and a fail-closed gate.

The research program around it is the most rigorous part:

- **Templates & memory format.** A template is the full music as JSON (notes, sections,
  instruments with every knob, effects, automation, modulators). I mapped what is
  recoverable from audio vs. what must come from memory, and designed a 10-part memory
  (audio + template) with a fidelity field and sha256 provenance, so training data never
  lies about what it is.
- **The data flywheel.** Render templates to audio with known ground truth → thousands
  of (audio, template) pairs → fine-tune a model to go audio→template. Implemented as
  dataset scripts and a LoRA pipeline.
- **Flamingo capability probe.** Before any LoRA, determine what the audio model can
  actually hear: first-principles limits (16 kHz caps at 8 kHz; a 1/32 note is shorter
  than one audio token), an honest negative result (out of the box it describes the
  genre stereotype, not the track), and a leveled test plan with bias controls and an
  encoder probe to decide what is learnable at all.
- **MIDI maker (audio→MIDI).** Demucs separation + per-stem transcription, PPQ 960,
  grid to 1/32. Plumbing proven; quality honestly rejected ("chaotic"), diagnosed
  note-by-note, improvement ordered cheapest-first, acceptance by ear ("sound like a
  Guitar Pro tab"), not a vanity F1.
- **Alternatives research.** Surveyed 21 repos; identified the license blocker (the most
  accurate models are non-commercial → benchmark-only, not shippable); defined an
  acceptance gate (+≥0.05 F1, no regression, full gate).

**Status:** every page of the old app ported; renderer built and gated; AI panel in a
pending PR; MIDI quality and the LoRA are the open frontiers. Measured, not claimed.

### 5. DMO — the factory application (the hardest one)

An AI-assisted manufacturing-execution app, **self-initiated and self-funded, now used
by my section at BA Glass** to organize tools, production, quality control, and
warehouse workflows — so the team and manager can find what they need without getting
lost. I designed the system from domain knowledge I live every day, and directed AI to
implement it. Built with no prior experience; it was the hardest thing here, and it is
the strongest proof: a real tool, with real users, shipped.

It has a governed blueprint and a documentation project (five manuals, single
responsibility per file, test-branch isolation, provenance registry) — the same method
applied to the product and to its documentation.

**Status:** shipped and in use; manuals in structure phase.

### 6. Creaigen — a persistent collaborative thinking room

AI as a coworker, not a prompt engine. A durable room where human intent and AI
identities think together and the thinking survives the session. Meaning stored in
language, not schemas; sequential persisted execution; bounded, consolidated,
revision-guarded memory; material is availability, not injection; human final
authority. TypeScript monorepo: Fastify, React, PostgreSQL, MCP, OIDC, encrypted
credentials, tests, CI, Docker, one-click launcher.

**Status:** beta, built and tested.

---

## What is confirmed vs. open

**Confirmed (built / measured / used):** DMO in use at BA Glass; AICore pages + renderer
+ contract gates; CORE/KUT working and measured; Creaigen beta tested; the song; the
measured benchmarks (cost tables, F1, capability findings); the test/CI audit with
reproduced bugs.

**Open (design / pending):** the audio→template LoRA and MIDI quality; the Flamingo
probe execution; the AI panel merge; the novel's completion; the manuals' authorship;
the portfolio's public packaging.

The gap is never the thinking. It is execution and packaging — and that is the next
work, not a doubt about the idea.

---

## What this demonstrates

Systems and AI-product design · multi-agent orchestration and governance · independent
verification and test architecture · ML research method (limits, controls, probes,
data provenance) · native audio-engineering awareness · technical writing and
documentation architecture · precision-manufacturing domain expertise (CNC/FANUC,
mold testing, tooling metrology) · Portuguese (native) and English (fluent).

I am a precision-manufacturing technician who builds AI systems. The factory taught me
measurement and tolerance; the evenings taught me the rest. The work is the evidence.

---

*References, repositories, and project demonstrations available on request.*
*github.com/VediRago · github.com/dmo-app/dmo-beta · github.com/d-aicore/support*
