# IT Infrastructure Dashboard

A single-file, zero-dependency web dashboard for monitoring IT infrastructure — hosts, alerts, bandwidth, and hardware inventory — built with vanilla HTML, CSS, and JavaScript.

Designed to demonstrate practical front-end and IT operations skills: real-time UI, data visualisation with Chart.js, responsive layout, and a professional dark-mode design suitable for an IT NOC or operations team.

**[Live demo →](https://peterkamau-dev.github.io/it-dashboard)**

---

## Screenshot

> A dark-mode operations dashboard showing host status, CPU/memory trends, active alerts, bandwidth usage, and hardware inventory across five navigation sections.

---

## Features

- **Overview** — KPI cards (hosts up, availability %, open alerts, avg CPU) with live clock and animated status indicator
- **Hosts** — full host table with per-host CPU/memory bar charts and colour-coded status pills
- **Alerts** — prioritised alert feed (critical / warning / info) with remediation guidance
- **Bandwidth** — daily traffic bar chart (inbound/outbound), top talker breakdown, protocol analysis
- **Inventory** — hardware asset register with asset tags, assigned users, locations, and audit dates

---

## Quick start

No build tools or dependencies required.

```bash
# Clone
git clone https://github.com/peterkamau-dev/it-dashboard.git
cd it-dashboard

# Open directly in browser
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

Or serve locally:

```bash
# Python 3
python3 -m http.server 8080
# then open http://localhost:8080
```

---

## Deploying to GitHub Pages

1. Go to your repository **Settings → Pages**
2. Set source to **main branch / root**
3. Your dashboard will be live at `https://<your-username>.github.io/it-dashboard`

---

## Customising the data

All host, alert, and inventory data is defined in plain JavaScript arrays near the top of `index.html`. To point it at real data, replace the static arrays with `fetch()` calls to your monitoring API or backend:

```javascript
// Replace static data with a live API call
async function loadHosts() {
  const res  = await fetch('/api/hosts');
  const data = await res.json();
  renderHosts(data);
}
```

---

## Tech stack

HTML · CSS · JavaScript · [Chart.js 4.4](https://www.chartjs.org/) (CDN)

No frameworks, no build step, no dependencies to install.

---

## Project structure

```
it-dashboard/
├── index.html    # Complete dashboard — HTML + CSS + JS in one file
└── README.md
```

---

## Roadmap

- [ ] Connect to a real REST API backend (Node.js / Python Flask)
- [ ] Add WebSocket support for live host status updates
- [ ] Export reports to CSV / PDF
- [ ] Add user authentication for multi-user access

---

## Author

Peter Griffin — [linkedin.com/in/peter-kamau-ba35b0175](https://linkedin.com/in/peter-kamau-ba35b0175) · [peterkamau.dev](https://peterkamau.dev)
