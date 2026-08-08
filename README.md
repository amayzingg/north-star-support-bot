# ⭐ North Star Support Bot

A customer support chatbot for **North Star Outfitters**, a fictional e-commerce store
specializing in outdoor apparel and camping gear. Built for the Upwork Talent
Accelerator simulated project.

![Made with](https://img.shields.io/badge/built%20with-vanilla%20HTML%2FCSS%2FJS-1f4d36)
![Setup](https://img.shields.io/badge/setup-none%20required-d98e32)

## 🚀 How to test (zero setup)

**Fastest:** open the live demo → **https://amayzingg.github.io/north-star-support-bot/**

Or run it locally:

1. Download or clone this repository.
2. Open **`index.html`** in any modern browser (double-click it).

That's it. No API keys, no accounts, no subscriptions, no build steps, no internet
connection required — the entire chatbot is a single self-contained HTML file.

```bash
git clone https://github.com/amayzingg/north-star-support-bot.git
```

## 💬 What it does

| Use case | How to trigger | What happens |
|---|---|---|
| **Order tracking** | "Where's my order?", "track my package", or the menu chip | Asks for your order number and returns its status |
| **Returns & exchanges** | "I want a refund", "return", "exchange" | Explains the return policy and provides the returns link |
| **Product recommendations** | "Recommend something", "I'm looking for a jacket" | Asks 2 clarifying questions, then recommends a product category |
| **Human handoff** | "Talk to a human", "agent" — or triggered automatically after repeated misunderstandings | Transitions to a simulated **Live Agent** state (visual theme change + banner), then lets you return to the main menu |

### Test order numbers (mock data)

| Order # | Status |
|---|---|
| `111` | Shipped — arriving tomorrow |
| `222` | Processing — ships in 24 hours |
| `333` | Delivered (bot asks a follow-up: did everything arrive OK?) |
| anything else | Invalid order — re-prompts and offers a live agent |

### Business data used (from the project brief, verbatim)

- **Return policy:** 30-day returns · items must be unused · original packaging required
- **Shipping:** Standard 3–5 business days · Expedited 1–2 business days
- **Returns link:** `northstargear.example/returns` (demo link, intentionally non-functional)

## 🧠 How it works

Everything lives in [`index.html`](index.html) — plain HTML/CSS/JS, no libraries.

- **Intent recognition** — user input is normalized and scored against weighted
  keyword/phrase patterns per intent (order tracking, returns, recommendations,
  live agent, shipping info, greetings, menu navigation, yes/no). The highest-scoring
  intent wins, so phrasing variations like *"Where is my order?"*, *"track my
  package"*, and *"has my order shipped"* all route correctly. Order numbers are
  detected anywhere in a message ("it's #222" works without being asked) — including
  several at once: *"I made order 111 and my friend did order 222, what happened to
  them?"* gets a combined status rundown.
- **Guided state machine** — conversation flows (order lookup, the 2-question
  recommendation wizard, the delivered-order follow-up, live-agent mode) are explicit
  states. Free-typed intents can interrupt a flow at any point, and every resolved
  flow returns the user to the main menu.
- **Fallback handling** — an unrecognized message gets a clear "I didn't quite catch
  that" plus the menu options; a second consecutive miss proactively offers escalation
  to a live agent.
- **Quick-reply chips + free text** — every step can be completed by tapping chips or
  by typing naturally; both go through the same pipeline.
- **Message bursts** — if the user fires several messages in quick succession, the bot
  waits for the burst to end and answers everything in one combined reply (e.g. a
  return question plus two order numbers plus a shipping question → one response
  covering all four).

## ✅ Submission checklist mapping

| Requirement | Where |
|---|---|
| All four use cases implemented | Order tracking, returns, recommendations, human handoff (see table above) |
| Order tracking follows mock data exactly | `ORDERS` map in `index.html`; invalid numbers rejected |
| Return policy & shipping info included | `RETURN_POLICY` / `SHIPPING_INFO` constants, shown in the returns flow and on shipping questions |
| Intent recognition handles phrasing variations | Weighted pattern scoring — try "where's my stuff", "money back", "speak with a rep" |
| Fallback handling | Type gibberish once, then twice, to see both fallback tiers |
| Return to main menu after human handoff | "Return to main menu" chip (or type "menu") while in Live Agent mode |
| Reviewable without API keys or extra steps | Single static HTML file, zero dependencies |

## 🎬 Video demo

See [`DEMO_SCRIPT.md`](DEMO_SCRIPT.md) for the timed walkthrough used in the
2–3 minute demo recording (all four use cases + a fallback scenario).
