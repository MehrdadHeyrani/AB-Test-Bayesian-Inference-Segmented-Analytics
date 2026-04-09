# Enterprise A/B Testing Framework: Mobile UI Redesign Experiment

This notebook provides a comprehensive A/B testing framework applied to a simulated banking product experiment. The goal of the experiment was to evaluate the impact of a new mobile-first UI redesign on product activation (defined as completing ≥1 funded transfer within 7 days).

## Experiment Overview
A mid-size bank rolled out a new mobile-first UI to a random 50% of its users. The old UI required multiple taps to access key actions, while the new design surfaced them on the home screen. The analysis aimed to determine if this change significantly improved product activation, while also considering heterogeneous treatment effects across different user segments (e.g., mobile vs. desktop users, age groups).

## Methods Used
This framework incorporates a variety of statistical methods to ensure robust analysis and actionable insights:

*   **Data Simulation**: Realistic banking cohort with heterogeneous treatment effects.
*   **Experiment Validity Checks**: Sample Ratio Mismatch (SRM) check and covariate balance assessment to ensure random assignment.
*   **Frequentist Testing**: Two-proportion Z-test for overall lift and significance.
*   **Bootstrap**: Non-parametric estimation of lift distribution and confidence intervals.
*   **Bayesian Analysis**: Beta-Binomial conjugate model for direct probability statements and risk assessment.
*   **Sequential Bayesian Monitoring**: Tracking experiment progress and belief updates over time.
*   **CUPED (Controlled Experiment using Pre-Experiment Data)**: Variance reduction technique using pre-experiment activity scores.
*   **Segmented Analysis**: Per-segment Z-tests with Bonferroni correction for multiple comparisons to identify heterogeneous effects.
*   **Decision Engine**: Translates statistical findings into a business recommendation with projected impact.
*   **Visualisation Dashboard**: A 10-panel publication-quality dashboard for clear communication of results.

## Key Findings (based on current execution):

*   **Overall Lift**: The treatment group showed an absolute lift of **+2.0300%** (relative lift of +24.27%) in conversion rate compared to the control group.
*   **Statistical Significance**: All frequentist, bootstrap, and Bayesian methods indicate a statistically significant positive effect.
    *   Frequentist P-Value: 0.000000 (SIGNIFICANT)
    *   Bayesian P(Treatment > Control): 100.00%
    *   Bootstrap 95% CI: [+1.2864%, +2.7579%] (entirely positive)
*   **Segmented Insights**: 
    *   **Mobile users**: Show a significant positive lift.
    *   **Desktop users**: Show a slight negative impact. 
    *   **Seniors**: Experience a negative impact from the new UI.

## Final Recommendation:

**📱 TARGETED ROLLOUT — Ship to Mobile users; exclude Seniors**

**Confidence: HIGH (with guardrail)**

**Rationale:**
*   Strong positive signal on Mobile users (primary target).
*   Seniors show negative impact (e.g., -6.83% relative lift for 'Senior' age band) — recommend exclusion or opt-out.
*   Segmented rollout captures significant upside while protecting at-risk groups.

**Projected Business Impact (500k users):**
*   Incremental conversions: 10,150/year
*   Revenue impact: $3,451,000/year
*   Revenue 95% CI: [$2,186,880, $4,688,430]


## Visual Analysis
### 
![Risk Profile Plot](ABtest.png) 

