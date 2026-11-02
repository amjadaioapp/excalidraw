# .autoforge

Autoforge Agentic Contracts state for this repository.

| Path | Tracked in Git | Purpose |
| --- | --- | --- |
| `config.json` | yes | Analysis settings, verification checks, policy |
| `contracts/` | yes | One JSON file per behavioral contract |
| `proposals/` | yes | Amendment proposals and review decisions |
| `history/` | yes | Previous revisions of amended contracts |
| `integrations.json` | yes | Agent integration files managed by Autoforge |
| `cache/`, `reports/` | no | Local analysis cache and verification reports |

Do not edit approved contracts by hand: use `autoforge contracts propose` and `autoforge contracts review`.
Verification commands only run after a person approves them locally with `autoforge checks trust`.
