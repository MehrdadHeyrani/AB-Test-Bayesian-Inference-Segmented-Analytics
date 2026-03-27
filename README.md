#  A/B Test Framework
### *Strategic UX Evaluation via Bayesian Inference & Segmented Analytics*

---

## Project Overview
In the banking sector, a "one-size-fits-all" UI update can be risky. While a new feature might boost conversions for tech-savvy younger users, it may create **UX friction** for senior segments or desktop users.

This project implements a professional-grade A/B testing engine that goes beyond simple p-values. It simulates a complex banking environment where conversion is influenced by **Credit Scores**, **Age**, **Income**, and **Device Type**, then uses three statistical "lenses" to verify if a UI change is truly a success.

## Key Technical Features
- **Sample Ratio Mismatch (SRM) Guardrail**: Automatically detects if the 50/50 traffic split was compromised using Chi-Square testing.
- **Bayesian Posterior Analysis**: Uses a Beta-Binomial conjugate prior to calculate the exact *Probability of Being the Winner*.
- **Vectorized Bootstrapping**: A high-performance NumPy implementation to calculate robust 95% Confidence Intervals without slow loops.
- **Multi-Dimensional Segmentation**: Analyzes "Lift" across Device Type (Mobile vs. Desktop) and Age Groups (Gen Z vs. Seniors).

## Data Architecture & Simulation
The engine generates a synthetic population of **20,000 users** with interdependent features:
* **Financials**: Credit Score (300-850), Annual Income, and Account Type.
* **Context**: Device Type (Mobile, Desktop, Tablet).
* **The "Twist"**: The simulation logic ensures the Treatment (Mobile-First UI) performs +4% better on Mobile but -3% worse for Seniors, allowing for a deep dive into **Simpson's Paradox**.

## Visual Analysis
### 
![Risk Profile Plot](ABtest.png) 

