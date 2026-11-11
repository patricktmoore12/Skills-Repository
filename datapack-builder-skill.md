# Financial Data Pack Builder — User Template

## Purpose

Create a standardized, investment-committee-ready Excel data pack from source materials such as:

- Confidential information memorandums (CIMs)
- Offering memorandums
- Financial statements
- SEC filings
- Management forecasts
- Operating reports
- User-provided tables
- Public market and industry research

The workflow should extract, normalize, calculate, format, source, and validate financial and operating information in the currently open Excel workbook.

## Recommended User Prompt

> Build an IC-ready financial data pack for **[Company]** using **[source materials]**. Cover **[historical and forecast periods]** and present financial figures in **[currency and units]**. Include **[required statements, KPIs, segments, adjustments, and scenarios]**. Use formulas for all calculations, cite source pages or URLs, flag missing or inconsistent data, and do not invent unavailable information. Build the deliverable in the open Excel workbook.

## Information to Provide

- Company name and industry
- Source files or public filings
- Fiscal year-end
- Historical and forecast periods
- Currency and reporting units
- Required financial statements
- Important operating KPIs
- Segment, product, property, or geographic detail
- EBITDA normalization policy
- Required scenarios
- Existing workbook template or formatting constraints

## Standard Workbook Structure

Adapt the tabs to the company and available information:

1. **Executive Summary**
2. **Historical Financials**
3. **Balance Sheet**
4. **Cash Flow**
5. **Operating Metrics**
6. **Segment or Property Performance**
7. **Market Analysis**
8. **Investment Highlights**

Omit a tab when it is genuinely irrelevant, but document material missing inputs.

## Workflow

### 1. Review and Map Sources

- Identify the company, reporting periods, units, and fiscal year-end.
- Locate the income statement, balance sheet, cash flow statement, forecasts, and KPIs.
- Create a source map with document name, page, URL, reporting period, and relevant section.
- Flag unreadable, missing, inconsistent, or ambiguous information.

### 2. Extract Data

- Capture reported historical financials.
- Capture management projections separately from historical results.
- Extract operating metrics relevant to the industry.
- Extract segment, product, property, customer, or geographic detail.
- Capture transaction terms, investment highlights, and risks when available.

### 3. Normalize Presentation

- Standardize line-item names across periods.
- Keep reported and adjusted results clearly separated.
- Identify accounting-policy or classification changes.
- Document each proposed EBITDA adjustment.
- Do not treat recurring costs as non-recurring without support.

### 4. Build the Workbook

- Write source values as inputs.
- Use live Excel formulas for totals, subtotals, growth, margins, ratios, and reconciliations.
- Link related figures across tabs instead of duplicating calculations.
- Keep assumptions clearly identified.
- Preserve source traceability for material inputs.

### 5. Validate

- Confirm subtotals and totals.
- Test that assets equal liabilities plus equity.
- Reconcile beginning cash, cash movement, and ending cash.
- Cross-check repeated metrics across tabs.
- Check for formula errors and blank required inputs.
- Distinguish a true zero from missing information.

### 6. Summarize

The Executive Summary should concisely present:

- Business model and company overview
- Revenue and EBITDA profile
- Growth and margin trends
- Important operating KPIs
- Key investment strengths
- Material risks and diligence questions
- Transaction context, if applicable

## Formula Policy

- Hardcode only source data and explicit assumptions.
- Use formulas for every derived value.
- Guard ratios against blank or zero denominators.
- Prefer transparent formulas over deeply nested calculations.
- Maintain cross-sheet links where the same figure is used in multiple places.

Example formulas:

```excel
=SUM(B8:B12)
```

```excel
=IFERROR(B20/B8,"")
```

```excel
='Historical Financials'!B25
```

## Number Formatting

- Financial amounts: currency with units clearly labeled
- Operational counts: whole numbers without currency symbols
- Percentages and margins: percentage format
- Years: display without thousands separators
- Negative financial values: parentheses
- Ratios and multiples: consistent decimal precision

Example conventions:

- Revenue: `$125.0`
- Employees: `1,250`
- EBITDA margin: `18.5%`
- Leverage: `4.2x`
- Negative expense: `$(12.5)`

## Visual Conventions

