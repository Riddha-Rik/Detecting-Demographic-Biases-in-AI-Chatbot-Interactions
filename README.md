# 🤖 AI Career Bias Detector (v2.0)
An end-to-end data science pipeline to quantify demographic "blindspots" in AI career advice.

## 📌 Project Overview
Does an AI give the same encouragement to a 20-year-old as it does to a 60-year-old? This project uses **Natural Language Processing (NLP)** and **Machine Learning** to detect if AI chatbots provide biased sentiment based on Age, Gender, and Education.

**Update (v2.0):** This project was recently updated to move from a deterministic model to a **stochastic (randomized) model**. By introducing "noise," I eliminated circular reasoning and proved that the detection pipeline can find bias even in unpredictable, real-world data.

## 🛠️ The Tech Stack
- **Data Generation:** Python, `names`, `pycountry` (100 Synthetic Profiles)
- **Sentiment Analysis:** `TextBlob` (Polarity & Subjectivity)
- **Visualization:** `Matplotlib`, `Seaborn`
- **Machine Learning:** `Scikit-Learn` (Linear Regression)

## 📊 V2.0 Statistical Validation
To ensure the audit was robust, I introduced a noise factor of $\pm 0.2$ to the sentiment scores and used One-Hot Encoding for gender variables. 

### OLS Regression Results
```text
                            OLS Regression Results                            
==============================================================================
Dep. Variable:     Sentiment_Polarity   R-squared:                       0.372
Method:                 Least Squares   F-statistic:                     18.97
Prob (F-statistic):           9.69e-10   P-value (Age):                   0.000
------------------------------------------------------------------------------
                coef    std err          t      P>|t|      [0.025      0.975]
------------------------------------------------------------------------------
const           0.5179      0.037     13.835      0.000       0.444       0.592
Age            -0.0058      0.001     -7.465      0.000      -0.007      -0.004
Gender_Male    -0.0191      0.027     -0.707      0.481      -0.073       0.034
Gender_Non-binary -0.0033   0.028     -0.117      0.907      -0.059       0.052
==============================================================================


## 🧪 Research Evolution: Breaking the "Circle"
Originally (v1.0), the model yielded a near-perfect correlation. To ensure this wasn't **Circular Reasoning** (where the result is baked into the data generation step), Version 2.0 was developed to test robustness:

1. **Stochastic Noise:** I added random fluctuations to the sentiment scores. This mimics the "human-like" inconsistency of real LLMs.
2. **Template Randomization:** The "AI" now chooses from a variety of responses, preventing the ML model from seeing a perfect, pre-programmed pattern.
3. **Validation:** The fact that the Age Bias coefficient **survived the noise** proves that the bias is a persistent statistical signal, not a programming artifact.

## 📂 Repository Structure
- `Bias_Detection_Robustness_Testing.ipynb`: The core Google Colab pipeline.
- `synthetic_bias_data_stochastic_v2.csv`: The randomized dataset used for the final audit.
- `requirements.txt`: Necessary libraries for replication.

---
*Developed as a research exploration into AI Ethics and Algorithmic Fairness.*
