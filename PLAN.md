# Team Plan: Portfolio Trajectory Simulator (TCSS 490 Artifact 4)

This is the shared plan both of us (and both of our Claude sessions) work from.
`CLAUDE.MD` points here, so any agent working in this repo reads it first.

## Who it is for

A co-worker who is planning their own long-term investing (the "Client Baseline" preset:
$45k starting balance, $800/month). They asked to see how their money could grow, what it is
worth after inflation, and how different savings plans stack up against each other.

**Hand-off (done 11/05):** we showed them the live site at https://ashvirguptar.github.io/TCSS490-Artifact-4/.
They used the tool successfully and got a reliable forecast of their planned investments (see the log in `CLAUDE.MD`).

## What we are building

One single-page, client-side calculator (`index.html`, no backend). All numbers come from real
compounding math in the browser.

## Who owns which part

| Owner | Part | Where in `index.html` |
| :--- | :--- | :--- |
| **Ashvir** | Compounding engine, inputs and presets, metric cards, growth chart, year-by-year table | Main grid + `calculateTrajectory()` / `renderSvgChart()` |
| **Ashvir** | Return-rate helper (CAGR & asset allocation) | Bottom panel |
| **Ashvir** | Saved Scenario Vault + CSV export (original version), GitHub Pages deployment | Vault card + vault script |
| **Vanessa** | Side-by-side scenario comparison: pick 2–4 saved scenarios and see them in one table and one chart | "Side-by-Side Scenario Comparison" panel + the comparison script block |
| **Vanessa** | Vault changes the comparison needs (Compare checkbox, saving inflation with each scenario) | Vault script |

Each section of `index.html` that has an owner is marked with an HTML/JS comment naming them.

## How we keep from colliding

1. **Nobody pushes to `main`.** Every change goes on a branch named `<name>/<feature>`
   (e.g. `vanessa/scenario-compare`).
2. **Every branch becomes a pull request.** The *other* person reviews and merges it:
   Ashvir merges Vanessa's PRs, Vanessa merges Ashvir's.
3. **Pull `main` before starting a branch** so you build on the latest version.
4. **Stay in your own section.** If you need to change code the other person owns, say so in the
   PR description so they can check it.
5. **Log as you go.** Each PR adds its own rows to the Log Entries table in `CLAUDE.MD`.
   GitHub Pages redeploys automatically after a merge.

## Saved scenario format (the boundary between our parts)

Ashvir's vault **writes** saved scenarios and Vanessa's comparison **reads** them, so this format
is the one place our code has to agree. Any change to it follows the rules at the end of this
section.

**Where:** `localStorage` key `tcss490_artifact4_vault`, holding a JSON array of scenario objects,
newest first.

| Field | Type | Required | Written by | Meaning |
| :--- | :--- | :--- | :--- | :--- |
| `name` | string | yes | Save button | Shown as plain text everywhere (always escaped, never inserted as HTML) |
| `principal` | number ≥ 0 | yes | Save button | Starting balance in dollars |
| `monthly` | number ≥ 0 | yes | Save button | Monthly contribution in dollars |
| `rate` | number | yes | Save button | Annual return in percent (`8` means 8%). With a range, the mid estimate `(rateLow + rateHigh) / 2`, rounded to 2 decimals |
| `years` | integer ≥ 1 | yes | Save button | Time horizon |
| `goal` | number ≥ 0 | yes | Save button | Target portfolio value in dollars |
| `inflation` | number | no | Save button | Annual inflation in percent. Missing on scenarios saved before 10/30: the comparison uses **2.5**, and Load leaves the slider as it is |
| `rateLow`, `rateHigh` | number | no, **both or neither** | Save button | Return range in percent, `rateLow ≤ rateHigh`. Load restores the range; the comparison uses `rate` (the mid) |
| `compare` | boolean | no | Compare checkbox | Ticked for the comparison. Missing means `false`. At most 4 are `true` |

**Readers:** Load (`applyScenario`), CSV export, the vault list, and the comparison panel
(`simulateScenario` / `renderComparison`).

**Example** (a range scenario; more examples in [`tests/scenario-examples.json`](tests/scenario-examples.json)):

```json
{
  "name": "Co-Worker 401k",
  "principal": 45000,
  "monthly": 800,
  "rate": 8,
  "rateLow": 6,
  "rateHigh": 10,
  "years": 25,
  "goal": 1000000,
  "inflation": 2.5,
  "compare": true
}
```

**Rules for changing the format**
1. A new field must be optional and have a stated default, so scenarios already saved in the
   co-worker's browser keep working.
2. Never rename, remove, or change the meaning of a field unless the same PR updates every reader
   listed above.
3. Update this table, `tests/scenario-examples.json`, and the tests in the same PR.

## Tests

Open `tests/index.html` through a local server or on the live site
(https://ashvirguptar.github.io/TCSS490-Artifact-4/tests/). It loads the real `index.html` in a
hidden frame and checks:

* **Oracle:** the compounding engines match the closed-form future-value formula
  `FV = PV(1 + r)^n + PMT((1 + r)^n − 1) / r` (`PV + PMT·n` at 0%).
* **Metamorphic relations:** properties that must hold even without a known answer (0% return adds
  no growth, doubling contributions doubles a $0-start balance, scaling every dollar amount scales
  the result, and so on).
* **Contract:** the example scenarios follow the format above, what the Save button writes follows
  it too, and the comparison panel and main calculator agree on every example.

Run the tests before opening a PR that touches the engine, the vault, or the comparison, and say
in the PR that they pass.

## Timeline

| Date | What | Who |
| :--- | :--- | :--- |
| 10/25–10/29 | Base simulator built and deployed | Ashvir |
| 10/30 | Plan written down (this file), comparison feature built, PR opened | Vanessa |
| 11/05 | Showed the co-worker the live site; they used it successfully and got a reliable forecast of their planned investments (logged in `CLAUDE.MD`) | Both |
| 11/06 | Saved-scenario format written down (above) and tests added in `tests/` | Vanessa |

> Note: the base simulator was built before this plan was written down. This file records
> how we are working from here on.
