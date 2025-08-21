![Python](https://img.shields.io/badge/Python-3.9+-blue?logo=python)
![LightGBM](https://img.shields.io/badge/LightGBM-2.3+-lightgreen?logo=leaflet)
![Optuna](https://img.shields.io/badge/Optuna-Bayesian--Opt-lightgrey?logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![IIT Kanpur](https://img.shields.io/badge/IIT-Kanpur-red?logo=google-scholar)

# 📊 American Express Campus Challenge 2025 — Decision Science Track  

**Team:** *IIT Kanpur (Top 50 Finalist out of 11,753 teams)*  
**Problem Statement:** Improve **customer engagement** by optimizing the **ranking of offers** shown to users.  

---

## 🚀 Project Overview  
Traditional click-prediction models treat each offer independently, missing the **business-critical objective**: *ranking offers by relevance*.  
Our solution delivers a **ranking system** that boosts offer engagement by **+195% (MAP@7)** using a pipeline of **feature engineering, smart sampling, and model optimization**.  

---

## 🔧 Methodology  

### 1️⃣ Data Sampling & Balancing  
- Designed a **smart negative sampling strategy** (5:1 ratio) to preserve **authentic user behavior**.  
- Retained all clicked offers, sampled subset of non-clicked offers → avoided synthetic bias (SMOTE/oversampling).  

### 2️⃣ Feature Engineering (51 Features)  
- **Temporal Signals**: offer age, recency, daily/hourly activity patterns.  
- **Behavioral Signals**: campaign fatigue, offer fatigue, user CTR, impression gaps.  
- **Semantic Signals**: TF-IDF embeddings on product/service, campaign codes, and offer types.  
- **Spend Patterns**: user-level spend mean, std, and variability.  

### 3️⃣ Modeling  
- **Algorithm**: LightGBM Ranker (LambdaRank objective).  
- **Validation**: 5-fold GroupKFold CV by session/user → no temporal leakage.  
- **Hyperparameter Tuning**: Optuna (847 trials, TPE sampler).  

### 4️⃣ Why This Works  
✔ Preserves real user preferences  
✔ Optimizes directly for ranking relevance (MAP@7)  
✔ Captures behavioral + semantic + temporal signals  

---

## 📈 Results  

| Iteration                                | MAP@7 | Δ vs Baseline |
|------------------------------------------|-------|---------------|
| Baseline LightGBM                        | 0.180 | —             |
| + Feature Engineering                    | 0.444 | +146.7%       |
| + Smart Sampling + Optuna Tuning         | 0.531 | +195.0%       |

- **Final Score:** MAP@7 = **0.531**  
- **Top 50 / 11,753 teams nationwide**  
- **Business Impact**:  
  - ↑ Engagement: +40–60% click-through uplift  
  - ↑ Customer Lifetime Value: +15–25% estimated increase  
  - ↓ Training Cost: –80% vs naive approaches  

---

## 🏗 Tech Stack  
- **Python** (pandas, numpy, scikit-learn, LightGBM, Optuna)  
- **Visualization**: Matplotlib, SHAP  
- **ML Paradigm**: Learning-to-Rank (LambdaRank objective)  

---

## 📂 Repository Structure  

