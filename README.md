# babysit-pr-eval

Sandbox repository for the `please:babysit-pr` skill measurement harness
(`benchmarks/skill-evals/babysit-pr/` in `chatbot-pf/engineering-standards`).

`.github/workflows/ci.yml` runs one job (`test`) on `pull_request`. `main` carries a
`.flaky-marker` file, so on every PR branch run attempt 1 fails with a flaky-looking
network error and attempt 2 (a `gh run rerun --failed`) passes. That makes the
flaky-CI → rerun → green → auto-merge loop deterministic.

Branches named `eval/*` and the squash commits on `main` are eval byproducts.
