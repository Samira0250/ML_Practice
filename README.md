# ML Pipeline Practice – Based on Kullmann et al.

This repository contains my practice implementation of the machine learning pipeline described in **Kullmann et al. (2025)**. The goal of this project was to gain hands-on experience with applying machine learning methods to genomic-style data.  

---

## Project Overview  
The pipeline I practiced includes three main steps:  
1. **Feature Selection** – Elastic Net regression to reduce thousands of features down to the most informative ones.  
2. **Classification** – Random Forest classifier trained on the selected features.  
3. **Evaluation** – Model performance measured using:  
   - Accuracy  
   - Sensitivity (Recall)  
   - Specificity  
   - Precision  
   - Confusion Matrix  
   - ROC Curve & AUC  

---

## Data  
- I used **simulated methylation-style data** (~200 samples × 5,000 features).  
- A subset of features contained a true signal, while the rest were noise.  
- This setup helped me test how well the pipeline can detect relevant features under both easy (strong signal) and realistic (weaker signal + noise) conditions.  

---

## Results  
- **Features selected**: ~80  
- **Accuracy**: ~0.62  
- **AUC**: ~0.63  
- **Sensitivity**: ~0.61  
- **Specificity**: ~0.63  
- **Precision**: ~0.67  

Confusion Matrix (example):  
```
Predicted / Actual    Control   Case
Control                 17       10
Case                    13       20
```

---

## Figures  
- **ROC Curve** → shows AUC ≈ 0.63 (not perfect, but better than random).  
- **Feature Importance Plot** → highlights the most informative features (mostly from the “true signal” set).  

---

## Takeaways  
- Perfect model results often mean unrealistic or overly clean data.  
- Once noise was added, the model’s performance dropped but became more biologically realistic.  
- This project helped me understand not only how to set up Elastic Net + Random Forest, but also why **data realism is critical in genomics ML**.  

---

## Future Work  
- Apply the pipeline to **real methylation data** instead of simulated data.  
- Compare **different classifiers** (e.g., SVM, XGBoost) to see if performance improves.  
- Experiment with **larger sample sizes** and **cross-validation** for more robust evaluation.  
- Explore **interpretability tools** (e.g., SHAP values) to better understand model decisions.  

---

## How to Run  
Clone the repo and run the pipeline in R or Python (depending on your setup).  
*(Note: This is a practice project; code may not be fully optimized.)*  

```bash
git clone https://github.com/your-username/ml-pipeline-practice.git
cd ml-pipeline-practice
```

