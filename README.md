# Compliance pages for A2P 10DLC

Three static pages. No build step, no dependencies, no JavaScript.

## Before you publish

Search and replace across all three files:

| Placeholder | Replace with |
|---|---|
| `[YOUR NAME]` | Your legal name — must match the `brand_name` on your Brand registration |
| `[YOUR EMAIL]` | A real, monitored address (same one used on the Brand) |
| `[CITY, STATE]` | e.g. `Dallas, Texas` |
| `[DATE]` | Today's date, e.g. `August 18, 2026` |

Also change "up to 20 messages per day" if your `--backtest 30` result says
otherwise. The stated frequency should be true.

```bash
cd site
sed -i '' 's/\[YOUR NAME\]/Jane Doe/g; s/\[YOUR EMAIL\]/jane@example.com/g' *.html
```
(drop the `''` after `-i` on Linux)

## Publish free on GitHub Pages

1. Create a public repo named exactly `<your-username>.github.io`.
2. Commit these three files to the root of the `main` branch.
3. Settings → Pages → Source: `main` / `/ (root)`. Save.
4. Wait a minute or two, then confirm both URLs load in a private window:
   - `https://<your-username>.github.io/privacy.html`
   - `https://<your-username>.github.io/terms.html`

The private-window check matters. Reviewers reject pages that need a login,
sit behind an auth wall, redirect to another domain, or return an error.

## What the reviewer is looking for

The privacy policy carries all four required elements: it is publicly
accessible, it states that mobile numbers are not shared with third parties,
it discloses message frequency, and it includes "Message and data rates may
apply." The terms page is on the same domain and is plain HTML, not a PDF.

Keep both pages live for as long as the campaign is registered.
