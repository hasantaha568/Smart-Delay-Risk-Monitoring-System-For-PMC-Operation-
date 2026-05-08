# Project Delay Risk Analysis Dashboard

**Perfect Engineers & Resources Pvt. Ltd. (PERPL)**

A single-file, client-side HTML dashboard for analyzing and predicting construction project delay risks across a 200-project PMC portfolio.

---

## Overview

This dashboard provides real-time visual analytics on project delay risk across five categories: Civil, Structural, Mechanical, Infrastructure, and Electrical. It covers FY 2024–2025 data and includes an ML-style risk predictor for new projects.

---

## Features

| Tab | Description |
|-----|-------------|
| **Overview** | KPI cards, risk distribution doughnut, delay-by-type bar chart, delay histogram, and location risk chart |
| **Analysis** | Contractor performance comparison, stacked risk breakdown by project type, and radar chart of key delay factors |
| **Projects** | Searchable, filterable, sortable table of all 200 projects with pagination |
| **Risk Predictor** | Rule-based scoring model — enter project parameters to get a predicted risk level and estimated delay |
| **Report** | Executive summary with portfolio stats, contractor rankings, location risk index, findings, and recommendations; supports CSV export and print |

---

## Key Metrics (FY 2024–2025)

- **200 total projects**
- **49% High Risk** (98 projects), **39% Medium** (78), **12% Low** (24)
- **Average delay:** 52.4 days per project
- **Average budget overrun:** 31.4%

---

## Risk Predictor — Scoring Logic

The predictor calculates a composite risk score (0–15) from nine input parameters:

| Parameter | Weight |
|-----------|--------|
| Contractor Rating < 2.5 | +3 |
| Contractor Rating 2.5–3.4 | +1 |
| Permit Delays (per delay) | +2 each (max +4) |
| Design Changes (per change) | +1.5 each (max +3) |
| Weather Issues | +2 |
| Material Shortage | +2 |
| Resources < 10 | +2 |
| Resources 10–19 | +1 |
| Site Inspections < 5 | +1 |

**Risk Thresholds:** Score ≤ 2 → Low · Score 3–5 → Medium · Score ≥ 6 → High

---

## Tech Stack

- **Vanilla HTML/CSS/JavaScript** — zero build step, zero dependencies to install
- **Chart.js 4.4.1** (via CDN) — all charts
- **Google Fonts** — Bebas Neue, DM Sans, DM Mono
- All 200 project records are embedded directly in the HTML file

---

## Usage

1. Open `dashboard.html` in any modern browser — no server required.
2. Navigate tabs to explore overview, analysis, project list, and the risk predictor.
3. Use the **Projects** tab search/filter controls to drill into specific risk levels, project types, or locations.
4. Use the **Risk Predictor** tab to assess a new project before kick-off.
5. Export the full dataset as CSV from the **Report** tab.

---

## Project Data Fields

Each of the 200 records contains:

`project_id` · `project_type` · `contractor` · `location` · `project_manager` · `planned_duration_days` · `actual_duration_days` · `delay_days` · `overrun_pct` · `no_of_resources` · `budget_allocated` · `budget_spent` · `site_inspections_done` · `weather_issues` · `contractor_rating` · `permit_delays` · `design_changes` · `material_shortage` · `delay_risk`

---

## Key Findings

- **Low contractor rating** is the #1 driver of project delays
- **Permit delays** effectively double project risk
- **Lucknow** projects average the highest delay at 64.5 days
- **Mechanical** projects carry the highest concentration of High-risk assignments
- **BuildCo** averages the longest delays among contractors (56.2 days)

## Recommendations

- Pre-qualify contractors with a rating ≥ 3.5
- Resolve all permits at least 30 days before project start
- Maintain material buffer stock for High-risk projects
- Target a minimum of 10 site inspections per project
- Assign senior project managers to all Lucknow-based sites

---

## File Structure

```
dashboard.html   ← entire application (HTML + CSS + JS + data, self-contained)
README.md        ← this file
```

---

*Generated for Perfect Engineers & Resources Pvt. Ltd. — PMC Division*
