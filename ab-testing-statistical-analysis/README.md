# A/B Testing & Statistical Analysis

## Experiment Design: Subscription Conversion Optimization

This project demonstrates a rigorous A/B testing framework applied to a subscription service's landing page. We compare two variants:
- **Control (Group A):** The current landing page.
- **Variant (Group B):** A redesigned landing page with a streamlined checkout process and new social proof elements.

**Primary Metric:** Conversion Rate (User subscribed: Yes/No).

### Key Findings
- **Statistical Significance:** The experiment achieved a p-value of < 0.05, allowing us to reject the null hypothesis.
- **Effect Size:** Measured using Cohen's d to determine the practical significance of the change.
- **Statistical Power:** A post-hoc power analysis confirmed the experiment was sufficiently powered to detect the observed difference.
- **Bayesian vs. Frequentist:** The Bayesian approach provided a probability distribution of the uplift, offering a more intuitive interpretation for business stakeholders compared to the frequentist p-value.

## Implementation Details
The accompanying Jupyter notebook (`experiment.ipynb`) provides a full end-to-end implementation including:
1. **Hypothesis Setup:** Defining null and alternative hypotheses.
2. **Synthetic Data Generation:** Simulating 10,000 user interactions with controlled conversion rates.
3. **Frequentist Tests:** Implementation of T-tests and Chi-square tests.
4. **Bayesian Modeling:** Using a Beta-Binomial conjugate prior to estimate the posterior distribution of conversion rates.
5. **Power Analysis:** Calculating the minimum required sample size and achieved power.
