# 🤖 HCP Engagement & Recommendation Model

## 📊 Project Overview

This project was developed to analyze **HCP (Healthcare Professional)** engagement patterns and build a **machine learning model** to recommend potential HCPs most likely to respond positively to brand interactions.  

It combines **multi-channel engagement data** (Calls, Emails, and Messages) to identify behavioral trends and predict the **propensity to recommend** specific brands.  

The model helps commercial and field teams focus on **high-potential HCPs**, optimize resource allocation, and enhance engagement strategy efficiency.

---

## 🧩 Problem Statement

In large healthcare markets, sales representatives engage with thousands of HCPs across multiple digital and physical touchpoints (calls, emails, messages, samples, etc.).  
However, understanding which engagement channels drive meaningful impact — and which HCPs are most likely to respond — remains challenging due to:
- Fragmented interaction data spread across multiple systems (Veeva, CRM, etc.)
- Limited visibility into cross-channel behavior
- Manual analysis not scaling to regional data volume

The goal was to **create a unified dataset** of HCP interactions and use **machine learning** to predict recommendation likelihood — helping the business prioritize engagements more effectively.

---

## 🧠 Approach

1. **Data Integration via PySpark & SQL**
   - Extracted data from multiple sources:
     - `fsfa_call` → Field calls data  
     - `fsfa_sentemail` → Email campaign performance  
     - `fsfa_sent_message` → Message interaction records  
   - Filtered for the **Egypt (EG) market** and post-2025 interactions.  
   - Unified all sources at the **Account (HCP)** level using PySpark and Pandas.  

2. **Feature Engineering**
   - Created behavioral features such as:
     - Total calls and recent (30, 60, 90 days) activity  
     - Number of sampled calls  
     - Email open & click rates (CTR)  
     - Message click-through metrics  
   - Engineered binary target variable `Recommendation` representing HCP likelihood to recommend.

3. **Model Training**
   - Standardized feature values using `StandardScaler`.  
   - Trained multiple models for comparison:
     - Logistic Regression  
     - Random Forest  
     - Gradient Boosting  
     - XGBoost  
     - Support Vector Machine (SVM)  
   - Tuned SVM parameters using **RandomizedSearchCV** to find optimal hyperparameters.  

4. **Model Evaluation**
   - Evaluated all models using:
     - **Accuracy**, **Precision**, **Recall**, and **F1-Score**  
     - **Confusion Matrix** for prediction balance  
   - SVM with `rbf` kernel and `class_weight='balanced'` performed best.  

---

## 📈 Key Insights

- Developed a **feature-driven view** of HCP interactions across all engagement channels.  
- Identified that **recent multi-channel engagement frequency** (calls + opened emails + clicked messages) had the highest correlation with positive brand recommendation.  
- Provided a **data-backed framework** to optimize targeting and resource allocation.  
- Automated generation of recommendations and stored results into Delta tables for Power BI integration.  

---

## ⚙️ Tools & Technologies

| Category | Tools Used |
|-----------|-------------|
| **Data Engineering** | PySpark, SQL (Databricks), Pandas |
| **Machine Learning** | scikit-learn, XGBoost |
| **Evaluation & Tuning** | GridSearchCV, RandomizedSearchCV |
| **Data Storage** | Delta Tables (Databricks) |
| **Visualization / BI** | Power BI (connected to model outputs) |

---

## 🚀 Business Impact

- Enabled **data-driven HCP prioritization** for marketing and field force teams.  
- Improved understanding of **which engagement channels influence HCP conversions**.  
- Automated the process from data extraction to model output — reducing manual work.  
- Provided scalable framework for **cross-market model deployment** in Middle East & Africa.

---

## 🔒 Confidentiality Note

Due to company data protection and compliance policies, real datasets and specific model performance metrics are not disclosed.  
This repository highlights the **analytical process, data engineering flow, and ML approach** used to generate actionable insights.

---

## 👤 Author

**Noor Wali**  
Expert Data Analyst – Haleon  
[LinkedIn](https://www.linkedin.com/in/noor-wali-9ba671175/) | [GitHub](https://github.com/noorw8354)

---

### 🔖 Tags
#Haleon #SQL #PySpark #MachineLearning #HCPAnalytics #RecommendationModel  
#DataScience #SVM #XGBoost #PowerBI #DataEngineering #HealthcareAnalytics #Automation
