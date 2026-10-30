# Team Plan: Portfolio Trajectory Simulator (TCSS 490 Artifact 4)

This is the shared plan both of us (and both of our Claude sessions) work from.
`CLAUDE.MD` points here, so any agent working in this repo reads it first.

## Who it is for

A co-worker who is planning their own long-term investing (the "Client Baseline" preset:
$45k starting balance, $800/month). They asked to see how their money could grow, what it is
worth after inflation, and how different savings plans stack up against each other.

**Hand-off:** we show them the live site at https://ashvirguptar.github.io/TCSS490-Artifact-4/
before the due date and record what they said in the log.

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

## Timeline

| Date | What | Who |
| :--- | :--- | :--- |
| 10/25–10/29 | Base simulator built and deployed | Ashvir |
| 10/30 | Plan written down (this file), comparison feature built, PR opened | Vanessa |
| After merge | Show the co-worker the live site, log their feedback | Both |

> Note: the base simulator was built before this plan was written down. This file records
> how we are working from here on.
