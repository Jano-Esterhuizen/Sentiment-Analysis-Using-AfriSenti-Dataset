
# Sentiment Analysis on African Languages Using Multilingual Transformers

## 📚 Project Overview

This project explores the effectiveness of multilingual transformer models for sentiment classification in low-resource African languages. It compares four models—**mBERT**, **AfriBERTa**, **AfroXLMR**, and **XLM-Roberta**—on four languages: **Ibo**, **Nigerian-Pidgin**, **Mozambican-Portuguese**, and **Yoruba**, using the **AfriSenti dataset**.

Explainability tools like **LIME** and **SHAP** are also integrated to help interpret model predictions and evaluate fairness.

---

## 💾 Dataset

- **Source**: [AfriSenti-SemEval Dataset (Muhammad et al., 2023)](https://github.com/afrisenti/afrisent-semeval-2023)
- **Languages Used**: Yoruba, Nigerian-Pidgin, Ibo, Mozambican-Portuguese
- **Split**: 70% Training / 30% Test
- **Labels**: `positive`, `neutral`, `negative` → Mapped to `0`, `1`, `2`

---

## 🧠 Models Used

| Model                  | Description                          |
|------------------------|--------------------------------------|
| `bert-base-multilingual-cased` | mBERT: General multilingual transformer |
| `castorini/afriberta_base`    | AfriBERTa: Pretrained on African corpora |
| `Davlan/afro-xlmr-base`       | AfroXLMR: African-optimized XLM-R |
| `xlm-roberta-base`            | XLM-Roberta: Trained on 100+ languages |

---

## ⚙️ Installation & Environment

Install required libraries:

```bash
pip install transformers datasets scikit-learn lime shap wandb
```

Log in to Weights & Biases (optional):

```bash
wandb login
```

---

## 🚀 How to Run

1. Clone this repository and navigate to the project folder.
2. Open the notebook:

```bash
jupyter notebook Project_Code_Final.ipynb
```

3. The notebook includes:
   - Preprocessing
   - Zero-shot evaluation
   - Fine-tuning using Hugging Face Trainer
   - Evaluation (F1, AUC, Kappa, etc.)
   - Explainability (LIME, SHAP)

---

## 📈 Evaluation Metrics

- Accuracy  
- Precision / Recall / F1 (Macro)  
- ROC AUC (OvR)  
- Cohen’s Kappa  

Baseline performance is compared with a majority-class predictor and zero-shot inference.

---

## 🧪 Results Summary

- **AfriBERTa** and **AfroXLMR** consistently outperformed general-purpose models in Ibo and Yoruba.
- **Nigerian-Pidgin** was the most challenging due to code-switching and informal structures.
- **Explainability**:
  - LIME highlighted alignment of predictions with emotion-laden tokens.
  - SHAP revealed token-level attribution inconsistencies in low-resource setups.

---

## 🛡️ Responsible AI

- Bias evaluation showed lower performance on informal dialects like Pidgin.
- Models pretrained on African corpora were more robust and fair.
- Transparent tracking and reproducibility were maintained using W&B and open datasets.

---

## 📌 Limitations

- Explainability (XAI) limited to a subset of models/languages.
- Nigerian-Pidgin results still unstable.
- ALE plots not implemented.

---

## 📂 Directory Structure

```
├── Project_Code_Final.ipynb     # Main notebook with full pipeline
├── Final Report.pdf             # Full technical report
├── README.md                    # This file
├── project_code_final.py        # Full codebase used for experiments and running code
```

---

## 🤝 Authors

- Niel Nortier  
- Fhulufhelo Tshivhula  
- Jano Esterhuizen  

University of Pretoria, COS760
