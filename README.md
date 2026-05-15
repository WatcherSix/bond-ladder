# Bond Ladder Calculator

A single-file, client-side bond ladder design and projection tool for modeling coupon and maturity cashflows across 12-month and multi-year horizons.

## Features

- **Stage 1: Monthly Income Table** — View coupon and maturity payments month-by-month, identify gaps, drill down by source
- **Stage 2: Scenario Stress Test (Non-Prescriptive)** — Compare capital requirement sensitivity under yield shock scenarios
- **Stage 3: Data Quality Audit** — Reconcile modeled income against imported bonds, validate structure, review change history
- **Stage 4: Multi-Year Reinvestment Simulator** — Project annual coverage, reinvestment income, and carry-cash deployment over 10+ years

## Tech Stack

- **Vanilla HTML5 + JavaScript** — No frameworks or build steps
- **Client-side only** — All data stored in browser localStorage; no backend required
- **CSV & JSON import/export** — Round-trip your bond portfolio and settings
- **SVG timeline visualization** — Interactive drill-down for monthly cashflow sources
- **Responsive CSS** — Light/dark theme support, mobile-friendly grid layout

## How to Use

1. **Open** `ladder.html` in any modern browser
2. **Load or import bonds** — CSV (quantity, coupon %, maturity) or JSON snapshot
3. **Review monthly income** — Stage 1 shows gaps and coverage %
4. **Run stress tests** — Stage 2 compares conservative/base/aggressive capital scenarios
5. **Audit data quality** — Stage 3 validates totals and flags issues
6. **Simulate reinvestment** — Stage 4 projects multi-year growth with custom yields and deployment %

## Key Assumptions

- **Income model:** Monthly coupon = face × annual rate ÷ number of coupon months per year
- **Zero-coupon gain:** Realized at maturity (face − purchase cost)
- **Stage 2 scope:** Scenario stress testing only; automated purchase recommendations are intentionally disabled
- **Audit:** Consistency checks on import; does not validate against actual brokerage data
- **Simulator:** Simple monthly accrual of reinvestment income; annual cash deployment blocks

## File Structure

```
ladder.html          — Complete application (HTML + CSS + JavaScript)
README.md            — This file
```

## Development Notes

- Single-file architecture minimizes deployment friction; all logic is self-contained
- Data persists to localStorage automatically; no server-side storage needed
- Audit log tracks all user actions (imports, edits, resets, calculations)
- Coupon schedules are flexible: bonds store `couponFrequency` and `months` array for granular control

## Financial Use Disclaimer

This tool is for educational and planning purposes only and does not constitute investment, legal, or tax advice. Outputs are model-based estimates using user-provided assumptions and may not reflect actual market results. Consult a licensed financial professional before making investment decisions.

## Limitations & Future Work

- No real-time market data integration (assumes fixed yields)
- No tax optimization (treats all gains equally)
- Reinvestment assumes single fixed yield (no rate curves)
- Multi-year simulator is simplified—no bond convexity or duration modeling

## License

MIT (feel free to use, modify, and share)

---

**Questions or feedback?** Open an issue or reach out.
