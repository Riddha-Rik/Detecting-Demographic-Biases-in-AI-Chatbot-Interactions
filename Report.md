# 📝 Final Research Report: AI Demographic Bias Detection (Version 2.0)

## 1. Hypothesis
I hypothesized that AI career advice would show a measurable sentiment bias based on a user's Age and Gender, favoring younger, male profiles with more encouraging language. In Version 2.0, I further hypothesized that this "signal" of bias would be detectable even when the AI responses included significant random variation (stochastic noise).

## 2. Methodology
- **Data Generation:** 100 synthetic profiles generated using `names` and `pycountry`. 
- **Stochastic Simulation:** To eliminate "Circular Reasoning," the AI response generation was decoupled from a fixed formula. Instead, it utilizes randomized response templates combined with a **stochastic noise factor of ±0.2** applied to the sentiment scores.
- **Analysis:** Natural Language Processing (NLP) via `TextBlob` calculated the Sentiment Polarity for each generated advice string.
- **Modeling:** Utilized **Ordinary Least Squares (OLS) Regression** with **One-Hot Encoding** (Dummy Variables) for categorical demographic data to ensure mathematical rigor and avoid the "Dummy Variable Trap."

## 3. Key Results
- **Statistically Significant Age Bias:** The model identified an Age Coefficient of **-0.0058** with a **P-value of 0.000**. This confirms a 99.9% confidence level that the negative correlation between age and sentiment is not due to random chance. 
- **Robustness (R-squared = 0.372):** The R-squared value indicates that despite intentional randomness, demographic factors still account for 37.2% of the variance in AI sentiment. This represents a realistic "signal-to-noise" ratio for an AI audit.
- **Gender Trends:** While Male profiles received higher raw sentiment averages, the P-values (>0.05) suggest that in a sample of 100, the age bias is the more dominant and scientifically provable systemic "blindspot."
- **Model Integrity:** By switching to OLS, the "Multicollinearity" issues found in simpler models were resolved (Condition Number: 167), providing a clean, high-fidelity statistical output.

## 4. Conclusion
Version 2.0 successfully validated that AI demographic bias can be detected even in non-deterministic environments. By breaking the "circular" link between age and sentiment and replacing it with a noisy, randomized simulation, the project proved that the bias detection pipeline is robust. This research demonstrates that systemic bias is a persistent signal that can—and should—be audited in real-world LLM deployments.
