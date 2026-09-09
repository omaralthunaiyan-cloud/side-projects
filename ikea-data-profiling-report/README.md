# IKEA Customer Data Profiling Report

A data quality profiling exercise on a synthetic (non-confidential) IKEA customer dataset of 1,000 records, created as a training project during my co-op at Devoteam's Data & Intelligence team.

## Overview

The project walks through data quality (DQ) concepts and applies them to a mock customer dataset, covering:

- Project overview and the importance of data quality
- Compliance & governance context (aligned with Saudi Vision 2030 data governance goals)
- Core data quality dimensions
- Technical profiling and key findings
- Strategic recommendations & roadmap

## Key Findings

- **Duplicate identifiers** — 50 primary keys reused across distinct customer profiles, distorting reporting accuracy
- **Timeline anomalies** — 63 registration dates that are logically inconsistent (likely system clock errors or entry glitches)
- **Hardcoded placeholders** — 62 dummy email addresses (`email@invalid`) used to bypass mandatory field validation
- **Contact unreachability** — 132 phone number records that are invalid, contain internal extensions, or have impossible lengths
- **Inaccurate ages** — 200 extreme/implausible age values
- **Missing data** — 58 null or empty values in mandatory fields
- **Inaccurate names** — 2 invalid name entries

## Recommended Roadmap

1. **Correction** — clean the 1,000 records and remove placeholder values
2. **Standards** — implement unified validation rules across all platforms
3. **Monitoring** — build live dashboards for ongoing data quality audits

## Files

- `Data_Profiling_Report.pptx` — full presentation deck

## Note

All data used is synthetic and was generated for training purposes; it does not represent any real IKEA customer information.