- Use a consistent professional font.
- Distinguish source inputs, formulas, and cross-sheet links with consistent font colors.
- Use restrained section-header fills.
- Bold headers and key totals.
- Right-align numbers and left-align labels.
- Indent subordinate line items.
- Use minimal borders.
- Size columns so labels and values display fully.
- Add charts only when requested or when they materially improve the analysis.

## EBITDA Adjustment Schedule

For each adjustment, include:

| Field | Required Detail |
|---|---|
| Adjustment | Clear name |
| Period | Relevant year or quarter |
| Amount | Financial impact |
| Category | Restructuring, transaction cost, litigation, etc. |
| Rationale | Why the item may be non-recurring |
| Recurrence risk | Low, medium, or high, with explanation |
| Source | Document and page or URL |
| Treatment | Accepted, rejected, or modified |

Maintain separate views where useful:

- **Management case:** Management’s proposed definition
- **Base case:** Defensible, risk-adjusted treatment
- **Downside case:** Conservative stress assumptions

## Industry Adaptation

### Software and SaaS

- ARR and MRR
- Gross and net retention
- Churn
- Customer count
- CAC, LTV, and payback
- Rule of 40
- Sales efficiency

### Manufacturing

- Units produced
- Capacity and utilization
- Backlog
- Inventory turns
- Product-line margins

### Real Estate and Hospitality

- Properties, rooms, or square footage
- Occupancy
- ADR and RevPAR
- NOI
- Cap rates
- FF&E reserves

### Healthcare and Services

- Locations and providers
- Patients or visits
- Revenue per visit
- Payor mix
- Same-location growth

## Quality-Control Checklist

### Data

- [ ] Every material input is traceable to a source.
- [ ] No unavailable value has been replaced with zero.
- [ ] Historical results and projections are clearly distinguished.
- [ ] Normalization adjustments are documented.

### Calculations

- [ ] Totals and derived metrics use formulas.
- [ ] Balance sheet balances.
- [ ] Cash flow reconciles to cash balances.
- [ ] Cross-tab figures are consistent.
- [ ] No formula errors remain.

### Formatting

- [ ] Currency, counts, percentages, years, and ratios use appropriate formats.
- [ ] Negatives use consistent conventions.
- [ ] Labels and values display fully.
- [ ] Headers, totals, and sections have a clear hierarchy.

### Deliverable

- [ ] Tabs follow a logical sequence.
- [ ] Executive Summary is concise and decision-useful.
- [ ] Missing inputs and limitations are visible.
- [ ] Sources and assumptions are documented.
- [ ] The workbook is suitable for review without additional cleanup.

## Example Prompts

### Full Build

> Build a complete data pack for **[Company]** from the attached CIM. Include three years of historical results and management projections, an adjusted EBITDA bridge, operating KPIs, segment performance, and an executive summary. Present financials in USD millions, cite document pages, and flag missing or inconsistent data.

### Existing Template

> Populate the open workbook using the attached financial statements. Preserve the existing tab names and layout. Use formulas for calculated values, retain source traceability, and list missing inputs without inserting placeholders or zeros.

### Update

> Update the existing data pack with the latest quarterly results. Preserve prior periods and workbook structure, add the new period, update formulas and summary metrics, and identify material changes from the previous quarter.

### EBITDA Review

> Review management’s EBITDA adjustments. Build reported-to-adjusted bridges by period, assess recurrence risk, and show management, base, and conservative treatments with supporting sources.

### Scenario Analysis

> Add management, base, and downside cases. Document revenue growth, margin, capex, and working-capital assumptions. Keep assumptions editable and make all projections formula-driven.

## Suggested Customizations

You can tailor this template by changing:

- Tab structure
- Industry-specific KPIs
- Adjustment eligibility rules
- Scenario definitions
- Reporting units and precision
- Source-citation method
- Color and formatting standards
- Required validation checks
- Executive Summary layout
- Treatment of estimates and missing data

## Guardrails

- Do not invent missing financial or operating information.
- Do not silently substitute a different source.
- Do not hardcode calculated outputs.
- Do not combine reported and adjusted results without clear labels.
- Do not present projections as historical results.
- Do not accept normalization adjustments without documenting their basis.
- Do not declare the workbook complete while material formula errors or unexplained reconciliation differences remain.

