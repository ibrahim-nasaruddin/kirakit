# kirakit

A privacy-first training monitor for strength, conditioning, and hybrid athletes. Log sessions, track training load and readiness over time, and run sports-science calculators — all in a single offline-capable web app, with your data stored only on your own device.

> **Status:** Early prototype, in active validation. Built as a focused tool for athletes and coaches who want load monitoring grounded in sports-science methodology rather than raw rep-counting.

## What it does

- **Granular session logging** — strength sessions with a searchable exercise library (filterable by movement pattern, with favourites and recents), sets/reps/load, and automatic tonnage; conditioning sessions classified by energy system and modality.
- **Training-load monitoring** — every session reduces to a common internal load (duration × RPE / sessionRPE method), so strength and conditioning are directly comparable. Tracks load trend against your *own* rolling baseline, plus monotony, strain, and individualised z-scores.
- **Readiness & wellness** — daily word-anchored check-ins that sharpen the load signals.
- **Testing** — log and trend field tests (CMJ, sprints, change-of-direction, and more), with an estimated-1RM lift-progression chart and protocol references.
- **Calculators** — pace/speed converter (solve for speed, distance, or time), Anaerobic Speed Reserve, and Karvonen heart-rate zones.
- **Interactive load chart** — view 7 days to 1 year, scroll back through history, with per-point detail.
- **Themes** — light/dark mode and a custom accent colour.

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

Conditioning definitions, energy-system framework, and testing protocols draw on the ASCA Level 1 framework and peer-reviewed sources, with calculator formulas referenced to published literature (e.g. Karvonen for heart-rate reserve; Sandford/Buchheit for Anaerobic Speed Reserve). See the in-app **References & Methodology** section for detail.

*This app is an informational and monitoring tool. It is not medical advice and makes no diagnostic or injury-prediction claims. Consult a qualified professional for individual guidance.*

## Third-party components

- [Chart.js](https://www.chartjs.org/) — charting, used under the MIT License (its copyright notice is retained).

## License

**Copyright © 2026 [Ibrahim Bin Nasaruddin]. All rights reserved.**

This source is published for viewing and evaluation only. No permission is granted to use, copy, modify, distribute, or create derivative works from this code, in whole or in part, without the express written consent of the copyright holder.

Embedded third-party components retain their own licenses (see above).

---

*Built as an independent project. Not affiliated with the ASCA, NSCA, or any other organisation referenced.*
