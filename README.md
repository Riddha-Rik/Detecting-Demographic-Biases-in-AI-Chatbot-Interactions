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

## 📊 Key Findings (Version 2.0 - Stochastic Model)
After introducing **random noise** ($\pm 0.2$ variance) and randomized text templates to ensure the model wasn't just "following a rule," the results remained consistent:

| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **Age Coefficient** | **-0.0048** | Older profiles receive less encouraging advice even with randomized data. |
| **Gender Code** | **0.0045** | Male profiles continue to trend higher in sentiment polarity. |
| **Mean Squared Error** | **0.1226** | Realistic error rate proving the model is finding a signal in "messy" data. |
| **Income Impact** | **0.0000** | No detectable correlation between income and sentiment. |



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
