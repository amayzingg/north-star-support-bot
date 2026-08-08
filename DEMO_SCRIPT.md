# 🎬 Demo Video Script — North Star Support Bot

Target length: **2:30–2:45**. Screen-record the browser with `index.html` open and a
fresh page (refresh before recording). Speak casually — the timings below are loose
guides, not a teleprompter.

> Tip: do one silent practice run first so the typing feels smooth. If a section runs
> long, the #222 lookup in Part 1 is the easiest cut.

---

## Part 0 — Intro (0:00–0:15)

Say something like:

> "Hi, I'm May. This is North Star Support Bot — a customer support chatbot for a
> fictional outdoor gear store. It's a single self-contained HTML file: no API keys,
> no accounts, nothing to install — you just open it in a browser. I'll walk through
> all four use cases plus fallback handling."

Show the fresh chat: greeting message + the four menu chips.

## Part 1 — Order tracking (0:15–0:55)

1. **Type** `Where's my order?` → bot asks for the order number.
   > "It recognizes natural phrasing, not just button clicks."
2. **Type** `111` → *Shipped, arriving tomorrow.*
3. When it asks "Anything else?", click **Track my order**, then **type** `999`
   → invalid order message with a re-try / live agent offer.
   > "Unknown order numbers are handled gracefully."
4. **Type** `333` → *Delivered*, and the bot asks a follow-up — click **All good 👍**.
   > "For delivered orders it checks that everything arrived OK."

## Part 2 — Returns & exchanges (0:55–1:15)

1. **Type** `I want to return something` → return policy (30-day, unused, original
   packaging) + returns link.
   > "The policy and link come straight from the business data provided."
2. Click **Back to menu**.

## Part 3 — Product recommendations (1:15–1:45)

1. Click **Product recommendations** (or type `what should I buy?`).
2. Bot asks what you're gearing up for → click **Camping**.
3. Bot asks mild vs. cold weather → click **Cold weather**.
4. Bot recommends *4-season tents and insulated sleeping bags*.
   > "Two clarifying questions, then a category recommendation — and you can answer
   > by typing or tapping."

## Part 4 — Fallback scenario (1:45–2:05)

1. **Type** `asdf qwerty` → clear "didn't catch that" + menu options.
2. **Type** `blorp` again → bot escalates: offers a live agent.
   > "One miss re-offers the menu; two in a row proactively offers a human."

## Part 5 — Human handoff (2:05–2:35)

1. Click **Talk to a live agent** → notice the **theme change and Live Agent banner**;
   simulated agent "Riley" greets you.
2. **Type** `my tent zipper broke` → agent acknowledges (simulated).
3. Click **Return to main menu** → bot mode resumes with the main menu.
   > "The handoff is clearly communicated, and the user can always come back to the
   > bot afterwards."

## Part 6 — Wrap up (2:35–2:45)

> "That's all four use cases — order tracking with the exact mock data, returns,
> guided recommendations, and human handoff — plus intent recognition and two-tier
> fallback handling, in one dependency-free file. Thanks for watching!"

---

## Coverage checklist (spec requirements)

- [x] Use case 1: Order tracking (valid #111, invalid #999, delivered #333 follow-up)
- [x] Use case 2: Returns & exchanges (policy + link)
- [x] Use case 3: Product recommendations (2 clarifying questions → category)
- [x] Use case 4: Human handoff (clear transition + return to main menu)
- [x] At least one fallback scenario (two, including escalation)
- [x] Intent recognition via typed natural phrases (Parts 1, 2, 4)
