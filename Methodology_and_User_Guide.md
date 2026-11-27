# Methodology and User Guide

## 1. Update the source data
Maintain Project Master with approved project IDs, owners, planned dates, budgets and planned effort. Add one row per project per reporting week in Weekly Updates. Use the same Project ID consistently.

## 2. Weekly update fields
Record week-ending date, submitted date, planned and actual completion percentages, planned and actual cumulative spend, planned and actual hours, blocker/comment and update status. Do not overwrite historical weeks; add a new weekly row.

## 3. RAG rules
The workbook classifies a record as RED when a comment begins with `CRITICAL:` or progress variance is below -15 percentage points. It classifies as AMBER when variance is below -5 percentage points or a non-empty blocker exists. Otherwise it is GREEN. Missing reports are marked NO DATA. Reporting alerts are separate: MISSING UPDATE, LATE UPDATE or ON TIME.

## 4. Portfolio Summary
The summary pulls the latest non-missing completion record for each project and shows actual progress, planned progress, variance, RAG status and latest reporting alert. KPI formulas count the six projects and calculate average progress.

## 5. Issue Log
Repeated blocker comments are grouped into continuing issue records. First and last observed dates are based on the historical weekly records. Age is calculated from the first observed date using TODAY(). Missing-report issues are flagged High and do not receive a numeric age in this curated log.

## 6. EVM and forecasting
PV = BAC × planned completion percentage. EV = BAC × actual completion percentage. AC is latest cumulative actual spend. SV = EV − PV; CV = EV − AC; SPI = EV/PV; CPI = EV/AC; EAC = BAC/CPI; ETC = EAC − AC; VAC = BAC − EAC. Forecast finish adjusts the planned duration by SPI. These are simplified indicative calculations using synthetic data.

## 7. Milestones and dependencies
Milestone Tracker contains illustrative proposed milestone dates and must be validated by project owners before being treated as a baseline. Dependency Register summarises recurring constraints found in blocker comments and suggested follow-up actions.

## 8. Refresh and quality checks
Open in Excel 365 and allow automatic calculation. Check that formulas recalculate, filters include all columns, dates are valid, project IDs match Project Master, and new weekly records are included in formula ranges. Validate forecast assumptions with project managers.

## 9. Limitations
The workbook is a demonstration portfolio model, not a live connected project management system. Issue grouping is manually curated. Milestone dates are proposed, not source-approved. All records are synthetic.
