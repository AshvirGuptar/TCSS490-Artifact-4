# AI LOG: TCSS 490 Artifact 04 - Portfolio Trajectory Simulator

## 0. Team Plan (read this first)
Two people work on this repo, each with their own Claude session, and our agents do not talk to each other.
**Read `PLAN.md` before making any change.** In short:
* **Ownership:** Ashvir owns the core engine, inputs/presets, metric cards, growth chart, table, return-rate helper and deployment. Vanessa owns the Side-by-Side Scenario Comparison panel and the vault changes it needs. Owned sections of `index.html` are marked with comments.
* **Branches & PRs:** never commit to `main`. Work on `<name>/<feature>`, open a pull request, and the *other* teammate reviews and merges it.
* **Stay in your lane:** only edit the other person's section if the task requires it, and call that out in the PR description.
* **Log:** every PR adds its own rows to the Log Entries table at the bottom of this file.

## 1. Project Info for AI use along with Overview & Objective
* **Course:** TCSS 490 (Special Topics in Computing / Software Systems Portfolio)
* **Project Name:** Portfolio Trajectory Simulator (Investment Goal & Trajectory Calculator)
* **Creators:** Vanessa and Ashvir 
* **Live Deployment URL:** `https://ashvirguptar.github.io/TCSS490-Artifact-4/`
* **Repository:** `https://github.com/AshvirGuptar/TCSS490-Artifact-4`
* **Core Objective:** Provide a production-ready, 100% client-side financial compounding calculator and scenario modeling dashboard that satisfies all academic constraints while delivering professional utility.

---

## 2. Selecting Technical Stack & Architecture
* **Markup & Styling:** HTML5, Tailwind CSS (via CDN with custom dark mode configuration), FontAwesome icons, Inter & JetBrains Mono typography.
* **Scripting:** Vanilla JavaScript (ES6+), running entirely client-side. No backend required.
* **Persistence:** HTML5 `localStorage` for saving and loading user-defined portfolio scenarios.
* **Data Export:** Built-in CSV export engine converting saved scenarios into downloadable spreadsheet data.
* **Visualization:** Dynamic SVG path generation engine drawing real-time Principal vs. Total Balance growth curves.

---

## 3. Implemented Feature Set
1. **Compounding Math Engine:** Monthly compounding interest calculation factoring starting principal, monthly recurring contributions, expected annual return rate, and total time horizon.
2. **Inflation-Adjusted Purchasing Power:** Real-time discount calculation applying an adjustable annual inflation rate (e.g., 2.5%) to show future milestone values in today's dollars.
3. **"What-If" Boost Accelerator:** Allows users to test secondary recurring contribution boosts (e.g., +$200/mo) and instantly computes how many months or years sooner they reach their target goal.
4. **Expected Return Rate Helper (Bottom Panel):**
   * *Historical CAGR Mode:* Derives annualized returns from cost basis, current value, and holding duration.
   * *Asset Allocation Mode:* Calculates weighted average return benchmarks across Equities (~10%), Bonds (~4.5%), and Cash (~2%).
5. **Saved Scenario Vault & CSV Export:** Store, reload, or batch-export custom financial strategies directly from browser local storage. Each saved scenario also keeps its inflation rate.
6. **Side-by-Side Scenario Comparison (Vanessa):** Tick "Compare" on 2–4 saved scenarios to see them in one table (final balance, today's dollars, invested, growth, time to goal, with the best values highlighted) and one overlaid balance chart.
7. **Responsive UI & Mobile Fixes:** Clean header layout with responsive spacing, compact artifact badges, and dark/light mode toggling.

---

## 4. Compliance & Constraints Checklist
* **Ensure Zero Fake Text Outputs:** All calculations are driven by real mathematical compound growth formulas executed natively in JavaScript.
* **Single-File Portability:** Packed into a clean, modern structure designed for easy repository deployment and grading.

---

## Workflow Notes & AI Collaboration Reflection

- **Primary Tool Used:** Claude (collaborative development and code architecture).
- **Additional Tool Used:** Gemini (Brainstorming, idea validation and initial planning).
- **Key Technical Challenges Resolved:**
  1. Ensuring compounding math updates instantly in real-time as range sliders move without stuttering or DOM lag.
  2. Structuring `localStorage` serialization so users can save, name, and compare multiple financial scenarios side-by-side.
  3. Strict adherence to instructor feedback: all math executes live in standard browser JS with zero hardcoded or simulated AI audit text.


## Log Entries

| Timestamp (UTC) | Tool / AI Model | Development Focus / Goal | Technical Intent & Summary |
| :--- | :--- | :--- | :--- |
| **2026-10-25 2:00PM** | Gemini | Project Structure | Evaluated artifact ideas against artifact 4 instructions. Selected client-side investment simulator with dynamic outputs that lined up with the needs of a known and trusted future user. Established single-file index.html architecture using Tailwind CSS and FontAwesome CDN, moved info to Claude for development. |
| **2026-10-28 8:00AM** | Claude Code | Debug / Updates | Coded client-side mathematical compounding growth logic ($PV$, $PMT$, $r$) executing dynamically on input events. Built milestone goal timeline estimator and year-by-year trajectory table breakdown. |
| **2026-10-28 9:00AM** | Claude Code | Added Features | Implemented bottom calculation helper panel providing Historical CAGR ($CAGR = (FV/PV)^{1/t} - 1$) and weighted Asset Allocation methods (Equities/Bonds/Cash) with auto-apply bindings to the main return slider. |
| **2026-10-28 9:00PM** | Claude Code | Added Features | Inflation-Adjusted Purchasing, Save Scenarios, Presets based on clients verbal requests for use case. |
| **2026-10-29 9:00PM** | Claude Code | Criteria Evaluation | Compliance & Constraints Checklist based on artifact 4 instructions and past artifact feedback. |
| **2026-10-30 12:30PM** | Claude Code (Vanessa) | Planning | Reviewed the repo against the Artifact 4 directions. Found it had no written team plan and no work from Vanessa yet, and that the log claimed scenarios could be compared side by side when the vault could only load one at a time. Picked the side-by-side comparison as Vanessa's part. |
| **2026-10-30 1:00PM** | Claude Code (Vanessa) | Team Plan | Wrote `PLAN.md` (who it's for, who owns which part, branch/PR/merge rules, timeline) and added a "Team Plan" section to the top of this file so both of our agents work from the same plan. Branch: `vanessa/scenario-compare`. |
| **2026-10-30 1:30PM** | Claude Code (Vanessa) | Added Feature | Built the Side-by-Side Scenario Comparison panel: "Compare" checkbox on each saved scenario (2–4 at once), a table with scenarios as columns (projected value, today's dollars, invested, growth, time to goal, best values starred), and an overlaid balance chart. Saved scenarios now keep their inflation rate (older saves fall back to 2.5%). Also escaped scenario names so HTML typed into a name can't run on the page, and fixed CSV quoting for names that contain quotes. |
| **2026-10-30 1:45PM** | Claude Code (Vanessa) | Testing | Tested in the browser: comparison numbers match the main calculator exactly for all three presets, the 4-scenario limit works, the panel hides with fewer than 2 selected, a name containing `<img onerror>` shows as plain text, and the layout fits a 375px phone screen without sideways scrolling. |
| *(pending)* | (Vanessa) | Hand-off | Show the co-worker the live site after the PR is merged and record what they said here. |
