# 🧠 DQ Intelligence System  
### Automated Data Quality Assessment, Improvement & Scoring Engine

This project delivers an intelligent **end-to-end Data Quality Management framework** capable of profiling, detecting, cleansing, and benchmarking data issues — fully automated across multiple real-world datasets.

---

## 🚀 Objective

To ensure **high-trust, ML-ready datasets** by building a system that:
✔ Diagnoses data quality issues  
✔ Recommends the best corrective actions  
✔ Automatically cleans the data  
✔ Quantifies improvements using a **DQ Score (0–100)**

---

## 🔍 Key System Highlights

- Fully automated **meta-profiling** across 20+ Data Quality dimensions  
- **Recommendation Engine** that suggests best cleaning action per column  
- Automated cleansing pipeline tightly linked to recommendations  
- Benchmarks pre- vs post-cleaning quality using weighted scoring  
- Scalable solution that generalizes to any tabular dataset

---

## 🧪 Metrics & Issues Detected

| Category | What is Evaluated |
|---------|------------------|
| Completeness | Missing % |
| Integrity | Type errors, rule violations |
| Uniqueness | Duplicate rows %, uniqueness |
| Consistency | Whitespace errors, category formatting |
| Accuracy | Statistical outliers (Z-score) |
| Variety | Rare categories, cardinality |
| Temporal Validity | Date anomalies & static dates |
| Stability / Drift | KL Divergence, PSI, Jensen-Shannon |
| Information Strength | Shannon Entropy |

---

## ⚙️ Cleaning Operations Supported

| Recommendation | Action Taken Automatically |
|--------------|--------------------------|
| High missing % | Drop column |
| Moderate missing % | Mode/Median/Mean Imputation |
| Outliers | Median capping via iterative Z-score |
| Whitespace issues | Auto-strip leading/trailing spaces |
| Rare categories | Merge under “Other” or closest match (NLP-based typo detection using N-grams + Jaccard) |
| Invalid dates | Flag for exclusion |

🧠 **Every decision is explainable** — logged in the recommendations report.

---

## 📈 Data Quality Scoring Engine

A configurable **weighted score (0–100)** combining:
- Structural issues
- Statistical quality
- Semantic errors
- Distribution drift
- Data richness (entropy)

📌 Helps quantify **actual improvement** after cleaning.

---

## 📂 Datasets Used

| Dataset | Domain | Size |
|--------|--------|------|
| NYC Yellow Taxi | Transportation | Large-scale time & fare data |
| UCI Credit Card | Finance | Credit default prediction dataset |
| Customer Churn | Telecom | Retention analytics |
| Adult Census | Workforce analytics | Income classification |

Same pipeline applied for fair benchmarking.

---

## 📥 Outputs Produced

| Output File | Description |
|------------|-------------|
| `meta_data.csv` | Column-wise metrics from profiling |
| `recommendations.csv` | Ranked fixes per column |
| `cleaned_dataset/` | Final cleansed datasets |
| `dq_scores.json` | DQ score per dataset |
| `logs/` | Recommendation traceability |

Compliant data → **better downstream ML performance** ✔

---

## 🛠️ Tech Stack

- Python  
- Pandas, NumPy  
- Scikit-Learn  
- NLTK  
- Mathematical Statistics (Entropy, KL Divergence, PSI)  

---

## 🧠 Architecture Overview

```text
Dataset → Profiling → Issue Detection → Recommendation Engine
       ↓                         ↓
   Drift & Entropy Analysis → Auto-Cleansing → DQ Score → Reports
