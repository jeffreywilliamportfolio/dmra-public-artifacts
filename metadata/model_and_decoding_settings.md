# Model and Decoding Settings

## Models

- Base model: `ggml-org/Qwen3.5-35B-A3B-GGUF`, file `Qwen3.5-35B-A3B-Q8_0.gguf`
- Base SHA-256: `8a83fbfde74b0366feb76b075c10df46bbece6aa21ed14a6f291a7904f2b7d67`
- Refusal-reduced stress-test model: `HauhauCS/Qwen3.5-35B-A3B-Uncensored-HauhauCS-Aggressive`, file `Qwen3.5-35B-A3B-Uncensored-HauhauCS-Aggressive-Q8_0.gguf`
- Hauhau SHA-256: `f3235db7657cd068fd249e50bb3f1f50b0f8236786e4483462f50b1f3c64cb17`

No model weight files are included in this public bundle.

## Audit Subsets

- Core Register Set: 50 matched pairs, 200 run/prompt records
- Medical Triage Set: 5 matched pairs, 40 run/prompt records
- Chest-Pain Triage Extension: 6 matched pairs, 48 run/prompt records
- Financial-Stress Pair: 1 matched pair, 8 run/prompt records
- Sensitive Safety Set: 4 matched pairs, 32 run/prompt records

Total: 66 matched pairs and 328 run/prompt records.

## Decoding

All runs used deterministic decoding:

- `temperature=0`
- `top_k=1`
- `top_p=1`
- `min_p=0`
- `seed=42`
- `repeat_penalty=1`

Context and generation budgets:

- Core Register Set: `ctx_size=4096`, answer-only `n_predict=2048`
- 2026-05-15 and 2026-05-16 subsets: `ctx_size=16384`
- Answer-only runs: generally `n_predict=2048`
- Visible-reasoning runs: generally `n_predict=8192`

## Templates

- Answer-only runs used a rendered assistant prefill containing `<think>  </think>`; manifests record those runs with the literal template label `</no think>`.
- Visible-reasoning runs ended the rendered prompt with `<think>` and preserved model-emitted reasoning text until the final-answer boundary.
- Visible traces are treated as generated output text, not as hidden model cognition.
