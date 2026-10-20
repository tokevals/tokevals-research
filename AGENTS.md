# Agent Guide

## Start here

- Read `PROJECT_CONTEXT.md` before research, architecture, or terminology
  decisions. It is the cross-repository source of truth.
- TokEval measures multilingual tokenization efficiency and its effects on
  model quality and serving cost. Korean is the first optimization case;
  English is the initial baseline and Turkish an early contrast language.
- Label work as planned, attempted, completed, or measured. Do not report an
  experimental target as a result or claim an improvement without evidence.

## Research and reproducibility

- Keep token count, model quality, latency, throughput, memory, energy, and
  monetary cost as separate measurements. Combine them only through an
  explicitly defined cost-per-successful-task analysis.
- Use controlled comparisons, explicit metrics, fixed seeds, and versioned
  configs. Record dataset/model/tokenizer revisions or hashes and relevant
  hardware/software versions.
- Every experiment pins the `tanagerlabs/tokeval` library version or Git
  revision it uses.
- Preserve raw bytes and byte spans in tokenizer results. Test Unicode round
  trips, normalization, unusual spacing, emoji, mixed scripts, and boundaries
  that split UTF-8 code points.
- Prefer configuration-driven language support over language-specific branches
  in shared methods.
- Vocabulary expansion experiments preserve existing token IDs and special
  tokens, initialize new embeddings deliberately, and compare against both an
  untouched baseline and a matched data/compute control.

## Repository layout and hygiene

- Put experiment configuration under `configs/`, reproducible outputs and
  manifests under `results/`, and analyses or drafts under `writeups/`.
- Do not commit raw or processed datasets, model weights, checkpoints,
  credentials, API keys, personal paths, account identifiers, or raw machine
  diagnostics. The existing compact environment snapshot is the only current
  exception.
- Commit only licensed, intentional artifacts and record provenance.
- Preserve unrelated changes and avoid destructive Git operations.
