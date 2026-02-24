# LeaseIQ — India's Lease Intelligence Platform

> **Know exactly what your lease deposit is costing you — before you sign.**

LeaseIQ is a comprehensive, client-side lease vs rent decision engine built specifically for India's property market. It goes far beyond simple EMI calculators by modelling opportunity costs, stress-testing 9 market scenarios, computing early-exit positions, and integrating qualitative factors into a single, clear verdict.

**→ [Live Demo](https://your-username.github.io/leaseiq/)**

---

## What makes LeaseIQ different

Most lease calculators compare your EMI to market rent and stop there. LeaseIQ exposes everything the receipt doesn't show:

| Feature | LeaseIQ | Typical Calculator |
|---|---|---|
| Hidden opportunity cost on locked capital | ✅ Separated explicitly | ❌ Ignored |
| 9-scenario stress test matrix | ✅ | ❌ |
| Early exit net position at every month | ✅ | ❌ |
| Breakeven thresholds (rent, rate, growth) | ✅ 3 computed | ❌ |
| Liquidity risk assessment | ✅ | ❌ |
| Qualitative checklist scoring | ✅ 6 factors | ❌ |
| Payback period on own funds locked | ✅ | ❌ |
| Cash costs vs opportunity costs separated | ✅ Visually distinct | ❌ Mixed |

---

## Features

### Financial Intelligence
- **17+ input variables** — deposit, loan, rate, maintenance, withholding, refund delay, rent deposit, rent growth, opportunity cost, liquidity premium, volatility, risk premium, inflation, flexibility
- **Payback period** — how many months of savings to recover locked own-funds
- **3 breakeven thresholds** — the exact rent level, loan rate, and rent growth rate where the decision flips
- **9-scenario matrix** — 3 rent levels × 3 growth rates, colour-coded verdict per cell

### Risk Modelling
- **Early Exit Analysis** — drag-slider simulation of exiting at any month; net position vs renting at every point in the lease
- **Liquidity Risk** — own funds locked expressed as months of rent (not abstract percentages)
- **Decision Confidence** — margin-based confidence score with plain-English interpretation

### Visualisation
- **6 interactive charts** — cost breakdown, monthly comparison, cumulative 3-line (cash/economic/rent), rent growth vs fixed lease, sensitivity tornado, amortisation schedule
- **Cash vs Opportunity cost** — TCO bar chart visually separates real outflows from foregone returns
- **3-line cumulative chart** — lease cash outflows, full economic cost, rent — so you compare like with like

### Decision Quality
- **Exit Likelihood buttons** — replace an impossible ₹/month input with guided Low/Possible/Likely options
- **Qualitative Checklist** — landlord reliability, renovation rights, stability, income certainty, liquidity buffer, location scarcity — scored and explained
- **Plain-English Verdict Dial** — STRONG LEASE / LEASE AHEAD / LEASE EDGE / RENT EDGE / RENT WINS

### UX
- 4 real India presets — Metro Apartment (Bengaluru), High-Street Retail, Grade-B Office, Warehouse
- Shareable URL state — share any scenario via link
- Dark / Light mode
- Keyboard shortcuts (R = reset, ? = help)
- Fully accessible (ARIA, keyboard navigation, reduced-motion)
- 100% client-side — no server, no tracking, no cookies, no signup

---

## Screenshots

*Coming soon*

---

## Quick Start

### Option 1: GitHub Pages (Recommended)

1. Fork this repository
2. Go to **Settings → Pages**
3. Set source to **main branch / root**
4. Visit `https://your-username.github.io/leaseiq/`

### Option 2: Local

```bash
git clone https://github.com/your-username/leaseiq.git
cd leaseiq
# Open index.html in any browser — no build step required
open index.html
```

### Option 3: Any Static Host

Upload `index.html` to Vercel, Netlify, Cloudflare Pages, or any static host. The entire tool is a single file with no dependencies to install.

---

## How It Works

LeaseIQ computes a **risk-adjusted economic lease cost** that includes:

```
Total Lease Cost = EMI payments
                 + Own funds opportunity cost  (capital locked × rate × tenure)
                 + Withholding loss            (deposit × withholding %)
                 + Refund delay cost           (deposit × rate × delay months)
                 + Maintenance                 (monthly × tenure)
                 + Net lease risk premium      (deposit × risk %)
```

This is then compared to an **adjusted rent cost**:

```
Total Rent Cost = Sum of monthly rents (with annual escalation)
               + Rent deposit opportunity cost
               − Flexibility premium          (exit likelihood × market rent)
```

The monthly savings = (Total Rent Cost − Total Lease Cost) / Tenure

**Opportunity costs are always separated from cash costs** — both in the charts and in the monthly comparison — so you can reason about each independently.

---

## The 9-Scenario Matrix

LeaseIQ stress-tests your decision across 9 combinations:

|               | Rent −15%     | Rent Base     | Rent +15%     |
|---|---|---|---|
| **Growth −3pp** | Worst case    | Pessimistic   | Neutral       |
| **Growth Base** | Pessimistic   | **Your case** | Optimistic    |
| **Growth +3pp** | Neutral       | Optimistic    | Best case     |

Each cell shows monthly savings and a colour-coded verdict (Lease wins / Rent wins / Toss-up).

---

## Technical

- **Zero dependencies** to install — Chart.js and ChartDataLabels loaded from CDN
- **Single file** — all HTML, CSS, and JS in `index.html`
- **No build pipeline** — edit and deploy directly
- **~3,900 lines** of well-commented code
- Tested on Chrome, Firefox, Safari, Edge

### Key Algorithms
- EMI formula: standard reducing-balance
- Opportunity cost: compound growth `P × ((1+r)^n − 1)`
- Payback period: own funds ÷ monthly savings
- Breakeven thresholds: 60-iteration binary search
- Early exit net position: month-by-month loan amortisation + cumulative rent comparison

---

## Contributing

PRs welcome. Particularly interested in:
- Additional India-specific presets
- Rental deposit tax implications (TDS on lease deposits)
- Inflation-adjusted real returns
- Export to PDF / Excel

---

## Licence

MIT — use freely, credit appreciated.

---

*LeaseIQ is independent. It is not affiliated with any bank, broker, or property platform. No data you enter is ever transmitted.*
