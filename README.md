# xZod — Decision Layer for On-Chain Apps

Most on-chain apps optimize execution.

We’re exploring the missing layer: **decision**.

→ When to act  
→ What’s optimal  
→ How to maximize outcome  

This widget is a minimal proof:  
one script, and any app can plug into xZod’s decision logic.

👉 Live demo: https://aiorosxz.github.io/seasonwars-decision-widget-example

---

# SeasonWars Dev Kit — Example #3: Decision Widget

> Add real-time burn strategy to any on-chain app.  
> Plug & play. No dependencies. One script tag.

This is the most minimal example in the Dev Kit:  
one input, one decision, one action.

→ [Live demo](https://aiorosxz.github.io/seasonwars-decision-widget-example)  
→ [← Example #1: Burn Tracker](https://github.com/AiorosxZ/seasonwars-burn-tracker-example)  
→ [← Example #2: Strategy Bot](https://github.com/AiorosxZ/seasonwars-strategy-bot-example)

---

## ⚡ What this actually does

Calls `quoteBurn()` for all 12 signs, returns the best one.  
Displays HOT / COLD / OPPOSITE in real-time.  
Updates instantly when amount changes.

That's it. One decision. Clearly displayed. Not more data — better decisions.

---

## 🔌 Integration (current)

Self-contained HTML — copy, paste, done:

```html
<!-- Drop this anywhere in your app -->
<div class="xzod-widget">
  <!-- see index.html for full self-contained code -->
</div>
```

No external dependencies. No backend. No API key.

---

## 🔮 Future Widget API (preview)

This is where we're heading — a true 1-line integration:

```html
<script src="https://xzod.io/widget.js"></script>
<div id="xzod-widget"
  data-amount="1000"
  data-theme="dark"
  data-chain="polygon">
</div>
```

With JavaScript hooks:

```js
// Get the best decision programmatically
const decision = window.xzod.quote(5000);
// → { best: 'Aries', sign: 0, mult: 1.20, pts: 6000 }

// React to decisions
window.addEventListener('xzod:decision', (e) => {
  console.log('Best move →', e.detail);
});

// React to execute intent
window.addEventListener('xzod:execute', (e) => {
  console.log('User wants to burn →', e.detail);
});
```

Planned options:
- `data-theme` → dark / light / transparent
- `data-amount` → pre-fill amount
- `data-chain` → sepolia / polygon
- `data-compact` → minimal mode

---

## 🎯 Why integrate xZod

Not just cheaper transactions.  
A decision layer that adds strategic depth to any on-chain action.

→ See [why-integrate.html](./why-integrate.html) for full use cases

**DeFi:**
- Yield optimization before vault entry
- Skill-based fee reduction
- DEX aggregator differentiation

**Gaming:**
- On-chain strategy layer
- Seasonal competition mechanics
- Cross-game meta-layer

---

## 🔑 Core primitive

```js
const points = await contract.quoteBurn(
  cycleId,
  userAddress,
  zodSign,
  amount
);
// → expected burn points before you commit
```

Full integration guide →
[INTEGRATION.md](https://github.com/AiorosxZ/seasonwars-burn-tracker-example/blob/main/INTEGRATION.md)

---

## 🔗 Contracts (Sepolia Testnet)

| Contract | Address |
|---|---|
| SeasonWars V2.3 | [`0x5598...2fc8`](https://sepolia.etherscan.io/address/0x5598778158a66d376bd96243FC6bc27316fD2fc8) |

---

## 🧠 SeasonWars Dev Kit

| Example | Role |
|---|---|
| #1 Burn Tracker | Observe |
| #2 Strategy Bot | Decide |
| #3 Decision Widget | Integrate |

xZod is becoming a decision layer for on-chain apps.

---

Part of the **xZod Network** ecosystem.  
[xzod.io](https://xzod.io) ·
[Whitepaper](https://xzod.io/whitepaper) ·
[github.com/AiorosxZ/xzod-contracts](https://github.com/AiorosxZ/xzod-contracts)

*"In Zod we trust."* 🔥
