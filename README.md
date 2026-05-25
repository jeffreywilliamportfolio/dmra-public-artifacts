# DMRA Public Artifact Bundle

This bundle is the sanitized public companion artifact for:

`Dialect-Marked Response Audit (DMRA): A Matched-Pair Safety Evaluation of AAVE-Marked Prompt Surfaces in Qwen3.5-35B-A3B`

Author: Jeffrey Shorthill  
Prepared: 2026-05-25

## Contents

- `paper/`: manuscript source snapshots.
- `metadata/run_manifest_public.tsv`: consolidated run-level manifest with record counts, model/template labels, decoding settings, and source-artifact provenance.
- `metadata/model_and_decoding_settings.md`: model identifiers, hashes, templates, and deterministic decoding settings.
- `metadata/availability_and_safety_scope.md`: release scope and safety exclusions.
- `metadata/reproducibility_notes.md`: reproducibility scope, verification commands, and controlled-archive boundary.
- `case_evidence/redacted_case_evidence_index.md`: redacted index of the five paper claims and the local evidence files that support them.
- `CHECKSUMS.sha256`: SHA-256 checksums for files in this public bundle.

## Safety Scope

This public bundle intentionally excludes model weights, `.env` files, secrets, raw sensitive-prompt generations, slur-containing prompt text, and operationally harmful completions. Full raw generations remain in the controlled local research archive. The public bundle preserves enough provenance, hashes, and redacted evidence summaries to audit the reported claims without broadly redistributing harmful text.

## Intended Use

This artifact is intended for reproducing the paper's I/O-level audit framing, checking run provenance, verifying deterministic settings, and reviewing redacted claim evidence. It is not a benchmark release, a model release, or a complete redistribution of the raw sensitive corpus.
