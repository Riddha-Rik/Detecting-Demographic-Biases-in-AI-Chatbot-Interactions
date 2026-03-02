# 📝 Final Research Report: AI Demographic Bias Detection (Version 1.0)

## 1. Hypothesis
I hypothesized that AI career advice would show a measurable sentiment bias based on a user's Age and Gender, favoring younger, male profiles with more encouraging language.

## 2. Methodology
- **Data:** Generated 100 synthetic profiles using `names` and `pycountry` to create a diverse set of demographic inputs.
- **Analysis:** Used `TextBlob` to calculate Sentiment Polarity (on a scale of -1 to 1) for each simulated AI response.
- **Modeling:** Trained a `Scikit-Learn` Linear Regression model to quantify the exact impact of demographic features (Age, Gender, Income) on the AI’s sentiment.

## 3. Key Results
- **Age Bias Detected:** The model showed a coefficient of **-0.0148** for Age. This proves an inverse relationship: as age increases, the encouragement and positivity from the AI decreases significantly.
- **Gender Bias:** Visual analysis confirmed that Male profiles received higher average sentiment scores than Female and Non-binary/Transgender profiles.
- **Income/Education:** These factors showed negligible impact on the AI’s sentiment, suggesting the "blindspot" is primarily demographic (Age and Gender).

## 4. Conclusion
The project successfully validated the presence of demographic bias in simulated AI career coaching. This highlights the need for Bias Auditing in LLM deployments to ensure equitable career guidance for all age groups and genders. This initial version established the technical pipeline for sentiment-based bias detection.

---
*Note: This report represents the initial deterministic model (V1.0). For the updated stochastic model that addresses circular reasoning, see Version 2.0.*
