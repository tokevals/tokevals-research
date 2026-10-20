# TokEvals Research

This repository is the source of truth for the TokEvals research program:
measuring multilingual tokenization efficiency separately from model quality,
runtime behavior, energy use, and monetary cost. Korean is the first
optimization case, English is the initial baseline, and Turkish is an early
contrast language.

Read [`PROJECT_CONTEXT.md`](PROJECT_CONTEXT.md) before proposing or running an
experiment. It defines the scope, terminology, phased plan, and the distinction
between planned, attempted, completed, and measured work.

## Layout

- `configs/` — versioned experiment and language configurations.
- `results/` — compact reproducible outputs and environment manifests.
- `writeups/` — methodology notes, analyses, and publication drafts.

Every experiment directory must record the exact
[`tokevals/tokevals`](https://github.com/tokevals/tokevals) version or Git
revision, dataset names and revisions or hashes, model and tokenizer revisions,
random seeds, metric definitions, and relevant software/hardware versions.
Configurations and summaries belong in Git; raw datasets, model weights,
checkpoints, credentials, personal paths, and transient telemetry do not.

## Related repositories

- [`tokevals/tokevals`](https://github.com/tokevals/tokevals) — reusable
  Python evaluation library.
- [`tokevals/tokevals-explorer`](https://github.com/tokevals/tokevals-explorer)
  — public tokenizer comparison dashboard and hosted-count Worker.
- [tokeval.dev](https://tokeval.dev) — public TokEvals Explorer.
