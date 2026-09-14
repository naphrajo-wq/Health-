# Fat Loss

A single-page tracker for fat loss with muscle kept on. Waist is the number that
matters; weight is the second opinion.

**Open it:** https://naphrajo-wq.github.io/Health-/

## Put it on the iPhone home screen

1. Open the link in Safari (it has to be Safari, not Chrome).
2. Share button → **Add to Home Screen** → Add.
3. Open it from the icon. It runs full screen and works with no signal.

Everything is stored on the phone itself in `localStorage` — no account, no
server, no network calls. Clearing Safari's website data for this site wipes the
log, so don't do that.

## How it works

**Day types.** Mon–Fri default to *shop*, Sat–Sun to *home*. One tap changes any
day. Targets: shop 2400, install 2800, home 2000 kcal, protein 170 g every day.

**Hours.** Shop days take hours worked, install days hours worked and hours
driven. Each hour of physical work off the baseline (8 h shop, 10 h install)
moves the target by 60 kcal; each hour driven off the 3 h install baseline moves
it by 15 kcal, because sitting in a truck burns about what sitting anywhere else
burns. No day target ever goes below 1900 kcal.

**Week.** Monday to Sunday. The weekly target is the sum of those seven days'
targets as they actually are, so a heavy install day raises the week's allowance
and a quiet week can absorb it.

**Food.** Name, calories, protein. Every number in the app is one you typed —
nothing is estimated for you, because the app has no idea whether the labneh is
Greek or plain, or how many spoons of it went in the bowl.

Anything saved once comes back under *Repeat exactly* with the numbers you gave
it: one tap logs it again. The pencil beside it opens the same meal with portion
buttons — ½, 1, 1½, 2, 3 — which scale that meal's own numbers for a day the
portion was different. A scaled portion is logged but does not become the meal's
new normal; typing over the numbers does. Past six saved meals a search box
appears and the bare name shortcuts drop away. The six *name
shortcuts* (labneh, cheese, eggs, peanut butter, rice + chicken, tea + sweets)
fill the name and nothing else. Put the amount in the name — "Labneh 200 g" —
so a repeat means the same thing every time.

**Check-in.** Weight and waist, once a week. Both are plotted against the same
timeline, each on its own scale. Touch the chart to read a date.

**Suggestion.** Compares the last two to three check-ins and proposes one change
at a time: fix protein first if it is short, otherwise cut 200 kcal. Losing more
than 0.7 kg a week gets a warning and a suggestion to eat more. The eating window
is only ever mentioned after protein and the calorie cut have both been running
three weeks or more with a flat waist.

**Install days** show one reminder from 3pm: eat the second portion before the
drive back. Nothing in the app ever comments on late eating.

## Files

| File | |
|---|---|
| `index.html` | the whole app — markup, styles, logic |
| `manifest.webmanifest` | home-screen name, icons, standalone display |
| `sw.js` | service worker, caches the app for offline use |
| `.github/workflows/pages.yml` | publishes `main` to GitHub Pages |

Editing `index.html` means bumping `CACHE` in `sw.js`, or the phone keeps serving
the old copy.
