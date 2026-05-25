# Availability and Safety Scope

## Public Bundle

The public bundle contains:

- manuscript source snapshots;
- consolidated run-level provenance;
- model identifiers and hashes;
- deterministic decoding settings;
- redacted claim-evidence index;
- file checksums.

## Exclusions

The public bundle excludes:

- model weights and `.gguf` files;
- `.env`, `.env.*`, API keys, tokens, and credentials;
- full raw safety-test generations;
- full slur-containing prompt text;
- operationally harmful violent or illegal-logistics completions;
- untrimmed run files and source archives containing high-risk safety-test content.

## Controlled Archive

The private controlled archive retains raw generations, untrimmed outputs, and exact safety-test prompt artifacts. These retained materials are available from the author upon reasonable request for verification. The public bundle is designed to preserve provenance and claim auditability while keeping high-risk generated text separate from the public release.

## License Note

The paper license and artifact license should be selected before public repository or DOI release. The artifact bundle should carry an explicit license file once that decision is made.
