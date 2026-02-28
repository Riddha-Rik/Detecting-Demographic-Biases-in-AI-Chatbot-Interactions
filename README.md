# Detecting-Demographic-Biases-in-AI-Chatbot-Interactions
An end-to-end Python pipeline detecting demographic bias in AI career advice. Using a synthetic dataset of 100 profiles (names/pycountry), I performed sentiment analysis via TextBlob and trained a Scikit-Learn regression model. Found a significant age-based bias (coeff: -0.0148), proving AI gives less encouraging advice as age increases.
# 🤖 AI Career Bias Detector
An end-to-end data science pipeline to quantify demographic "blindspots" in AI career advice.

## 📌 Project Overview
Does an AI give the same encouragement to a 20-year-old as it does to a 60-year-old? This project uses **Natural Language Processing (NLP)** and **Machine Learning** to detect if AI chatbots provide biased sentiment based on Age, Gender, and Education.

## 🛠️ The Tech Stack
- **Data Generation:** Python, `names`, `pycountry` (100 Synthetic Profiles)
- **Sentiment Analysis:** `TextBlob` (Polarity & Subjectivity)
- **Visualization:** `Matplotlib`, `Seaborn`
- **Machine Learning:** `Scikit-Learn` (Linear Regression)

## 📊 Key Findings
After analyzing 100 unique demographic prompts, the model revealed:
1. **Age Bias:** A strong negative correlation (**Coefficient: -0.0148**). For every year a user ages, AI encouragement scores drop significantly.
2. **Gender Disparity:** Male profiles received the highest average sentiment polarity, followed by Female and Non-binary/Transgender profiles.
3. **Income Neutrality:** The AI remained neutral regardless of the user's annual income.

## 🚀 How to Run
1. Clone the repo.
2. Run the `AI_Bias_Analysis.ipynb` notebook.
3. View the generated `AI_Demographic_Bias_Results.csv`.

Note: Due to API rate limits, the results in this repository were generated using a biased simulation script to demonstrate the data science pipeline and the effectiveness of the Linear Regression bias-detection model.
