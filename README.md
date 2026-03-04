# AI Bias Auditor: Organic Hiring Data Analysis

## 📌 Project Overview
This project is an automated auditing suite designed to detect systemic bias within AI-driven hiring models. By analyzing 1,500 candidate records, this tool evaluates whether factors like **Age (Experience)**, **Education Level**, or **Intersectional Traits** unfairly influence the AI's hiring decisions compared to human recruiters.

This repository serves as an extension of the core Informatics project, focused on **Algorithmic Accountability** and **AI Ethics**.



## 🛠 Features
- **Negative Result Auditing:** Proves the absence of bias using statistical significance (P-Values).
- **Multi-Factor OLS Regression:** Analyzes how specific variables (like PhD vs. Bachelors) affect final scores.
- **Logistic Regression Analysis:** Audits the binary "Hire/No-Hire" decision logic to see if probability of selection is skewed.
- **Intersectional Stress Testing:** Checks for "hidden" biases where multiple factors combine (e.g., Highly experienced + PhD).
- **Decision Friction Heatmaps:** Visualizes the "Divergence Gap" where human intuition and AI logic disagree most.

## 📊 Key Findings (Audit V5.0)
- **Merit-First Logic:** The model shows a **0.98 correlation** between Skill Fit and AI Scores, proving high alignment with objective qualifications.
- **Age Neutrality:** No statistically significant age bias was found across the dataset ($P > 0.50$).
- **High Alignment:** Human recruiters and the AI model achieved a **90.6% agreement rate** on final hiring decisions.
- **Education Fairness:** The model maintains consistent standards across all degree levels; no significant "Credentialism" was detected.



## 🚀 Tech Stack
- **Language:** Python 3.x
- **Core Libraries:** - `pandas`: Data manipulation and feature engineering.
  - `statsmodels`: Advanced statistical modeling and OLS/Logit regressions.
  - `plotly`: Interactive data visualization and heatmap generation.
- **Version Control:** Git (Branching strategy: `feature/bias-auditor-v5`)

## 📂 Dataset Structure
The audit utilizes `ai_hiring_audit_dataset.csv`, containing:
- `Candidate_ID`: Unique identifier.
- `Years_Experience`: Proxy for candidate age.
- `Skill_Fit_Score`: Normalized merit score based on testing.
- `AI_Decision` / `Human_Decision`: Binary outcomes (0=Reject, 1=Hire).
- `Score_Divergence`: The mathematical delta between human and machine ratings.

## 📈 How to Run
1. Clone the repository.
2. Switch to the audit branch:
   ```bash
   git checkout feature/bias-auditor-v5
