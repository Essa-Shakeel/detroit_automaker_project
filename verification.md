# Verification log

Spot checks of pipeline values against the text of the filings themselves (primary 10-K / 20-F document, not the XBRL tags). **21 of 21 match.**

Method: `src/verify.py` downloads each filing's primary document, finds the line label, and compares the figures printed right after it with the value the pipeline extracted from XBRL. Values are in millions of the filing currency; parentheses in filings denote outflows, so signs are compared in absolute terms. Re-run with `python src/verify.py`.

| # | Company | FY | Line item | Pipeline value | Value in filing | Match | Filing checked | Excerpt from filing |
|---|---|---|---|---|---|---|---|---|
| 1 | GM | 2025 | revenue | $185,019m | $185,019m | yes | [10-K 0001467858-26-000013](https://www.sec.gov/Archives/edgar/data/1467858/000146785826000013/gm-20251231.htm) | "Total net sales and revenue / $ / 185,019 / $ / 187,442 / $ / (2,422) / (1.3) / % / $ / (7.9) / $ / 2.5 / $ / 1.9 / $ / 1.2 / Refer to th…" |
| 2 | GM | 2025 | ocf | $26,867m | $26,867m | yes | [10-K 0001467858-26-000013](https://www.sec.gov/Archives/edgar/data/1467858/000146785826000013/gm-20251231.htm) | "Net cash provided by (used in) operating activities / 26,867 / 20,129 / 20,930 / Cash flows from investing activities / Expenditures for property / ( …" |
| 3 | GM | 2023 | buybacks | $11,115m | ($11,115m) | yes | [10-K 0001467858-24-000031](https://www.sec.gov/Archives/edgar/data/1467858/000146785824000031/gm-20231231.htm) | "Purchase of common stock (Note 20) / ( 2 ) / ( 7,686 ) / ( 3,426 ) / — / — / ( 11,115 ) / — / Stock based compensation / — / 259 / ( 6…" |
| 4 | GM | 2016 | revenue | $149,184m | $149,184m | yes | [10-K 0001467858-18-000022](https://www.sec.gov/Archives/edgar/data/1467858/000146785818000022/gm201710k.htm) | "Total net sales and revenue / $ / 145,588 / $ / 149,184 / $ / 135,725 / $ / 137,958 / $ / 138,792 / Income from continuing operations(a)(…" |
| 5 | GM | 2020 | dividends | $545m | ($545m) | yes | [10-K 0001467858-21-000037](https://www.sec.gov/Archives/edgar/data/1467858/000146785821000037/gm-20201231.htm) | "Cash dividends paid on common stock / — / — / ( 545 ) / — / — / ( 545 ) / Dividends to noncontrolling interests / — / — / — / — / ( 46 ) / ( 46 )…" |
| 6 | GMF | 2024 | debt_total | $114,264m | $114,264m | yes | [10-K 0000804269-25-000007](https://www.sec.gov/Archives/edgar/data/804269/000080426925000007/acf-20241231.htm) | "Total secured and unsecured debt / $ / 114,264 / $ / 115,010 / $ / 105,327 / $ / 104,622 / Fair value utilizing Level 2 inputs / $ / 112,941 /…" |
| 7 | Ford | 2025 | revenue | $187,267m | $187,267m | yes | [10-K 0000037996-26-000015](https://www.sec.gov/Archives/edgar/data/37996/000003799626000015/f-20251231.htm) | "Total revenues (Note 4) / 176,191 / 184,992 / 187,267 / Costs and expenses / Cost of sales (Note 13) / 150,550 / 158,434 / 1…" |
| 8 | Ford | 2016 | ocf | $19,850m | $19,792m | yes | [10-K 0000037996-17-000013](https://www.sec.gov/Archives/edgar/data/37996/000003799617000013/f1231201610-k.htm) | "Net cash provided by/(used in) operating activities / 11,045 / $ / 8,754 / $ / (7 / ) / $ / 19,792 / Reconciling Adjustments to Automotive Segment Ope…" *Filing shows the as-first-reported value; pipeline uses the restated 19,850 from 0000037996-19-000012.* |
| 9 | Ford | 2023 | dividends | $4,995m | ($4,995m) | yes | [10-K 0000037996-24-000009](https://www.sec.gov/Archives/edgar/data/37996/000003799624000009/f-20231231.htm) | "Cash payments for dividends and dividend equivalents / $ / (4,995) / $ / — / $ / — / $ / (4,995) / Purchases of common stock / (335) / — / — / (335) /…" |
| 10 | Ford | 2022 | net_income | ($1,981m) | ($1,981m) | yes | [10-K 0000037996-23-000012](https://www.sec.gov/Archives/edgar/data/37996/000003799623000012/f-20221231.htm) | "Net income/(loss) attributable to Ford Motor Company / $ / (4,190) / $ / 2,209 / $ / (1,981) / __________ / (a) Ford Credit excludes a specials charge…" |
| 11 | Ford | 2024 | capex | $8,684m | ($8,684m) | yes | [10-K 0000037996-25-000013](https://www.sec.gov/Archives/edgar/data/37996/000003799625000013/f-20241231.htm) | "Capital spending / $ / (8,590) / $ / (94) / $ / — / $ / (8,684) / Acquisitions of finance receivables and operating leases / —…" |
| 12 | FMCC | 2024 | equity_total | $13,757m | $13,757m | yes | [10-K 0000038009-25-000007](https://www.sec.gov/Archives/edgar/data/38009/000003800925000007/fmcc-20241231.htm) | "Total shareholder’s interest / 13,389 / 13,757 / Total liabilities and shareholder’s interest / $ / 149,205 / $ / 158,292 / The following …" |
| 13 | Stellantis | 2018 | capex | €5,392m | €5,392m | yes | [20-F 0001605484-19-000014](https://www.sec.gov/Archives/edgar/data/1605484/000160548419000014/fca20181231annualreport.htm) | "Investments in property, plant and equipment and intangible assets / (5,392 / ) / (8,105 / ) / (8,241 / ) / Investments in joint ventures, associates …" |
| 14 | Stellantis | 2020 | revenue | €86,676m | €86,676m | yes | [20-F 0001605484-21-000032](https://www.sec.gov/Archives/edgar/data/1605484/000160548421000032/stellantis-20201231.htm) | "Net revenues / € / 86,676 / € / 108,187 / € / 110,412 / € / 105,730 / € / 105,798 / Profit before taxes / € / 1,356 / € / …" |
| 15 | Stellantis | 2025 | revenue | €153,508m | €153,508m | yes | [20-F 0001605484-26-000021](https://www.sec.gov/Archives/edgar/data/1605484/000160548426000021/stellantis-20251231.htm) | "Net revenues / 153,508 / 156,878 / Cost of revenues / 155,627 / 136,360 / Selling, general and other costs / 8,967 / 9,299…" |
| 16 | Stellantis | 2024 | buybacks | €3,000m | (€3,000m) | yes | [20-F 0001605484-26-000021](https://www.sec.gov/Archives/edgar/data/1605484/000160548426000021/stellantis-20251231.htm) | "(Purchases)/sales of treasury shares / — / ( 3,000 ) / ( 2,434 ) / Changes in short-term debt and other financial assets and liabilities / 31 / 45…" |
| 17 | Stellantis | 2023 | ocf | €22,485m | €22,485m | yes | [20-F 0001605484-24-000022](https://www.sec.gov/Archives/edgar/data/1605484/000160548424000022/stellantis-20231231.htm) | "Cash flows from/(used in) operating activities / € 22,485 / € 19,959 / Less: Cash flows from operating activities - discontinued operations / — / — / …" |
| 18 | Stellantis | 2025 | net_income | (€22,368m) | (€22,368m) | yes | [20-F 0001605484-26-000021](https://www.sec.gov/Archives/edgar/data/1605484/000160548426000021/stellantis-20251231.htm) | "Owners of the parent / (22,368) / 5,473 / Non-controlling interests / 36 / 47 / Net revenues / Years ended December 31, / Increase…" |
| 19 | Stellantis | 2016 | revenue | €105,798m | €105,798m | yes | [20-F 0001605484-19-000014](https://www.sec.gov/Archives/edgar/data/1605484/000160548419000014/fca20181231annualreport.htm) | "Net revenues / € / 110,412 / € / 105,730 / € / 105,798 / € / 105,859 / € / 89,350 / Profit before taxes / € / 4,108 / € / …" |
| 20 | GM | 2024 | LongTermDebtAndCapitalLeaseObligations (gm:Automotive) | $13,327m | $13,327m | yes | [10-K 0001467858-25-000032](https://www.sec.gov/Archives/edgar/data/1467858/000146785825000032/gm-20241231.htm) | "Long-term debt (Note 13) / Automotive / 13,327 / 15,985 / GM Financial (Note 11) / 76,973 / 66,788 / Postretirement benefits other than pensions (N…" |
| 21 | Ford | 2024 | LongTermDebtNoncurrent (f:CompanyExcludingFordCredit) | $18,898m | $18,898m | yes | [10-K 0000037996-25-000013](https://www.sec.gov/Archives/edgar/data/37996/000003799625000013/f-20241231.htm) | "Long-term debt (Note 18) / Company excluding Ford Credit / 19,467 / 18,898 / Ford Credit / 80,095 / 84,675 / Deferred income taxes (Note 7) / 1,005 / …" |

## Data issues flagged by the pipeline

Full list with details: `data/data_issues.csv`. Nothing was silently filled: every zero-fill, fallback and restatement below is recorded there with the filings involved.

| Type | Count |
|---|---|
| restatement | 59 |
| tag fallback | 49 |
| zero-fill | 9 |
| missing | 3 |
| one-off | 3 |
| tag inconsistency | 3 |
| basis override | 2 |
| structural break | 2 |
| tag conflict | 1 |
| missing XBRL | 1 |
| reclassification | 1 |
| no segment split | 1 |
| tag change | 1 |
| segment profit tags | 1 |
| derived | 1 |
| tag gaps | 1 |

### Structural breaks, tag inconsistencies and one-offs

- **Stellantis 2024 — tag conflict.** ifrs-full:IncomeTaxExpenseContinuingOperations tagged with several values (-1,500, -1,488m) in 0001605484-26-000021; first value used.
- **Stellantis 2016-2020 — structural break.** FY2016-FY2020 are FCA N.V. (predecessor). Stellantis (FCA+PSA) exists from 16-Jan-2021. PSA was the accounting acquirer, so Stellantis 20-Fs restate FY2019-FY2020 with PSA figures; those comparatives are excluded and FY2016-2020 come only from FCA-era 20-Fs.
- **Stellantis 2021 — structural break.** FY2021 includes FCA from 17-Jan-2021 only (merger date) and PSA for the full year; revenue growth FY2021 vs FY2020 compares Stellantis with FCA alone and is not meaningful. FY2021 ROIC uses year-end invested capital, because the opening balance (FCA only) excludes PSA.
- **Stellantis 2016 — missing XBRL.** FCA FY2015-FY2016 20-Fs have no XBRL (SEC accepted IFRS XBRL only from 2017). FY2016 values are the comparatives in the FY2017/FY2018 20-Fs. FY2015 balance sheet is unavailable, so FY2016 ROIC uses year-end (not average) invested capital.
- **Stellantis 2023-2025 — reclassification.** The FY2025 20-F reclassified the cash-flow statement (financial-services receivables and other items moved into operating activities) and restated FY2023 OCF from EUR 22,485m to 17,954m and FY2024 from 4,008m to 1,535m. FY2016-2024 OCF is kept on the original basis for consistency; FY2025 is only available on the new basis, which lowers OCF relative to prior years.
- **Stellantis all — no segment split.** Stellantis does not tag an industrial vs financial-services split of debt or equity in XBRL; consolidated figures are used. Its European captive financing is via equity-accounted JVs, so consolidated debt is much closer to industrial debt than at GM or Ford.
- **Stellantis 2019 — one-off.** FY2019 dividends include a EUR 2,038m extraordinary dividend from the Magneti Marelli sale; FY2019 net income includes EUR 3,930m profit from discontinued operations.
- **Stellantis 2021 — one-off.** FY2021 dividends include the EUR 2.9bn extraordinary distribution to former FCA shareholders agreed in the merger.
- **GM 2023-2024 — tag inconsistency.** In its FY2025 10-K GM tags pre-tax income for FY2023-24 under the "before equity-method income" concept with values that include equity income (FY2024: 8,519 vs 13,194 in the FY2024 10-K). Pre-tax income here uses the concept that includes equity income, which is consistent across years.
- **GM 2022-2025 — tag change.** From FY2022 GM tags cost of sales and SG&A only with a BusinessGroup=Automotive dimension (previously undimensioned); handled as an alternative mapping.
- **GM all — segment profit tags.** GM tags its segment profit measure with three different custom concept names over the period (IncomeLossBeforeAutomotiveInterestAndIncomeTaxesAdjusted, Earningslossbefore..., EarningsLossBefore...).
- **Ford all — tag inconsistency.** Ford renamed the segment members used for its balance-sheet debt/cash split four times (Automotive sector; AutomotiveSegment/FinancialServicesSegment; AutomotiveSegment/FordCredit; CompanyExcludingFordCredit/FordCredit) and changed the consolidation-axis prefix; all variants mapped.
- **Ford 2018-2020 — tag inconsistency.** Ford FY2019-FY2020 10-Ks contain an undimensioned DebtAndCapitalLeaseObligations fact of ~600m that is actually Mobility-segment debt; undimensioned debt totals are therefore not used for Ford.
- **Ford 2015-2016 — derived.** Ford reported no operating-income subtotal before its FY2019 10-K; FY2015-16 operating income is revenues minus total costs and expenses (this reproduces the later-reported FY2017 figure exactly).
- **Ford 2016-2025 — tag gaps.** Ford tags NetIncomeLoss in only some years; NetIncomeLossAvailableToCommonStockholdersBasic is used (identical, Ford has no preferred stock). FY2025 revenue is tagged only as RevenueFromContractWithCustomer.
- **Ford 2022-2025 — one-off.** Ford non-operating results include Rivian mark-to-market gains/losses (FY2021 +$9.1bn pre-tax, FY2022 -$7.4bn); these sit below operating income and are excluded from NOPAT.

### Zero-filled and missing values

- GM FY2021 `dividends` (zero-fill): GM paid no common dividend in FY2021 (suspended Apr-2020, resumed Q3-2022); no fact tagged.
- Stellantis FY2015 `buybacks` (zero-fill): FCA made no share repurchases; cash-flow statement has no treasury-share line.
- Stellantis FY2016 `buybacks` (zero-fill): FCA made no share repurchases; cash-flow statement has no treasury-share line.
- Stellantis FY2017 `buybacks` (zero-fill): FCA made no share repurchases; cash-flow statement has no treasury-share line.
- Stellantis FY2018 `buybacks` (zero-fill): FCA made no share repurchases; cash-flow statement has no treasury-share line.
- Stellantis FY2019 `buybacks` (zero-fill): FCA made no share repurchases; cash-flow statement has no treasury-share line.
- Stellantis FY2020 `buybacks` (zero-fill): FCA made no share repurchases; cash-flow statement has no treasury-share line.
- Stellantis FY2021 `buybacks` (zero-fill): No Stellantis buyback in FY2021 (program began 2022); not tagged.
- Stellantis FY2025 `buybacks` (zero-fill): FY2025 20-F cash-flow statement shows "(Purchases)/sales of treasury shares: —".
- Stellantis FY2015 `debt_total` (missing): No eligible XBRL fact found in any filing.
- Stellantis FY2015 `cash` (missing): No eligible XBRL fact found in any filing.
- Stellantis FY2015 `equity_parent` (missing): No eligible XBRL fact found in any filing.

### Largest restatements (latest filing vs. as first reported)

The pipeline uses the most recent filing of the same reporting entity for each year, so restated figures flow through. The biggest changes:

- Ford FY2016 `operating_income`: 4,116 as first reported (0000037996-17-000013) -> 5,786 in 0000037996-19-000012 (filed 2019-02-21); latest used. (41% change)
- GM FY2015 `income_tax`: -1,897 as first reported (0001467858-16-000255) -> -1,219 in 0001467858-18-000022 (filed 2018-02-06); latest used. (36% change)
- Ford FY2015 `sga`: 14,999 as first reported (0000037996-16-000092) -> 10,763 in 0000037996-18-000015 (filed 2018-02-08); latest used. (28% change)
- FMCC FY2015 `cash`: 11,609 as first reported (0000038009-16-000235) -> 8,886 in 0000038009-18-000030 (filed 2018-02-08); latest used. (23% change)
- Ford FY2017 `income_tax`: 520 as first reported (0000037996-18-000015) -> 402 in 0000037996-20-000010 (filed 2020-02-05); latest used. (23% change)
- FMCC FY2020 `net_income`: 1,924 as first reported (0000038009-21-000015) -> 2,338 in 0000038009-23-000013 (filed 2023-02-03); latest used. (22% change)
- GMF FY2015 `pretax_income`: 837 as first reported (0000804269-16-000008) -> 679 in 0000804269-18-000010 (filed 2018-02-06); latest used. (19% change)
- FMCC FY2019 `net_income`: 2,228 as first reported (0000038009-20-000009) -> 2,620 in 0000038009-22-000012 (filed 2022-02-04); latest used. (18% change)
- GMF FY2016 `pretax_income`: 913 as first reported (0000804269-17-000006) -> 762 in 0000804269-19-000008 (filed 2019-02-06); latest used. (17% change)
- FMCC FY2019 `equity_total`: 14,347 as first reported (0000038009-20-000009) -> 16,389 in 0000038009-23-000013 (filed 2023-02-03); latest used. (14% change)
- GM FY2017 `operating_income`: 10,016 as first reported (0001467858-18-000022) -> 8,661 in 0001467858-20-000028 (filed 2020-02-05); latest used. (14% change)
- GM FY2015 `capex`: 7,874 as first reported (0001467858-16-000255) -> 6,813 in 0001467858-18-000022 (filed 2018-02-06); latest used. (13% change)
- GM FY2016 `income_tax`: 2,416 as first reported (0001467858-17-000028) -> 2,739 in 0001467858-19-000033 (filed 2019-02-06); latest used. (13% change)
- GM FY2015 `operating_income`: 4,897 as first reported (0001467858-16-000255) -> 5,538 in 0001467858-18-000022 (filed 2018-02-06); latest used. (13% change)
- GMF FY2016 `debt_total`: 73,876 as first reported (0000804269-17-000006) -> 64,563 in 0000804269-18-000010 (filed 2018-02-06); latest used. (13% change)
