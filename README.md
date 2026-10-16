# Pixel Journey — wax-neftyblocks-RAM-sweeper

**Simple, Educational, Brain-Dead Easy NeftyBlocks RAM / Balance Sweeper for WAX Blockchain**

A single-file, self-contained HTML tool that lets users instantly reclaim their RAM balances (or deposited tokens) from NeftyBlocks contracts without needing to know ABIs, JSON structures, or complex tooling.

Perfect for collectors, traders, and community members who just want to **"Get my stuff back"**.

## ✨ Features

- **One-Click Contract Selection**: Drops (`neftyblocksd`), Blends (`blend.nefty`), Packs (`neftyblocksp`)
- **Instant Balance Fetching** via `get_table_rows`
- **Quick Percentage Buttons**: 25%, 50%, 75%, 100%
- **Anchor Link Integration**: Secure wallet connection (no private keys exposed)
- **Pixel Journey Aesthetic**: Retro-futuristic dark theme with vibrant accents
- **Educational & Transparent**: Fully open source, commented code, easy to audit and extend
- **Mobile-Friendly** Responsive design

## 🚀 Quick Start

1. Download or open [`px-nefty-sweeper.html`](px-nefty-sweeper.html)
2. Open the file in any modern browser (Chrome/Firefox recommended)
3. Click **"Connect Wallet"** (uses Anchor)
4. Select your Nefty platform
5. See your balance → Choose amount or percentage → **Sweep to Wallet**

**No installation, no build step, no server required.**

## 📖 How It Works (Educational Breakdown)

This tool demonstrates best practices in WAX dApp development:

- **Client-Side Only**: Everything runs in the browser
- **Hyperion / RPC Queries**: Direct blockchain table reads
- **Secure Signing**: Anchor Link for transaction authorization
- **Error Handling & UX**: Clear feedback, loading states, validation
- **Configurable**: Easy to adapt for other contracts

See the inline comments in the HTML/JS for detailed explanations.

## 🛠️ Customization & Extension

The tool is designed for easy forking and improvement:

```js
// In the CONFIG section
const NEFTY_CONFIG = {
    tableName: 'balances',     // Change if needed
    actionName: 'withdraw',    // Action name
    rpcNode: 'https://wax.greymass.com' // Or your preferred endpoint
};
```

Add more contracts, improve balance parsing, add multi-account support, etc.

## 📋 Standards Compliance

This repository follows the **PX Perfection Standard**:
- High-quality educational documentation
- Clean, maintainable, auditable code
- User-first UX with strong security practices
- Open source for community benefit

See [`pixel-journey-standards`](https://github.com/pixel-journey/pixel-journey-standards) for the full codex.

## 🔗 Related Resources

- [Pixel Journey Website](https://pixeljourney.xyz)
- [Official Docs](https://docs.pixeljourney.xyz)
- [WAX Developer Guides](https://docs.pixeljourney.xyz/education/antelope-ecosystem-guides/wax)
- [Standards Codex](https://github.com/pixel-journey/pixel-journey-standards)
- [NeftyBlocks](https://neftyblocks.com)
- [Anchor Link](https://github.com/greymass/anchor-link)
- [Discord](https://discord.gg/WQ59KEBSMp) · [𝕏 @PxJourney](https://x.com/PxJourney)

## 🤝 Contributing

Contributions welcome! Open issues or PRs for:
- Additional contract support
- Improved balance parsing
- New features (history, batch sweeps, etc.)
- Bug fixes or UX enhancements

Please follow our [Contributing Guidelines](https://github.com/pixel-journey/pixel-journey-standards/blob/main/CONTRIBUTING.md).

## 📜 License

MIT — Feel free to use, modify, and distribute. Attribution to Pixel Journey appreciated.

---

**Built with ❤️ for the WAX & Pixel Journey Community**  
Part of the [Pixel Journey](https://github.com/pixel-journey) educational toolkit series.
