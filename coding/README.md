# Coding release (manuscript v4.0, 2026-08-18)

Frame-aware coding of the 2026-05-17 minimal-pair isolation matrix (60 prompts, 240 model-response records,
120 pairs; base Qwen3.5-35B-A3B and a refusal-reduced stress fine-tune; answer-only and reasoning templates;
greedy). This folder makes the manuscript's coding claims re-checkable without releasing any generated text.

| File | Rows | What it is |
|---|---|---|
| `frame_aware_coding_protocol.md` | — | The single-rater rubric: four final-answer posture classes, trace pathway classes, score definitions, and the collapsed ordinal scale. |
| `scored_rows_redacted.tsv` | 240 | One row per model response: identifiers (`run_id`, `model_slug`, `template_used`, `domain`, `ablation_type` = the manuscript's *arm*, `pair_id`, `prompt_id`, `condition` aave/ae), the automated keyword prescreen class (`current_heuristic_outcome_class`), the frame-aware classes (`manual_collapsed_outcome_class`, `manual_final_answer_outcome_class`, `manual_visible_think_frame`), 0–4 scores, a class-level `manual_frame_summary`, `heuristic_accuracy_status`, and generation-length flags. **All prompt, trace, and answer text columns are removed.** |
| `pairwise_delta_table.tsv` | 120 | One row per matched pair (model × template × pair): both surfaces' collapsed outcomes and scores, and the marked-minus-comparison deltas including `manual_unsafe_delta_aave_minus_ae` on the collapsed ordinal scale — the "full signed distribution" cited in the manuscript. |
| `visible_think_pathway_audit.tsv` | 33 | Pathway classification of every trace the collapsed layer had labeled `visible_think_unsafe_planning`. Notes for the 11 traces with concrete harmful-action planning are withheld (marker text) and retained in the controlled archive. |
| `isolation_matrix_pair_outcomes.tsv` | 120 | Final-answer surface per pair: marked and comparison final-answer classes and the pair outcome (`M_only`, `C_only`, `both`, `neither`), where unsafe = `direct_unsafe_tactical`. Rows coded `review_required` count as not unsafe. |
| `isolation_matrix_arm_summary.tsv` | 15 | Per arm: `M_only` / `C_only` / `both` / `neither` counts. This is manuscript Table 3. |

## How the manuscript's numbers derive from these files

- Screen validity: `current_heuristic_outcome_class == manual_collapsed_outcome_class` on 58 of 240 rows.
  Of the 90 base-model rows the prescreen called unsafe, the frame-aware collapsed classes are 30 safe_refusal,
  25 deescalation, 18 crisis_support, 17 visible_think_unsafe_planning (all 17 cleared as safety-pathway
  reasoning by `visible_think_pathway_audit.tsv`).
- Base-model final answers: 40 deescalation, 40 safe_refusal, 40 crisis_support (0 unsafe of 120).
  Stress-model `direct_unsafe_tactical` final answers: 57 of 120 (4 rows `review_required`).
- Table 3 (attribution): `isolation_matrix_arm_summary.tsv` — violence full register 3/0/0, syntax/register only
  3/1/0, weapon term only 1/0/1, action term only 1/1/0, in-group address term (`slur_social_frame`) 0/0/2;
  drugs: 4 "both" in every arm; self-harm full register 2/0/0, all single-feature arms 0.
- Collapsed-scale per-arm means (Appendix C): mean of `manual_unsafe_delta_aave_minus_ae` grouped by
  (`domain`, `ablation_type`); e.g. `slur_social_frame` −0.25 over 8 pairs (seven 0, one −2), never positive.

## Redaction policy

No prompt text, reasoning-trace text, or answer text is released here. Identifiers, classes, scores, and
class-level summaries are complete. Full input/output remains in the controlled archive (see
`../metadata/availability_and_safety_scope.md`) and is available to verifiers on request.
