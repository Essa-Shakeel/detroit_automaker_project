## 1. Detroit Automaker Capital Allocation Analysis | GM vs. Ford vs. Stellantis (FY2016–FY2025)

### Resume bullets

- **Engineered an end-to-end Python data pipeline** that parsed 62 annual filings (10-K and 20-F) and ~160K tagged data points, including segment-level facts most free data sources omit. Resolved changing segment labels, custom company tags, and the 2021 FCA–PSA merger break.
- **Adjusted for captive finance distortion** by separating GM Financial and Ford Credit (84–91% of parent debt) using their standalone filings. The adjustment showed both automotive businesses held net cash every year and reframed Ford's underperformance as a returns problem, not a leverage problem.
- **Validated every figure back to source documents,** achieving a 21/21 match on spot-checks against the filing text. Built a full audit trail and logged all restatements, data gaps and tagging inconsistencies.
- **Delivered a formula-driven Excel model** (1,898 formulas, zero mismatches against the Python output) with sensitivity analysis across tax rates, capital definitions and time windows, plus publication-ready charts and a findings report.

### Short description (under 500 characters)

10-year capital allocation analysis of GM, Ford and Stellantis built from SEC EDGAR XBRL filings. Engineered a Python pipeline parsing 62 filings and ~160K data points; separated captive finance arms (84–91% of parent debt) to measure true automotive ROIC. Validated 21/21 figures against source filings and built a 1,898-formula Excel model with sensitivity analysis. Found GM led (13.9% ROIC vs. Stellantis 11.0%, Ford −2.6%) despite returns falling every year.

### Long description (about 2,000 characters)

Ten-year capital allocation study of GM, Ford and Stellantis (FY2016–FY2025), built end to end from primary SEC filings to answer one question: which Detroit automaker allocates capital best?

**Data engineering:** Designed a reproducible Python pipeline that pulls 10-K and 20-F filings from the SEC EDGAR API, parses 62 XBRL filings (~160K tagged facts, including segment-level data most free sources omit) and maps them into a standardized financial dataset. Resolved real-world data issues, including renamed segment tags, custom company taxonomies, restatements and the 2021 FCA–PSA merger break.

**Financial analysis:** Modeled revenue growth, gross/operating/net margins, free cash flow, ROIC, leverage and shareholder payouts across US GAAP and IFRS filers, with EUR converted using Federal Reserve (FRED) exchange-rate data. Separated the captive finance arms GM Financial and Ford Credit (84–91% of parent debt) to isolate true automotive returns, showing both car businesses held net cash every year.

**Validation:** Traced every figure to its source filing and verified 21/21 spot-checks against the filing text. Logged all restatements, gaps and tagging inconsistencies for full auditability.

**Deliverables:** Built a formula-driven Excel model (1,898 formulas, zero mismatches against the Python output) with sensitivity analysis across tax rates, capital definitions and time windows, plus publication-ready charts and a written findings report.

**Key finding:** GM led with a 13.9% capital-weighted ROIC vs. 11.0% for Stellantis and −2.6% for Ford, yet its returns declined in every year of the decade.

**Skills:** Python (pandas, NumPy, lxml, matplotlib, openpyxl) · SEC EDGAR / XBRL · Financial Statement Analysis · ROIC & FCF Modeling · US GAAP & IFRS · Data Engineering · Data Validation · Excel Financial Modeling · Data Visualization · Technical Writing
