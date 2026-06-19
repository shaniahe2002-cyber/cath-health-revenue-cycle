
# Reducing Denials and AR Delays: A Revenue Cycle SQL Analysis

**Cath Health Group** (fictional multi-specialty clinic) | 800 claims, FY 2024

## Problem

Cath Health Group, a four-specialty outpatient clinic, was losing revenue to preventable claim denials and slow accounts receivable. This analysis uses 800 claims to find where, why, and how much.

## Tools

MySQL 8.0. CTEs, window functions (RANK() OVER), AR aging buckets, running totals, multi-metric provider ranking.

## Key Findings

- **Behavioral Health.** 16.8% denial rate, driven by prior authorization failures and a 30% self-pay concentration. Lowest collection rate of any service line at 64.0%.
- **Primary Care.** 58 average AR days despite the highest claim volume at 224 claims. This points to a billing workflow bottleneck, not a payer problem.
- **Cardiology.** 89.4% net collection rate, the strongest performer in the dataset and a model worth replicating across other service lines.

## Recommendations

1. Implement a pre-authorization check protocol for Behavioral Health CPT codes 90834, 90837, and 90791 before scheduling. Estimated annual recovery of $14,000 to $18,000 in currently denied charges.
2. Audit charge entry lag time in Primary Care. If entry exceeds 3 days post-service, implement same-day charge capture. Target is to reduce AR days to 45 within 90 days.
3. Introduce upfront self-pay collection and a sliding scale fee schedule in Behavioral Health to address structural revenue leakage.
4. Document and replicate Cardiology's billing and follow-up workflows as an internal best practice model.

## What's in This Repo

| File | Description |
|---|---|
| `cath_health_revenue_cycle.sql` | Full schema, seed data (800 claims), and 12 analysis queries (MySQL 8.0+) |
| `Cath_Health_Revenue_Cycle_Report.pdf` | Full case study with results tables, findings, and recommendations |

## Skills Demonstrated

CTEs, Window Functions (RANK, PARTITION BY), Running Totals, CASE WHEN Aggregation, AR Aging Analysis, Denial Rate Analysis, Revenue Cycle Management, MySQL 8.0

---

All data is synthetically generated for portfolio demonstration purposes. The schema, query logic, and analytical methodology reflect authentic revenue cycle analytics practice based on direct experience restructuring billing operations in a clinical environment.

**Analyst:** Shaniah Edwards | MBA, Business Analytics
