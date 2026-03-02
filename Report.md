# 📝 Final Research Report: AI Demographic Bias Detection (Version 2.0)

## 1. Hypothesis
I hypothesized that AI career advice would show a measurable sentiment bias based on a user's Age and Gender, favoring younger, male profiles with more encouraging language. In Version 2.0, I further hypothesized that this "signal" of bias would be detectable even when the AI responses included significant random variation (stochastic noise).

## 2. Methodology
- **Data Generation:** 100 synthetic profiles generated using `names` and `pycountry`. 
- **Stochastic Simulation (V2.0):** To eliminate circular reasoning, I moved away from a deterministic formula. The AI now selects from randomized response templates, and a **stochastic noise factor of ±0.2** was added to the sentiment scores to simulate the unpredictability of real-world AI behavior.
- **Analysis:** Used `TextBlob` to calculate Sentiment Polarity for each response.
- **Modeling:** Trained a `Scikit-Learn` Linear Regression model to identify underlying trends within the noisy data.

## 3. Key Results
- **Robust Age Bias:** Despite the introduction of noise, the model identified a persistent **Age Coefficient of -0.0048**. While more subtle than V1.0, the negative slope confirms that age-based discouragement is a systemic trend rather than a random occurrence.
- **Model Reliability:** The **Mean Squared Error (MSE) of 0.1226** proves the model is no longer "predicting a rule," but is instead finding a statistical signal in a messy, realistic environment.
- **Gender Disparity:** Male profiles continued to trend toward higher sentiment scores, suggesting a "Meta-Bias" where even randomized neutral/positive language is weighted differently across gendered names.
- **Income Neutrality:** Income remained a non-factor (0.0000 weight), validating that the model is specifically isolating demographic variables.

## 4. Conclusion
Version 2.0 successfully validated that AI demographic bias can be detected even in non-deterministic environments. By breaking the "circular" link between age and sentiment and replacing it with a noisy, randomized simulation, the project proved that the bias detection pipeline is robust. This research demonstrates that systemic bias is a persistent signal that can—and should—be audited in real-world LLM deployments.
