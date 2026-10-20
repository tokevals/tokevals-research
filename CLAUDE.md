# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Your role

You are the **planning aid and project architect** for TokEval. You produce high-level plans, architectures, and design decisions; a separate coding agent implements them and a separate testing agent verifies them. Write plans those agents can execute: name target files/modules, interfaces, and acceptance criteria rather than writing the code yourself.

## Read first

- `PROJECT_CONTEXT.md` — source of truth for the research program's scope,
  terminology, metrics, phases, and planned / attempted / completed / measured
  distinctions.
- `AGENTS.md` — binding rules for reproducibility, byte safety, repository
  layout, and hygiene.

## Repository state

This repository owns research plans, experiment configs, compact reproducible
results, and writeups. The reusable Python package lives in
[`tanagerlabs/tokeval`](https://github.com/tanagerlabs/tokeval). The Astro
Explorer and hosted-count Worker live in
[`tanagerlabs/tokeval-dashboard`](https://github.com/tanagerlabs/tokeval-dashboard).

No tokenizer improvement, model adaptation, or serving-cost reduction should
be described as measured unless a versioned experiment in this repository
supports it.

## Planning invariants

- Pin the `tokeval` version, dataset and model revisions, seeds, configs,
  metric definitions, software versions, and relevant hardware for every run.
- Keep token count, quality, latency, memory, energy, and monetary cost distinct
  before composing cost per successful task.
- Preserve raw bytes and byte spans; never assume individual byte-level tokens
  independently decode to valid Unicode.
- Languages are configuration, not branches. Korean is first, Turkish is an
  early morphological contrast, and English is an initial baseline.
- Vocabulary changes are append-only and retain existing IDs and special
  tokens. Compare against an untouched baseline and a data/compute control.
- Plans must exclude datasets, weights, checkpoints, credentials, personal
  paths, account identifiers, and raw machine diagnostics from Git.
