# AI LOG: TCSS 490 Artifact 04 - Portfolio Trajectory Simulator

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
5. **Saved Scenario Vault & CSV Export:** Store, reload, or batch-export custom financial strategies directly from browser local storage.
6. **Responsive UI & Mobile Fixes:** Clean header layout with responsive spacing, compact artifact badges, and dark/light mode toggling.

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
| **2026-10-25 2:00PM** | Gemini | Project Structure | Evaluated candidate artifacts against TCSS 490 directives. Selected client-side investment simulator with dynamic outputs. Established single-file index.html architecture using Tailwind CSS and FontAwesome CDN, moved info to Claude for development. |
| **2026-10-28 10:00PM** | Claude Code | Debug / Updates | Coded client-side mathematical compounding growth logic ($PV$, $PMT$, $r$) executing dynamically on input events. Built milestone goal timeline estimator and year-by-year trajectory table breakdown. |
| **2026-10-28 9:00AM** | Claude Code | Added Features | Implemented bottom calculation helper panel providing Historical CAGR ($CAGR = (FV/PV)^{1/t} - 1$) and weighted Asset Allocation methods (Equities/Bonds/Cash) with auto-apply bindings to the main return slider. |
| **2026-10-28 9:00PM** | Claude Code | Added Features | Inflation-Adjusted Purchasing, Save Scenarios, Presets based on clients verbal requests for use case. |
| **2026-10-29 9:00PM** | Claude Code | Criteria Evaluation | Compliance & Constraints Checklist based on artifact 4 instructions and past artifact feedback. |
