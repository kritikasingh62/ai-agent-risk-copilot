# Synthetic Agent Data Schema

To enable safe experimentation and demonstration, the AI Agent Risk Copilot uses synthetic agent-level data.

The schema mirrors real Auto LOB behavioral metrics without exposing sensitive or proprietary information.

## Entity: Agent

Each row represents a single agent over a defined evaluation period.

## Fields

- `agent_id`  
  Unique synthetic identifier

- `pct_no_need`  
  Percentage of quotes classified as “No Need”

- `excluded_accident_rate`  
  Percentage of accident claims excluded from consideration

- `excluded_violation_rate`  
  Percentage of violations excluded

- `mpd_recycle_rate`  
  Rate at which motor vehicle reports are reprocessed

- `mvr_order_rate`  
  Percentage of quotes with MVR ordered

- `cbr_na_modify_rate`  
  Rate of CBR marked as not applicable

- `cbr_inconclusive_modify_rate`  
  Rate of inconclusive CBR modifications

- `earned_days`  
  Total earned exposure days

- `claims_count`  
  Number of property damage claims

- `pd_frequency`  
  Calculated as:
  claims_count / earned_days × 365

## Rationale for Synthetic Data

- Enables safe public sharing
- Preserves realistic metric relationships
- Supports repeatable product simulations
- Avoids reliance on confidential internal datasets
