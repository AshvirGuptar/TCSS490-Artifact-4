# AI Prompt Log & Development Activity - Artifact 04
## Project: Investment Goal & Trajectory Calculator
## Student: Ashvir Guptar

This document records the prompt engineering and development workflow utilized to design, build, and test the Investment Goal & Trajectory Calculator for TCSS 490 (Artifact 04).

---

## Development & AI Interaction Log

| Date | Start | End | Duration | Pace | Location | Eng | Type | Tool / Model | Focus / Activity Description |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **10/28** | 10:00 AM | 11:30 AM | 90 mins | Normal | Home (Remote) | 4 | Build | Gemini | Initialized application architecture. Generated client-side financial compounding math engine (`FV = PV(1+r)^n + PMT[...]`) and built dark/light Tailwind CSS layout with responsive sliders. |
| **10/28** | 1:00 PM | 2:30 PM | 90 mins | Fast | UW Tacoma Campus | 5 | Build / Integration | Gemini | Structured preset profile loader (co-worker scenario & aggressive growth test). Configured dynamic year-by-year milestone breakdown rendering and fixed DOM re-calculation listeners. |
| **10/28** | 3:30 PM | 4:30 PM | 60 mins | Normal | UW Tacoma Campus | 4 | Debug / Storage | Gemini | Implemented scenario saving vault using `localStorage`. Resolved JSON array mapping bug for deletion handlers to ensure saved comparison strategies persist properly across browser reloads. |
| **10/28** | 4:30 PM | 5:00 PM | 30 mins | Fast | Home (Remote) | 5 | Deployment | Terminal / Git | Validated application on GitHub Pages, verified zero console errors, ensured 100% real mathematical execution (no static/fake outputs), and updated course portfolio cards. |

---

## Workflow Notes & AI Collaboration Reflection

- **Primary Tool Used:** Gemini (collaborative development and code architecture).
- **Key Technical Challenges Resolved:**
  1. Ensuring compounding math updates instantly in real-time as range sliders move without stuttering or DOM lag.
  2. Structuring `localStorage` serialization so users can save, name, and compare multiple financial scenarios side-by-side.
  3. Strict adherence to instructor feedback: all math executes live in standard browser JS with zero hardcoded or simulated AI audit text.
