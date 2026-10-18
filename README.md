# wax-neftyblocks-RAM-sweeper

> **Status:** 🔄 Recovery toolkit (PX + ECOSYSTEM-RESILIENCE)  
> **Trust level:** **Recovery only** — not recommended for new high-value deposits  
> **Catalog:** [wax-ecosystem-blueprint-catalog](https://github.com/pixel-journey/wax-ecosystem-blueprint-catalog) · [ECOSYSTEM-RESILIENCE.md](https://github.com/pixel-journey/wax-ecosystem-blueprint-catalog/blob/main/ECOSYSTEM-RESILIENCE.md)

**Goal:** A **single-file, offline-capable** browser tool so users can attempt to **withdraw remaining balances / RAM-related deposits** from legacy NeftyBlocks-class contracts when the product website is gone or unusable.

> **The chain is the backup. The website is not.**

---

## Critical disclaimers

1. **NeftyBlocks** has been widely reported as **out of business / without a maintained product UI**. Do **not** treat this tool as an endorsement to deposit new funds into those contracts.
2. Contract accounts in the HTML (`neftyblocksd`, `blend.nefty`, `neftyblocksp`) are **community recovery targets**. **Verify on a block explorer** (tables, ABI, your row) before signing anything.
3. Table layout, action names, and quantity formats can change or differ by account. If the wallet rejects the action, stop and inspect the ABI — do not spam failed txs.
4. This is **educational operational tooling**, not legal, financial, or audit advice.
5. Prefer **self-controlled contracts** for any new creator tooling (see resilience doc). Deploy cost on WAX is often small relative to platform risk.

---

## What it does

| Step | Behavior |
|------|----------|
| Connect | Anchor Link (no keys in the page) |
| Select | Multi-select Drops / Blends / Packs contract buttons |
| Read | `get_table_rows` on configured table for your account scope |
| Withdraw | Builds `withdraw`-style actions for selected contracts |

Open [`px-nefty-sweeper.html`](px-nefty-sweeper.html) in a modern browser — **no build step**.

---

## Quick start

1. Open `px-nefty-sweeper.html` locally or via GitHub Pages/raw host you trust.
2. Connect wallet (Anchor).
3. Select one or more platforms.
4. Confirm displayed balance matches explorer.
5. Choose amount → review wallet prompt carefully → sign only if correct.

---

## Configuration

In the HTML `NEFTY_CONFIG` block:

- `tableName` — default `balances` (verify)
- `actionName` — default `withdraw` (verify ABI)
- `rpcNode` — use a reliable WAX endpoint you trust

Fork and extend for other **recovery** contracts the same way: document account + action + table in git, keep UI minimal.

---

## Related

- Catalog **ECOSYSTEM-RESILIENCE.md**
- `wax-community-governance-and-proposal-tools` — recovery recipe patterns
- `wax-drops-and-pack-opening-experience` — pack claim UX patterns (next recovery pass)
- Multi-sig blueprints — for treasuries that must not depend on a vendor domain

---

## License

MIT — **Pixel Journey** educational toolkit.

*Last refined: October 2026*
