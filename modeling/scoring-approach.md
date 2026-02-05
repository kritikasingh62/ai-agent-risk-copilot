# Scoring Approach

## Initial Approach: Predictive Modeling

The project initially explored a predictive modeling approach using LightGBM with **Loss Ratio** as the target variable.

While technically sound, this approach surfaced several issues:
- High variance driven by low exposure counts
- Sensitivity to rare but severe claims
- Limited interpretability for business users
- Poor alignment with stakeholder expectations

Model accuracy did not translate into actionable insight.

## Key Pivot: Business-Aligned Metrics

Through collaboration with actuarial, pricing, and data science teams, two critical insights emerged:

1. Loss ratios are unreliable at the agent level
2. The business goal was understanding performance, not prediction

## Final Approach: PD Frequency–Based Scoring

The solution pivoted to:
- Policy-level analysis
- **PD Frequency** as the outcome metric  
  (claims / earned days × 365)
- Simple linear modeling to derive directional weights

### Why This Worked
- PD frequency is more stable and interpretable
- Coefficients clearly reflect behavioral impact
- Weights can be transparently translated into scores

The resulting score is intentionally directional, designed to support interpretation and discussion rather than optimization.
