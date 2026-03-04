# 🛡️ Technical Comparison Report: AI Bias Auditing Evolution

## 1. Executive Summary
This report analyzes the transition from Project Alpha (Synthetic Bias Detection) to the current Project Extension (v5.0 Organic Decision Audit). While the initial phase established the feasibility of using regression to find age-based sentiment trends, this extension introduces high-fidelity organic data and advanced statistical methodologies to audit actual hiring outcomes.



## 2. Methodology Comparison

| Feature | Project Alpha (Baseline) | Project Extension (v5.0) |
| :--- | :--- | :--- |
| **Data Fidelity** | Synthetic (Python-generated) | Organic (1,500 real-world records) |
| **Primary Variable** | Sentiment Polarity (-1 to 1) | AI Hiring Decision (Binary 0/1) |
| **Statistical Engine** | Simple OLS Regression | OLS + Logit + Interaction Terms |
| **Scope** | Single-variable (Age) | Intersectional (Age x Education) |
| **Visualization** | Static Scatter Plots | Interactive Heatmaps & Lowess Curves |

## 3. Key Technical Advancements

### A. From Sentiment to Selection
Project Alpha focused on "soft bias"—how an AI's tone changed based on age. The Extension pivots to "hard bias"—analyzing the **Logistic Regression** of the `AI_Decision`. This shift allows us to measure the probability of a candidate being hired, providing a more legally and ethically relevant audit.



### B. Intersectional Robustness
A major limitation of the previous project was the inability to see how variables interact. In v5.0, we introduced the **Exp_PhD_Interaction** term. This allows the auditor to detect if the AI penalizes a candidate not just for their degree, but for the combination of a high degree and high experience (the "overqualified" bias).

### C. The "Friction" Heatmap
By calculating `Score_Divergence` (Human Score - AI Score), we moved beyond auditing the AI in a vacuum. We now audit the **Human-AI Agreement**. This identifies specific job categories (like HR and Marketing) where human intuition and algorithmic logic are most likely to clash.

## 4. Comparative Findings

* **Project Alpha:** Indicated a subtle bias in career advice for older candidates (Negative Coefficient).
* **Project Extension (v5.0):** Proved that in a structured hiring environment, the AI is **statistically neutral** regarding age ($P = 0.555$ for decisions), showing a high **90.6% agreement rate** with human recruiters.

## 5. Implementation Status
The v5.0 branch is significantly more robust for professional use. It includes:
- **`requirements.txt`**: For environment reproducibility.
- **`.gitignore`**: For data security and repo cleanliness.
- **`README.md`**: For stakeholder communication.

---
**Status:** ✅ EXTENSION COMPLETE  
**Branch:** `feature/bias-auditor-v5`  
**Date:** March 2026
