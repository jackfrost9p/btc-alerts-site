# btc-alerts-site

Three static pages describing **BTC Streak Alerts**, a private tool that watches
BTC-USD 15-minute candles and pushes a notification on a three-candle streak.

No build step, no dependencies, no JavaScript.

| File | What it is |
|---|---|
| `index.html` | What the tool does, how it works, sample alerts |
| `privacy.html` | Privacy notice — nothing is collected from anyone |
| `terms.html` | Disclaimers: not financial advice, no warranty, no service offered |

## Status: personal project, not a service

These pages originally existed to satisfy **A2P 10DLC carrier registration** for
an SMS version of the alerter. That version is retired. Alerts now go out over a
push backend instead, so none of the SMS compliance machinery applies anymore:

- No opt-in keyword, no START/STOP/HELP flows, no phone number.
- No message-frequency or "message and data rates may apply" disclosures.
- No Twilio, no carrier, no subscriber list.
- No sign-up of any kind. The tool has exactly one recipient: its author.

If the 10DLC campaign is still registered, cancel it — the pages it pointed at
no longer describe an SMS program.

## Do not publish delivery details

The notification destination is configured entirely through the alerter's local
`.env` and stays out of this repo and off these pages. Nothing here should ever
carry:

- a bot token, API key, or app token
- a chat ID, user key, topic name, channel name, or handle
- an invite or join link of any kind

The pages describe delivery only as "a private push channel" on purpose. Keep it
that way — anything more specific is an invitation for someone to find it.
`.gitignore` should cover `.env`; verify before every push.

## Editing

Each page carries its own inline `<style>` block, and the three share the same
CSS variables (`--paper`, `--ink`, `--rule`, `--green`, `--red`). Change a color
in one file and change it in all three, or the set stops matching.

`index.html`, `privacy.html`, and `terms.html` each cross-link to the other two
in the footer. Renaming a file means fixing six links.

Both `privacy.html` and `terms.html` show a "Last updated" date near the top.
Bump it when the text changes.

## Publishing on GitHub Pages

1. Commit to the root of `main`.
2. Settings → Pages → Source: `main` / `/ (root)`.
3. Confirm the three URLs load in a private window.

All three pages carry `<meta name="robots" content="noindex">`, since a personal
project page has no reason to rank in search results. Remove it if you ever want
them indexed.
