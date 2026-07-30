# Chicago Healthcare Access Gap

Identifying the Chicago neighborhoods with the greatest unmet need for free/charitable
healthcare access, using public health data and clinic location analysis.

## The Question

If an organization wanted to expand free healthcare access in Chicago, which
neighborhoods should they prioritize?

## Key Finding

The 10 highest-priority community areas — led by South Lawndale, Belmont Cragin, and
Chicago Lawn — account for 31% of the city's estimated uninsured adults. These same
areas show nearly double the limited-English-proficiency rate of the citywide average
(24% vs. 14%), and 4 of the 10 sit more than 3 miles from the nearest free clinic.

## Data Sources

- **Chicago Health Atlas** — uninsured rate, chronic disease indicators, limited
  English proficiency, and population by community area (sourced from Census ACS
  2020-2024 and the Healthy Chicago Survey 2023-2024)
- **Illinois Association of Free & Charitable Clinics** — directory of 18 Chicago-based
  clinics, geocoded using geopy/Nominatim

## Methodology

Four factors were normalized (0-1 scale) and combined into a weighted priority index:

| Factor | Weight | Rationale |
|---|---|---|
| Estimated uninsured adult volume | 40% | Maximize people reached by expansion |
| Distance to nearest free clinic | 30% | Direct measure of access gap |
| Chronic disease burden (avg. diabetes, hypertension, obesity) | 20% | Urgency of need |
| Limited English proficiency | 10% | Barrier to effective care once accessed |

## Limitations

- Adult population (18-64) was estimated using a citywide ratio (62%), not
  neighborhood-specific Census age breakdowns.
- Clinic distances are straight-line, not drive/transit time.
- The clinic directory reflects one point-in-time pull and may not be exhaustive.

## Files

- `chicago_access_gap.ipynb` — full analysis notebook
- `ranked_priority_areas.csv` — final ranked output, all 77 community areas
- `chart_top10_priority.png`, `chart_scatter_access_gap.png` — key visuals
- `dashboard/` — Power BI dashboard file and screenshots

## Author

Silvia Poulakidas — www.linkedin.com/in/silvia-poulakidas — silviapoulakidas@gmail.com
