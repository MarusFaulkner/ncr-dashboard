# NCR Dashboard

> **Nonconformance Report Tracker** — a browser-based quality management tool designed with ISO 9001:2015 concepts in mind.

## 🌐 Live Application

**[Launch the NCR Dashboard](https://MarusFaulkner.github.io/ncr-dashboard/)**

[![Live Demo](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-blue?style=flat-square)](https://MarusFaulkner.github.io/ncr-dashboard)
[![HTML](https://img.shields.io/badge/Built%20With-HTML%20%2F%20JS-orange?style=flat-square)](https://github.com/MarusFaulkner/ncr-dashboard)
[![Chart.js](https://img.shields.io/badge/Charts-Chart.js%204.4-pink?style=flat-square)](https://www.chartjs.org/)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

---

## About

This project demonstrates how quality management workflow concepts can be implemented as a lightweight, interactive web application — no backend, no database, no dependencies beyond a single CDN script.

It was built as a portfolio project by a **Quality Inspector in power transformer manufacturing**, drawing on hands-on experience with ISO 9001:2015 nonconformance reporting, in-process inspection, and corrective action documentation.

The application is intentionally self-contained. Data persists in the browser's `localStorage`, making it suitable for a demo or personal tracking environment without requiring a server.

---

## Features

### Dashboard KPIs
| Card | What it tracks |
|---|---|
| Total NCRs | All records in the system |
| Open | NCRs awaiting action |
| In Progress | Active investigation / rework |
| Closed | Resolved and documented |
| Overdue | Open NCRs exceeding 30 days |
| Critical Open | Severity = Critical and not yet closed — **pulses red when > 0** |

### Charts
- **Status Donut** — live breakdown of Open / In Progress / Closed
- **Monthly Severity Trend** — stacked bar chart, trailing 6 months, auto-advances with the current date

### NCR Table
- Sortable columns (click any header)
- Expandable rows — reveals full Nonconformance Detail, Acceptance Criteria, Root Cause, and Photo Reference
- **Days Open with 4-tier visual system:**
  - `0–7 days` → gray (normal)
  - `8–14 days` → amber (attention)
  - `15–30 days` → orange (aging)
  - `30+ days` → red bold (overdue)

### Filtering
- Full-text search across NCR #, Sales Order, Component, Description, Acceptance Criteria
- Filter by Status, Severity, Disposition, and Assigned To (dynamically populated)

### NCR Form — 4 structured sections
| Section | Fields |
|---|---|
| **1 — Identification** | Sales Order, Component, Drawing / Spec Number, Date Found |
| **2 — Nonconformance Detail** | What Was Found, Acceptance Criteria, Photo Reference (Z Drive path) |
| **3 — Classification** | Severity (Minor / Major / Critical), Disposition, Status |
| **4 — Root Cause & Assignment** | Root Cause (3-category framework), Assigned To |

### Disposition Tracking
`Pending` · `Accept As-Is` · `Rework` · `Scrap` · `Return to Vendor` · `Use As-Is with Deviation`

### Export
- **CSV export** — 15 columns including all NCR fields, filtered to current view, filename stamped with today's date

---

## Tech Stack

| Layer | Choice | Why |
|---|---|---|
| UI | Vanilla HTML / CSS / JS | Zero build step, deploys as a single file |
| Charts | [Chart.js 4.4.1](https://www.chartjs.org/) via cdnjs | Lightweight, well-supported |
| Persistence | Browser `localStorage` | No server required for portfolio/demo use |
| Hosting | GitHub Pages | Free, instant, shareable URL |

---

## Quality Concepts Demonstrated

This project reflects real QMS workflow knowledge:

- **Acceptance Criteria** are stored separately from the nonconformance finding — a critical distinction in ISO 9001 documentation (criteria = what the drawing says; finding = what was actually observed)
- **Photo Reference** field stores Z drive file paths, matching how photo evidence is organized in a manufacturing QMS
- **Root Cause** field guides the user toward the three error categories (Thinking / Action / Risk-based) rather than accepting "human error" as a root cause
- **Disposition** options match standard NCR disposition workflow
- **Days Open** aging tiers reflect the urgency escalation logic used in real corrective action management

---

## Getting Started

### Option 1 — Open locally
```
Download index.html → open in any modern browser
```
No installation required.

### Option 2 — Deploy to GitHub Pages
```bash
# 1. Create a new GitHub repository named: ncr-dashboard
# 2. Upload index.html to the main branch
# 3. Go to Settings → Pages → Deploy from branch → main → / (root)
# 4. Your dashboard is live at:
https://<your-username>.github.io/ncr-dashboard
```

### Option 3 — Clone and run
```bash
git clone https://github.com/MarusFaulkner/ncr-dashboard.git
cd ncr-dashboard
open index.html
```

---

## Sample Data

The dashboard loads 10 pre-built NCRs based on realistic power transformer manufacturing scenarios, including:

- Paint damage on bushings (Minor / Rework / Closed)
- Missing radiator unit from packing list (Major / Open)
- Failed conservator pressure test (Critical / Closed)
- Missing mounting hardware / M12 bolts (Major / In Progress)
- Stud bolt length out of tolerance (Minor / Scrap / Closed)
- Loose U-bolt torque on gas pipe (Major / In Progress)
- Missing traceability tag (Minor / Accept As-Is / Closed)
- Winding insulation discoloration (Critical / Open)
- Surface rust on arrester support (Minor / Rework / Closed)
- Gasket set quantity shortage (Major / Open)

Use **Reset Sample Data** to restore these at any time.

---

## Roadmap (not planned — documenting for context)

This project is intentionally scoped as a portfolio demo. The following are **out of scope by design**:

- User authentication / multi-user access
- CAPA (Corrective and Preventive Action) workflow
- Electronic signatures or approval chains
- Audit trail / change history
- Supplier management
- Document control
- Training records

A production QMS would use dedicated software (ETQ, MasterControl, Greenlight Guru, etc.). This project demonstrates **quality knowledge + workflow design + data visualization + front-end development** — not a replacement for an enterprise eQMS.

---

## Author

**Marcus Faulkner** — Quality Inspector, Power Transformer Manufacturing  
ISO 9001:2015 · ISO 13485 · Manufacturing QA · Medical Device Background

[github.com/MarusFaulkner](https://github.com/MarusFaulkner)

---

*This is a portfolio/demo application. Data is stored in the browser's localStorage and is not shared or transmitted.*
