# GNR: Genetic-Embedded Nuclear Reaction Optimization for Gene Selection  
### Official Repository of the IJMS 2025 Published Method  
**“GNR: Genetic-Embedded Nuclear Reaction Optimization with F-Score Filter for Gene Selection in Cancer Classification”**  
Alkamli & Alshamlan, 2025  

---

## 📌 Overview

This repository presents the methodology, datasets, and experimental results of **GNR**, a hybrid metaheuristic algorithm designed for **gene selection in microarray cancer datasets**.  

GNR integrates:

- **F-Score filtering** (pre-selection of top 500 genes)  
- **Nuclear Reaction Optimization (NRO)**  
- **Embedded Uniform Genetic Crossover (30% probability)**  
- **Lévy Flight Mutation**  

The selected genes are evaluated using an **SVM classifier with Leave-One-Out Cross-Validation (LOOCV)**.

In the published study, GNR achieved:

- **100% accuracy** on *all six* benchmark datasets  
- Using **only 2–22 genes** depending on the dataset  
- Outperforming 9 state-of-the-art algorithms  

---

## 🔒 Code Availability

The implementation of the GNR algorithm is available upon request for academic and research purposes.

---

## 📁 Repository Structure

```
GNR/
│
├── GNR.py               # Code availability notice
│
├── Datasets/
│     ├── Colon.arff
│     ├── Leukemia1.arff
│     ├── Leukemia2.arff
│     ├── Lung.arff
│     ├── Lymphoma.arff
│     └── SRBCT.arff
│
└── README.md
```

---

## 🔬 Methodology

### **1. Preprocessing**
- Fix malformed ARFF structures  
- Convert categorical labels to integers  
- Z-score normalization  
- Mean imputation for missing values  

---

### **2. F-Score Filtering**
Reduces thousands of genes to the **top 500 most informative**:

```python
f_classif(X, y)
```

---

### **3. GNR Optimization**

A population-based search combining:

#### 🔹 Nuclear Fission  
- Random Gaussian mutation  
- Lévy flight steps for exploration  

#### 🔹 Nuclear Fusion  
- Solution ionization  
- **Embedded uniform crossover**  
  - 80% inheritance from best solution  
  - 20% from a random solution  

#### 🔹 Mutation on 20% of genes  
Ensures strong exploration of the search space.

---

### **4. Evaluation**

Each candidate gene subset is evaluated with:

- **Linear SVM**  
- **Leave-One-Out Cross-Validation (LOOCV)**  
- Fitness = **classification accuracy**  

---

### **5. Repetition**

All experiments repeat **30 runs per dataset** for statistical significance.

---

## 📊 Datasets

GNR is evaluated on six well-known microarray datasets:

| Dataset | Classes | Samples | Genes |
|--------|---------|---------|--------|
| Colon | 2 | 62 | 2000 |
| Leukemia 1 | 2 | 72 | 7129 |
| Leukemia 2 | 3 | 72 | 7129 |
| Lung | 2 | 96 | 7129 |
| Lymphoma | 3 | 62 | 4026 |
| SRBCT | 4 | 83 | 2308 |

---

## 📈 Published Results (IJMS 2025)

| Dataset | # Genes Selected | Accuracy |
|--------|------------------|----------|
| Colon | 22 | 100% |
| Leukemia 1 | 3 | 100% |
| Leukemia 2 | 4 | 100% |
| Lung | 2 | 100% |
| Lymphoma | 2 | 100% |
| SRBCT | 5 | 100% |

GNR is the **only algorithm** among all compared methods to achieve **perfect accuracy** on every dataset.

---

## 🧬 Predictive Gene Sets (Final Output)

### Colon — 22 genes  
T68848, L08069, X74795, U31525, L05144, T90280, X87342, R01124, D14520,  
R54097, T47584, T47383, T58861, R88740, T51539, U31215, T84049,  
H20709, T72879, R80427, M29065, X65873  

### Leukemia 1 — 3 genes  
M75715_s_at, HG1612-HT1612_at, X95735_at  

### Leukemia 2 — 4 genes  
M37271_s_at, D87459_at, X85116_rna1_s_at, M89957_at  

### Lung — 2 genes  
U53446_at, U60115_at  

### Lymphoma — 2 genes  
GENE1602X, GENE3621X  

### SRBCT — 5 genes  
gene2000, gene509, gene586, gene545, gene742  

---

## 📝 Citation

If you use this work, please cite:

```
Alkamli, S.; Alshamlan, H. GNR: Genetic-Embedded Nuclear Reaction
Optimization with F-Score Filter for Gene Selection in Cancer Classification.
International Journal of Molecular Sciences, 2025.
```

---

## 📜 License

This repository is provided for **academic and research purposes only**.
