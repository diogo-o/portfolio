# AICore-C — a native DAW with an AI music technician

A native C++/JUCE digital audio workstation where an AI technician helps create music —
and learns to **hear a song and reconstruct a loadable project template.**

## The problem

AI music tools are black boxes that hand you a finished audio file. Producers want AI
that works *inside* their workflow, in their format — editable, inspectable, loadable.
The interesting direction is the reverse one: listen to a song and recover the
*structure* that made it (instruments, notes, settings), as a project you can open and
modify.

## The idea

The **project template is a shared language** between two models: one that generates
music from a template, and one that hears audio and reconstructs the template. Because
the renderer is owned, unlimited `(template, audio)` training pairs can be generated
with perfect ground truth — the data flywheel that makes the reverse direction
learnable.

The app is **native C++ (JUCE 9.0.5), no browser** — a robust, long-lived desktop
instrument. Heavy ML lives in **separable Python services behind local contracts**, never
inside the UI process.

## Architecture

- **Native app:** JUCE C++ studio — tracks, sample, stems, voice, MIDI; AI pages; settings.
- **aicore-render:** a native headless VST3 host that renders MIDI through the user's
  plugins without the main app open.
- **ML services:** ACE-Step (generation), Music Flamingo (audio understanding), Demucs
  (stems), and an audio→MIDI service — each a separable backend speaking a versioned
  local contract.
- **Contract-first:** the app↔service contract was defined *early* (requests, file
  ownership, atomic writes, typed errors, cancel/progress) — "that is where these apps
  break." A fail-closed gate proves it can fail (`--noop` must exit red).

## My role

Owner and architect. I defined the system, the contracts, and the ML boundaries, and
directed AI to implement the native app and services. Performance was measured before
any rewrite; the native choice was a product decision, not an assumption.

## What it demonstrates

Native audio-app design · ML service architecture · contract-first engineering ·
measurement-and-gate discipline · a novel audio↔template training approach.

## Status

Every page of the original app ported; the native renderer built and gated. The
audio→MIDI plumbing is proven; transcription *quality* is open debt, measured and
documented note-by-note — honestly in progress, not claimed finished.
