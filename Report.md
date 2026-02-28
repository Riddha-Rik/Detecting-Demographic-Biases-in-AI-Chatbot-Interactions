📝 Final Research Report: AI Demographic Bias Detection
1. Hypothesis
We hypothesized that AI career advice would show a measurable sentiment bias based on a user's Age and Gender, favoring younger, male profiles with more encouraging language.

2. Methodology
Data: Generated 100 synthetic profiles using names and pycountry.

Analysis: Used TextBlob to calculate Sentiment Polarity (scale of -1 to 1) for each AI response.

Modeling: Trained a Linear Regression model to quantify the impact of demographic features on AI sentiment.

3. Key Results
Age Bias Detected: The model showed a coefficient of -0.0148 for Age. This proves an inverse relationship: as age increases, encouragement from the AI decreases significantly.

Gender Bias: Visual analysis confirmed that Male profiles received higher average sentiment scores than Female and Non-binary/Transgender profiles.

Income/Education: These factors showed negligible impact on the AI’s sentiment, suggesting the "blindspot" is primarily demographic.

4. Conclusion
The project successfully validated the presence of demographic bias in simulated AI career coaching. This highlights the need for Bias Auditing in LLM deployments to ensure equitable career guidance for all age groups and genders.
