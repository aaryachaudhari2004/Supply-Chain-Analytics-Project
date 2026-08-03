# Supply Chain Delivery Performance Analysis

End-to-end analysis of e-commerce order fulfillment, focused on identifying the root causes of late deliveries, quantifying their financial impact, and providing data-driven recommendations to improve on-time performance.

## Overview

This project analyzes **172,765 orders** from a global e-commerce company spanning **January 2015 to January 2018**. The goal was to move beyond a single "late delivery %" metric and understand *why* orders are late, *where* the problem is concentrated, and *what* it's costing the business.

## Business Problem

Actual shipping times frequently deviate from scheduled delivery windows, resulting in:

- Eroded customer trust
- Reduced order profitability
- Unreliable delivery commitments at point of purchase

## Key Findings

| Metric | Value |
|---|---|
| Total Orders Analyzed | 172,765 |
| Late Delivery Rate | 54.71% |
| On-Time Delivery Rate | 45.29% |
| Total Profit (profitable orders) | $7.5M |
| Profit at Risk (delayed orders) | $2.1M |
| 90th Percentile Delay | 3 days |
| Avg Order Profit | $22.03 |

**Headline insight:** More than half of all orders arrive late, and this is a *systemic* issue rather than a regional, seasonal, or segment-specific one — delay rates stay within a narrow 55–59% band across regions and 54–55% across customer segments.

**Root cause:** Shipping mode assignment logic is the single biggest lever:

| Shipping Mode | Delay Rate |
|---|---|
| First Class | 100.0% |
| Second Class | 79.8% |
| Standard Class | 39.8% |
| Same Day | 0.0% |

Customers paying for faster shipping were experiencing the worst delivery performance — the opposite of the intended service level.

Other contributing factors:
- Payment processing delays (`PENDING_PAYMENT`, `PAYMENT_REVIEW`) correlate with higher lateness
- Seasonal peaks in August, September, and December suggest under-planned capacity
- Mean profit per order stays stable (~$20–23) regardless of delay length, confirming this is a **volume problem**, not a per-order margin problem

## Strategic Recommendations

| Priority | Recommendation |
|---|---|
| Critical | Audit First Class & Second Class shipping carrier SLAs |
| High | Resolve payment processing bottlenecks with automated escalation |
| Medium | Build seasonal surge capacity plans for peak months |
| Medium | Default eligible orders to Standard Class |
| Medium | Investigate high-delay departments in worst-performing region |
| Low | Review pricing/discounting for loss-making orders |

## Target Outcomes

| Priority Area | Current State | Target State |
|---|---|---|
| Late Delivery Rate | 54.71% | < 30% within 12 months |
| First Class On-Time Rate | 0% | > 80% |
| Second Class On-Time Rate | 20.2% | > 60% |
| Loss-Making Orders | 18.7% | < 12% |
| Profit at Risk | $2.1M | Reduce by 40% |

## Contents

- `Supply_Chain_Performance_Report.pdf` — full report with charts and detailed breakdowns
