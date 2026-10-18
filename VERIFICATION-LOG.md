# Verification Log

Honest record of what has and has not been tested.
Never mark something verified without running it and recording evidence.

## Status legend
- `VERIFIED` — ran against live endpoint or manual test
- `UNTESTED` — code exists, never executed
- `BROKEN` — ran, failed
- `N/A` — not applicable

## Claims in this repo
| Claim | Status | Evidence |
| --- | --- | --- |
| Single-file HTML tool can read balances via get_table_rows | UNTESTED | px-nefty-sweeper.html |
| Withdraw action builds correctly for selected contracts | UNTESTED | NEFTY_CONFIG + action builder |
| Contract accounts and action names must be verified on explorer before use | VERIFIED | README disclaimers |
| Recovery-only — not recommended for new deposits | VERIFIED | Trust level + ECOSYSTEM-RESILIENCE reference |

## How to verify
```bash
# Manual: open px-nefty-sweeper.html, connect wallet, inspect table rows
# Cross-check balances on a WAX explorer before signing
```

**Trust label:** recovery-documentation (educational-reference for the recovery pattern)
