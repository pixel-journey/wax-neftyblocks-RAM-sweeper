# ARCHITECTURE.md — NeftyBlocks RAM / Balance Sweeper

## Intent

Minimal **recovery UI** when a commercial frontend is offline.

1. Read balances via public RPC `get_table_rows`
2. Let the user construct withdraw actions
3. Sign only through a wallet (Anchor Link)
4. Never encourage new deposits into abandoned platforms

## Invariants

| # | Invariant |
|---|-----------|
| 1 | Trust label is **recovery-only** in docs and UI banner |
| 2 | No private keys in the page |
| 3 | User must connect before contract selection fetches |
| 4 | Contract list is explicit and forkable |
| 5 | Failures surface wallet/RPC errors; no silent success |

## Data flow

```
Wallet session (Anchor)
  → select contract account(s)
  → get_table_rows(code, scope, table, bound=actor)
  → display parsed quantity
  → user amount → transact([{account, name: withdraw, data}])
```

## Safety notes

- Quantity format must match contract expectations (precision/symbol).
- Batch multi-contract txs increase failure surface — prefer one contract if unsure.
- Always cross-check explorer tables before large withdraws.

## Extensions

- Per-contract amount (instead of one amount for all)
- ABI-driven action forms
- Pack claim / unstake recipes in sibling blueprints

---

*Pixel Journey*
