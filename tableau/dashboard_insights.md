# Marketing Campaign Tableau Dashboard — Insights & Recommendations

## Business Context

A social media advertising dataset spanning 91 days (May–August 2025) across
50 campaigns, 200 ads, Facebook and Instagram platforms, and 385,786 user
events was analyzed to answer one core question:

**Where should budget move, and why?**

All findings and numbers in this file are sourced from the Tableau dashboard.
The interactive version is available on Tableau Public:
https://public.tableau.com/app/profile/mayur.patil7608/viz/MarketingCampaignAnalysis_17821297336050/TheBusinessCase

---

## Top 3 Recommendations

### 1. Reallocate budget to underfunded high-performers immediately
Campaign_27_Q3 delivers the highest CVR in the entire dataset at 8.56%
yet remains underfunded. This is the strongest reallocation case identified.
Budget should move here before any other action.

### 2. Protect Campaign_42_Summer's budget structure
At $118 cost per purchase, this is the most cost-efficient campaign in the
dataset. Do not scale it blindly — study the targeting and creative model
and replicate it across similar campaigns.

### 3. Cut or audit the 20 overfunded underperformers
Campaign_35_Launch wastes $6,512 per purchase while Campaign_42_Summer
delivers $118 on the same platform. Same reach, opposite results. The
problem is targeting and creative — not budget size.

---

## Systemic Finding — The Real Problem is Post-Click

CTR across all segments — platforms, ad types, age groups, gender — is
nearly identical, ranging only 11.72% to 12.11%.

**94.93% of clicks never convert to purchase. The problem is not reach.**

Optimization effort must focus on post-click experience, offer-audience
alignment, and conversion journey — not on improving CTR which is already
consistent across every segment analyzed.

---

## Dashboard 1 — The Business Case

**Business Question:** Where is marketing budget being lost — at reach, at
click, or at conversion — and which campaigns should receive more or less
budget?

**Visual Used:** KPI cards for headline metrics. Scatter plot (CVR vs CPP)
for the Campaign Efficiency Matrix — chosen because it simultaneously encodes
four variables (CVR, CPP, budget reallocation tier, and campaign identity)
enabling pattern recognition across all 50 campaigns in a single view. Bar
chart funnel for volume drop-off visualization at each funnel stage.

**Key Finding:** 94.93% of clicks never convert to purchase. CVR ranges from
2.5% to 8.56% across 50 campaigns — Campaign_42_Summer delivers $118 CPP
while Campaign_35_Launch wastes $6,512 on the same platform. The
differentiator is always post-click behavior, never reach.

**Recommendation:** Reallocate budget from the 20 overfunded underperforming
campaigns toward Campaign_27_Q3 (8.56% CVR, currently underfunded at low
budget) and Campaign_42_Summer (best CPP at $118 in the entire dataset).

---

## Dashboard 2 — Audience & Targeting

**Business Question:** Are we reaching the right audience, and does high CTR
actually predict purchase behavior across age groups and ad formats?

**Visual Used:** Paired bar charts (CTR vs CVR) by age group and ad type —
chosen to make the divergence between reach metrics and conversion metrics
immediately visible side by side without requiring calculation from the
reader. Audience mismatch heatmap — chosen to show actual purchase volume
across all target vs actual age group combinations simultaneously in one view.

**Key Finding:** CTR is nearly flat across all age groups (11.74%–12.11%)
but the 25-34 age group generates the most actual purchases (240) despite
being targeted less than 18-24. Stories CVR at 5.34% outperforms Image CVR
at 4.67% — ad format choice directly impacts purchase rate independent of
CTR performance.

**Recommendation:** Shift targeting priority toward the 25-34 age group and
Stories ad format to align spend with actual buyer behavior. Reduce Image ad
allocation — it consistently delivers the lowest CVR across all segments.

**Platform Performance**

| Platform  | CTR    | CVR   | Purchases |
|-----------|--------|-------|-----------|
| Facebook  | 11.76% | 5.23% | 1,280     |
| Instagram | 11.88% | 4.82% | 684       |

Instagram drives higher CTR but lower CVR. Facebook is the stronger
purchase-intent platform despite lower reach on Instagram.

**Ad Format Performance**

| Ad Type  | CTR    | CVR           |
|----------|--------|---------------|
| Stories  | 11.73% | 5.34% — Best  |
| Carousel | 11.72% | 5.13%         |
| Video    | 11.90% | 5.07%         |
| Image    | 11.88% | 4.67% — Worst |

Video drives the highest CTR but ranks third on CVR. Users engage with
video ads but do not purchase. Stories drive the strongest purchase intent
post-click. Image ads consistently underperform — lowest priority for future
budget allocation.

**Age Group Performance**

| Age Group | CTR    | CVR            |
|-----------|--------|----------------|
| 18-24     | 11.74% | 5.14%          |
| 25-34     | 11.85% | 5.09%          |
| 35-44     | 11.76% | 5.21% — Best   |
| 45-54     | 12.11% | 4.91% — Worst  |
| 55-65     | 11.87% | 5.01%          |

45-54 has the highest CTR but the worst CVR — the clearest CTR trap
in the dataset. High curiosity, low purchase intent.

**Audience Mismatch — Actual Purchasers vs Target Age Group**

| Actual \ Target | 18-24 | 25-34 | 35-44 | All |
|-----------------|-------|-------|-------|-----|
| 18-24           | 194   | 139   | 173   | 139 |
| 25-34           | 240   | 188   | 225   | 201 |
| 35-44           | 89    | 56    | 86    | 75  |
| 45-54           | 18    | 14    | 17    | 18  |
| 55-65           | 1     | 5     | 4     | 7   |

The dominant pattern: ads targeted at 18-24 are being purchased most by
25-34 actual buyers (240 purchases). Targeting assumptions do not reflect
actual buyer behavior. Audience definitions need to be rebuilt from purchase
data, not assumptions.

---

## Dashboard 3 — Trends & Lifecycle

**Business Question:** When does performance peak across the campaign period,
and what is the risk of terminating campaigns before their lifecycle
completes?

**Visual Used:** Annotated line chart for weekly purchase trend — annotations
are mandatory to prevent misreading the August data artifact as a real
decline. Heat table (campaigns × lifecycle phase) for CVR by Early/Mid/Late
phase — chosen over line charts to enable simultaneous comparison of all 50
campaigns across phases without overplotting.

**Key Finding:** Performance peaked week of June 15 at 182 purchases. Week
of May 12 recorded the strongest week-over-week spike at +44.44%. 40% of
campaigns show Late-phase CVR recovery — terminating at Mid phase forfeits
that unrealized conversion value. August 4 drop of -72.22% is a data
artifact — only 3 days of data, not a real performance decline.

**Recommendation:** Do not make campaign termination decisions based on
Mid-phase performance alone. Evaluate the full lifecycle trajectory before
cutting budget. The August data artifact must never be used as a performance
signal in any reporting or decision context.

**Weekly Trend Highlights**

| Week     | Event                                |
|----------|--------------------------------------|
| May 12   | +44.44% WoW — strongest spike        |
| June 15  | Peak — 182 purchases                 |
| June 23  | -20.22% WoW drop after peak          |
| August 4 | DATA ARTIFACT — 3 days only          |

---

## Optimal Campaign Configuration

Based on CVR analysis across all dimensions in the Tableau dashboard:

- **Platform:** Facebook
- **Ad Type:** Stories
- **Age Target:** 18-24
- **Gender Target:** All (broad targeting outperforms gender-specific)

This combination consistently delivers the highest post-click conversion
across every analytical lens applied in this project.

---