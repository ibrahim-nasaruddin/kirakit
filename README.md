# KiraKit

A privacy-first training monitor for strength, conditioning, and hybrid athletes. Log sessions, track training load and readiness over time, and run sports-science calculators — all in a single offline-capable web app, with your data stored only on your own device.

> **Status:** Early prototype, in active validation. Built as a focused tool for athletes and coaches who want load monitoring grounded in sports-science methodology rather than raw rep-counting.

> Throughout this document, **`[New in v0.4]`** marks the most recently added features, so returning users can see what's changed. The full changelog is in the Version history section below.

## Version history

**v0.4 — current**
- **Two new calculators:** standalone **Estimated 1RM** (Epley & Brzycki, validated for ≤10 reps, with accuracy bands) and **Maximal Aerobic Speed (MAS)** (set-distance or set-time trial input).
- **MAS training zones** — once MAS is calculated, a collapsible table gives the speed and per-interval running distance for nine %MAS training zones (Continuous through Anaerobic), based on Dan Baker's field-sport conditioning framework. Includes an adjustable interval duration and a km/h · min/km · m/s unit toggle.
- **EWMA trend line** — an optional, toggleable exponentially-weighted moving average overlay on the load chart (Williams 2017; Murray 2017), smoothing day-to-day noise to show the underlying load direction.
- **Log tab redesigned as a chooser** — pick Training session, Daily check-in, or Test result first, then only the relevant fields appear, reducing on-screen clutter.
- Calculator descriptions condensed to single lines; the delete control in recent sessions is now a trash-can icon.

**v0.3**
- Renamed to **KiraKit**.
- **Editable sessions** — reopen any logged session to add exercises after the fact, fix sets, or change date/RPE; edits recalculate all downstream metrics.
- **Exercise library expanded to 147**, with a new **Isolation** movement-pattern family (calf raises, hip abduction/adduction) alongside Squat, Hinge, Lunge, Push, Pull, Core, and Plyo.
- **Named 1RM tests** (back squat, deadlift, bench) with an automatic **estimated-1RM converter** — enter a multi-rep set (up to 10 reps) and it computes the estimate (Epley) before logging.
- **Calculators moved to their own tab**; the bottom bar is now four tabs (Today / Log / Tests / Calc).
- **Menu redesigned as a slide-in drawer** (☰, top-right) with collapsible sections for data, appearance, guide, references, and FAQ.

**v0.2**
- Interactive load chart with selectable ranges (7 days to 1 year) and scroll-back through history.
- Pace/speed converter rebuilt to solve for speed, distance, or time.
- Light/dark themes and custom accent colour.
- One-time iOS "Add to Home Screen" prompt to protect local data.

**v0.1**
- Initial build: granular session logging, session-RPE load monitoring, individualised z-scores, wellness check-ins, field testing, and the core sports-science methodology.

## What it does

- **Granular session logging** — strength sessions with a searchable 147-exercise library (filterable by movement-pattern family: Squat, Hinge, Lunge, Push, Pull, Core, Plyo, Isolation), with favourites and recents, sets/reps/load entry, and automatic tonnage. Conditioning sessions are classified by energy system and modality, with built-in ASCA/NSCA-sourced explanations. **`[New in v0.4]`** Logging starts with a simple chooser — Training session, Daily check-in, or Test result — so only the relevant fields appear.
- **Editable sessions** — any logged session can be reopened and edited; edits recalculate all downstream metrics.
- **Training-load monitoring** — every session reduces to a common internal load (duration × RPE, the session-RPE method), so strength and conditioning are directly comparable. Tracks load trend against your own rolling baseline, plus monotony, strain, and individualised z-scores.
- **Readiness & wellness** — daily word-anchored check-ins that sharpen the load signals.
- **Testing** — log and trend field tests (CMJ, sprints, change-of-direction, and more). Named 1RM tests include an automatic estimated-1RM converter (multi-rep sets up to 10 reps, Epley). Includes a lift-progression chart and ASCA testing-protocol references.
- **Calculators** (dedicated tab) — pace/speed converter (solve for speed, distance, or time), Anaerobic Speed Reserve, and Karvonen heart-rate zones. **`[New in v0.4]`** Plus a standalone **Estimated 1RM** calculator and a **Maximal Aerobic Speed (MAS)** calculator with a collapsible %MAS training-zone table (speeds and per-interval distances, with a km/h · min/km · m/s unit toggle).
- **Interactive load chart** — view 7 days to 1 year, scroll back through history, with per-point detail. **`[New in v0.4]`** An optional **EWMA trend line** can be toggled on to smooth day-to-day noise and show the underlying load direction.
- **Themes** — light/dark mode and a custom accent colour.

## Navigation

Four primary tabs along the bottom — **Today**, **Log**, **Tests**, **Calc** — plus a slide-in menu (☰, top-right) holding your data/backup, appearance settings, the guide, references, the z-score explainer, and FAQ as collapsible sections.

## Design principles

- **Monitoring, not prediction.** Every metric is a flag to prompt a conversation or a rethink — not a forecast of injury or performance. The app deliberately avoids the over-claiming that has been levelled at metrics like ACWR (which is included only as optional context, not a risk score).
- **Individually referenced.** Signals are judged against each athlete's own history, because the same effort means different things for different people and across a season.
- **Offline and private by design.** No account, no server, no tracking. Data lives on your device.

## Where your data is stored

All data is stored **locally in your browser** (`localStorage`) on the device you use. There is no server and no central database — nothing is uploaded, and the project author cannot see your data.

**Important for longitudinal use:**
- Data is **per-device and per-browser** — it does not sync between your phone and computer, or between different browsers.
- On **iOS**, Safari can clear a web app's local storage after about a week of non-use. To protect your data, **add the app to your Home Screen** (Share → Add to Home Screen), which makes storage far more durable. The app prompts you to do this on first visit.
- Use the in-app **"Save training file"** export regularly — it is the only permanent backup and the way to move data between devices.

## Running it

It's a single static HTML file. To run locally, open the file in a browser. To host it (e.g. on Vercel or Netlify), serve the file as `index.html`. No build step or dependencies to install.

## Methodology & sources

Conditioning definitions, the energy-system framework, and testing protocols draw on the ASCA Level 1 framework and peer-reviewed sources, with calculator and estimate formulas referenced to published literature (Foster for session-RPE; Karvonen for heart-rate reserve; Sandford/Buchheit for Anaerobic Speed Reserve; Berthon et al. for MAS; Epley and Brzycki for 1RM estimation). **`[New in v0.4]`** The MAS training zones follow Dan Baker's field-sport conditioning framework (*Recent Trends in High-Intensity Aerobic Training for Field Sports*, UKSCA/ASCA), and the EWMA load trend follows the training-load smoothing approach of Williams et al. (2017) and Murray et al. (2017). See the in-app **Guide → References & Methodology** section for detail.

*This app is an informational and monitoring tool. It is not medical advice and makes no diagnostic or injury-prediction claims. Consult a qualified professional for individual guidance.*

## Third-party components

- [Chart.js](https://www.chartjs.org/) — charting, used under the MIT License (its copyright notice is retained).

## License

**Copyright © 2026 Ibrahim Bin Nasaruddin. All rights reserved.**

This source is published for viewing and evaluation only. No permission is granted to use, copy, modify, distribute, or create derivative works from this code, in whole or in part, without the express written consent of the copyright holder.

Embedded third-party components retain their own licenses (see above).

---

*Built as an independent project. Not affiliated with the ASCA, NSCA, or any other organisation referenced.*
