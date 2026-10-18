# ACTION-RECIPES.md — Legacy Nefty-class recovery

**Trust:** `recovery` / `avoid-new-value`  
**Rule:** Replace nothing blindly — confirm account, table, and ABI on a live explorer.

## Contracts referenced by the HTML tool

| UI label | Account (as in tool) | Intended use |
|---------|----------------------|--------------|
| Drops | `neftyblocksd` | Balance / RAM-style withdraw recovery |
| Blends | `blend.nefty` | Same pattern |
| Packs | `neftyblocksp` | Same pattern |

These names appear in the shipped `px-nefty-sweeper.html`. **Operators and ABIs may change; verify before signing.**

## Generic withdraw recipe

```
Contract: <verified account>
Action:   withdraw          # confirm name in ABI
Auth:     user active (or required perm)
Data:     owner = <your account>
          amount = <quantity string matching contract>
```

## Read path

```
get_table_rows
  code  = contract
  scope = contract   # tool default — confirm if your rows use actor scope
  table = balances   # confirm
  lower_bound / upper_bound = your account
```

If your balance is scoped differently, adjust the tool’s fetch body.

## Related user needs (other blueprints)

| Need | Approach |
|------|----------|
| Unpack / claim pack NFT | Pack contract claim actions — see drops/pack experience blueprint |
| Unstake farm | Farm contract unstake/claim — verify account on explorer |
| Cancel market listing | Marketplace cancel action |

## Do not

- Advertise these contracts for **new** creator launches
- Assume `withdraw` always succeeds without ABI check
- Send the same raw amount string to contracts with different precision rules without checking

---

*Pixel Journey — recovery documentation*
