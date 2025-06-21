# Predicting-Drug-Toxicity-Using-AI-Cheminformatics
# 🧪 AI-Based Drug Toxicity Prediction using SMILES & RDKit

Predicting the **toxicological impact of chemical compounds** is a critical step in early-stage drug discovery. This project leverages **cheminformatics**, **machine learning**, and **SMILES-based molecular representation** to predict the potential toxicity of compounds using the **Tox21 dataset** — all before entering costly clinical trials.

---

## 🔬 Problem Statement

Late-stage drug failures due to **toxicity** not only waste resources but also risk patient safety. Traditional toxicological testing is slow, expensive, and dependent on animal models.

**Goal:** Use AI to predict whether a given molecule is toxic (specifically, active on the NR-AR endpoint) using its SMILES representation — helping scientists eliminate risky compounds early in the pipeline.

---

## 🧠 Why AI for Toxicity?

AI can:
- 🚫 Identify toxic compounds *before* synthesis
- 🧪 Reduce dependence on animal models
- 💰 Save millions in development costs
- ⏱️ Accelerate the drug discovery cycle

By encoding chemical structure into machine-readable formats and training models on known toxic/non-toxic examples, we can forecast outcomes for new, unseen molecules.

---

## 📚 Dataset: Tox21 (NIH)

- **Source**: [Tox21 Challenge](https://tripod.nih.gov/tox21/challenge/)
- **Target**: Binary classification for the **NR-AR (Androgen Receptor)** toxicity pathway.
- **Features**: SMILES strings
- **Labels**: 0 (non-toxic), 1 (toxic)

---

## ⚙️ Tech Stack

| Component | Tool |
|----------|------|
| Language | Python 3.x |
| Cheminformatics | RDKit |
| Modeling | scikit-learn (Random Forest) |
| Visualization | matplotlib, seaborn, py3Dmol |
| Data | Tox21 CSV (SMILES + labels) |

---

## 🧪 Key Steps

### 1. **Molecule Representation**
- Used **SMILES strings** as input
- Parsed using `rdkit.Chem.MolFromSmiles`
- Extracted 6 physicochemical descriptors:
  - Molecular Weight
  - LogP (lipophilicity)
  - Topological Polar Surface Area (TPSA)
  - Number of Rotatable Bonds
  - Hydrogen Bond Donors/Acceptors

### 2. **Model Training**
- Model: **Random Forest Classifier**
- Evaluation:
  - Accuracy: **~96%**
  - ROC AUC: **0.74**
  - Confusion matrix and classification report

### 3. **Visualization**
- Class distribution histogram
- Feature importance bar plot
- Confusion matrix
- ROC curve with AUC
- **3D Molecule Viewer** (Py3Dmol) for visual inspection

---

## 📂 Project Structure
toxicity-predictor/
│
├── data/
│ └── tox21.csv
│
├── src/
│ ├── feature_extraction.py
│ ├── train_model.py
│ └── predict.py
│
├── notebooks/
│ └── eda_visuals.ipynb
│
├── models/
│ └── random_forest_tox21_NR-AR.pkl
│
├── requirements.txt
└── README.md
#🧠 Future Work
 Add Morgan fingerprints (ECFP4) for richer structural information

 Train multi-output models across all Tox21 endpoints

 Deploy using Streamlit or FastAPI for live prediction

 Integrate SHAP for model interpretability

 Create molecular libraries and rank by toxicity risk

