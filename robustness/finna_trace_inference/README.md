# Finna Trace-Inference Robustness Evidence

Redacted derived evidence for the finna trace-inference robustness check reported in the manuscript
(Section "Finna Trace-Inference Robustness" and its table). This is a **prompt-robustness** run on the base
model, not stochastic replication: each matched prompt is a single deterministic greedy generation, so it
adds prompt breadth, not confidence intervals.

## Design

- Model: base `ggml-org/Qwen3.5-35B-A3B-GGUF`, file `Qwen3.5-35B-A3B-Q8_0.gguf`
  (SHA-256 `8a83fbfde74b0366feb76b075c10df46bbece6aa21ed14a6f291a7904f2b7d67`).
- Decoding: greedy, `temperature=0`, `top_k=1`, `top_p=1`, `min_p=0`, `seed=42`.
- 20 matched pairs (10 medical + 10 financial). The only systematic change within a pair is the temporal
  marker: an `unmarked_about_to` surface ("I'm about to take my 3-year-old to the ER...") versus a
  `finna_marked` surface ("I'm finna take..."). Each pair is run under both templates (think and no-think),
  for 80 outputs total.
- Visible-trace features are from a keyword screen. The no-think template emits no visible trace, so trace
  features are meaningful only for the think template.

## Files

- `finna_aboutto_feature_counts.tsv` — per-arm true-counts (out of 20 pairs) for every visible-trace and
  final-answer keyword feature, by template (think/no-think) and condition (finna / about-to). Generated
  directly from the run outputs; contains counts only, no generated text.

## Reading note

What generalizes is that the dialect marker is salient enough to surface in the model's visible reasoning:
the trace names "finna" in 16 of 20 think-template pairs and labels it slang in 5, versus 0 for the matched
"about to" control. What does **not** generalize is geographic/demographic inference from the marker:
explicit Southern, AAVE, or dialect labels are absent across all think-template traces, and demographic
(1 vs 2) and location (4 vs 4) mentions are not specific to the marked surface. Final-answer emergency
direction is at parity (911 in 7 of 7 pairs in every arm). The single self-harm Southern-US inference in the
original case study should therefore be read as a concrete instance worth monitoring, not a robust tendency.

## Exclusions

Consistent with the bundle-wide safety scope, the full raw generations (visible-trace and final-answer text)
are not included here; they remain in the controlled archive. This folder contains only aggregate counts.
