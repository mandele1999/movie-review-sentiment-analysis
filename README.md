# Sentiment Analysis on Movie Reviews
A model that classifies the sentiment of sentences from the Rotten Tomatoes dataset


## **Checkpoint Summary — Baseline to Optimized Ensemble**

### **Phase Coverage**

* Data Preprocessing
* Feature Engineering
* Tier 1 Model Training
* Hyperparameter Tuning
* Lightweight Ensemble Optimization
* Model Interpretation & Insights


### **1. Baseline Performance**

| Model                         | Validation Accuracy | Notes                             |
| :---------------------------- | :------------------ | :-------------------------------- |
| Dummy Classifier              | 0.346               | Establishes trivial benchmark     |
| Logistic Regression (Default) | 0.647               | Strong baseline, well-calibrated  |
| Linear SVC (Default)          | 0.647               | Slightly better boundary handling |
| Logistic Regression (Tuned)   | 0.652               | Improved generalization           |
| Linear SVC (Tuned)            | 0.648               | Minor drop post-tuning            |

---

### **2. Ensemble Performance**

| Configuration     | Weights (LR:SVC) | Validation Accuracy | Macro F1 | Comment                           |
| :---------------- | :--------------- | :------------------ | :------- | :-------------------------------- |
| Simple Average    | 0.5 : 0.5        | 0.6528              | ~0.53    | Baseline ensemble                 |
| Optimized Weights | **0.7 : 0.3**    | **0.6532**          | ~0.53    | Slight but consistent improvement |

*Ensemble improves stability and performance without overfitting.*

---

### **3. Model Behavior & Insights**

* Learns a **clear sentiment gradient** across classes 0–4.
* Captures **linguistic intensity modifiers** (“somewhat,” “mildly,” etc.).
* Handles contextual polarity moderately well but struggles with **subtle tone overlap** (e.g., “beautiful” used sarcastically).
* Ensemble balances **probability confidence (LR)** and **margin robustness (SVC)**.




