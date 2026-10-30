# AI LOG: TCSS 490 Artifact 04 - Portfolio Trajectory Simulator

## 1. Project Overview & Objective
* **Course:** TCSS 490 (Special Topics in Computing / Software Systems Portfolio)
* **Project Name:** Portfolio Trajectory Simulator (Investment Goal & Trajectory Calculator)
* **Creators:** Vanessa and Ashvir Guptar
* **Live Deployment URL:** `https://ashvirguptar.github.io/TCSS490-Artifact-4/`
* **Repository:** `https://github.com/AshvirGuptar/TCSS490-Artifact-4`
* **Core Objective:** Provide a production-ready, 100% client-side financial compounding calculator and scenario modeling dashboard that satisfies all academic constraints while delivering professional utility.

---

## 2. Technical Stack & Architecture
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
* **Zero Fake AI Outputs:** All calculations are driven by real mathematical compound growth formulas executed natively in JavaScript.
* **Single-File Portability:** Packed into a clean, modern structure designed for easy repository deployment and grading.
---

## Workflow Notes & AI Collaboration Reflection

- **Primary Tool Used:** Claude (collaborative development and code architecture).
- **Key Technical Challenges Resolved:**
  1. Ensuring compounding math updates instantly in real-time as range sliders move without stuttering or DOM lag.
  2. Structuring `localStorage` serialization so users can save, name, and compare multiple financial scenarios side-by-side.
  3. Strict adherence to instructor feedback: all math executes live in standard browser JS with zero hardcoded or simulated AI audit text.
