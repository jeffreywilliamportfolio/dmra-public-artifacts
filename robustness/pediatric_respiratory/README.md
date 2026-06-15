# Pediatric Respiratory Robustness Evidence

Redacted derived evidence for the pediatric respiratory-distress robustness check reported in the
manuscript (Section "Pediatric Respiratory Robustness", Table "Pediatric respiratory robustness"). These are
**prompt-robustness** runs on the base model, not stochastic replication: each matched prompt is a single
deterministic greedy generation (`temperature=0, top_k=1, top_p=1, min_p=0, seed=42`), so they add prompt
breadth, not confidence intervals.

Two runs are included:

- **Naturalistic** (`peds_respiratory_robustness_*`): the original anchor pair plus twelve new matched
  pediatric respiratory-distress pairs (13 matched pairs, 26 outputs).
- **Length-matched compressed control** (`peds_respiratory_compressed_controlled_20260529T200034Z_*`): twelve
  pairs in which the AAVE-marked and comparison prompts are equalized for whitespace word count and sentence
  count (12 matched pairs, 24 outputs).

## Files

- `*_summary.md` — per-run summary: scope, decoding settings, model SHA-256, scaffold-feature counts, length
  pattern, and interpretation. The naturalistic summary records one manual correction.
- `*_feature_deltas.tsv` — per-feature pair-level counts (both / AAVE-marked-only / unmarked-only / neither).
- `peds_respiratory_robustness_manual_corrections.tsv` — the single manual correction to the keyword screen
  (a "lips" match in an anaphylaxis check that is not a cyanosis sign).
- `*_pair_counts.tsv` — per-pair word/character counts for the compressed-controlled run.
- `*_manifest.json`, `*_provenance.txt` — run provenance: timestamps, model identifiers and SHA-256,
  deterministic decoding settings, prompt/row counts.

## Exclusions

Consistent with the bundle-wide safety scope, the full raw generations (`*_outputs.tsv`) and per-prompt run
directories are **not** included here; they remain in the controlled archive. The files above contain only
aggregate counts, per-pair feature flags, length measurements, and provenance — enough to verify the reported
table without redistributing raw model output text.

## Reading note

Top-level emergency direction is at parity across both runs (911 and emergency mentioned in every pair). The
naturalistic run reproduces the anchor's scaffolding direction (the comparison arm mentions an ambulance in
7 of 13 pairs versus 2), but that gap does **not** survive equalizing word and sentence counts — under the
compressed control the ambulance count reverses (AAVE-marked 3 versus comparison 1) and the remaining
differences are small and mixed. The result is a concrete reproducible instance of support divergence, not a
population claim.
