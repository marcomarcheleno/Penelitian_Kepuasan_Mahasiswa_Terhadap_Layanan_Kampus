# 📊 Student Satisfaction Analysis Using Naïve Bayes & K-NN

> Data-driven classification of student satisfaction toward academic services using machine learning algorithms.  
> **Academic Journal** · Institut Bisnis dan Informatika Kwik Kian Gie · 2025

---

## 📋 Abstract

This study analyzes the level of student satisfaction at **Kwik Kian Gie Institute of Business and Informatics (IBIKKG)** toward academic services using a descriptive quantitative approach. Data was collected via online questionnaire (Google Forms) from 100 student respondents across 9 service dimensions.

Two classification algorithms — **Naïve Bayes** and **K-Nearest Neighbor (K-NN)** — were applied to categorize student satisfaction into three classes:
- 🔴 **Class 1** — Dissatisfied (Tidak Puas)
- 🟡 **Class 2** — Moderately Satisfied (Cukup Puas)
- 🟢 **Class 3** — Highly Satisfied (Sangat Puas)

The combined algorithms achieved a **prediction consistency rate of 76.67%**.

---

## 🎯 Key Results

| Metric | Naïve Bayes | K-NN (K=3) |
|--------|------------|------------|
| Class 1 (Dissatisfied) | 23.33% | 0% |
| Class 2 (Moderately Satisfied) | 63.33% | 86.67% |
| Class 3 (Highly Satisfied) | 13.33% | 13.33% |
| Prediction Consistency | **76.67%** | **76.67%** |
| Distribution | ✅ More optimal | ⚠️ Less balanced |
| **Recommended Algorithm** | ✅ **Naïve Bayes** | — |

> **Conclusion:** Naïve Bayes produced a more optimal and balanced class distribution for this Likert-scale survey dataset.

---

## 📐 Survey Dimensions (X1–X9)

| Variable | Service Aspect |
|----------|---------------|
| X1 | Facility adequacy |
| X2 | Clarity of academic information |
| X3 | Staff friendliness |
| X4 | Ease of online service access |
| X5 | Service responsiveness |
| X6 | Effectiveness of academic communication |
| X7 | Speed of administrative processes |
| X8 | Transparency of academic assessment |
| X9 | Availability of learning resources |
| X10 | Satisfaction class (target variable) |

---

## 🧠 Algorithms Used

### 1. Naïve Bayes (Gaussian)
Based on Bayes' Theorem with conditional independence assumption:

$$\hat{C} = \arg\max_k P(C_k) \prod_{i=1}^{9} P(X_i | C_k)$$

Gaussian probability density for numerical Likert-scale data:

$$P(X_i | C_k) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left(-\frac{(x_i - \mu)^2}{2\sigma^2}\right)$$

### 2. K-Nearest Neighbor (K=3)
Classification based on Euclidean distance to nearest neighbors:

$$d(x, y) = \sqrt{\sum_{i=1}^{9} (x_i - y_i)^2}$$

---

## 🔧 Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)

- **Language:** Python
- **Libraries:** `pandas`, `numpy`, `scikit-learn`
- **Data Collection:** Google Forms (Likert Scale 1–5)
- **Dataset:** 100 respondents, 70/30 train-test split

---

## 🏗️ Research Workflow

```
Data Collection (Google Forms)
        │
        ▼
┌─────────────────────────────┐
│     Preprocessing           │
│  - Handle NULL values       │  → Mean imputation per attribute
│  - Round decimal values     │  → Maintain Likert scale 1–5
│  - Scale normalization      │
└────────────┬────────────────┘
             │
      ┌──────┴──────┐
      ▼             ▼
┌──────────┐  ┌──────────┐
│  Naïve   │  │   K-NN   │
│  Bayes   │  │  (K=3)   │
│(Gaussian)│  │(Euclidean│
│          │  │ Distance)│
└────┬─────┘  └────┬─────┘
     │              │
     └──────┬───────┘
            ▼
┌─────────────────────────────┐
│   Model Comparison          │
│   Accuracy · Precision      │
│   Recall · F1-Score         │
│   Distribution Analysis     │
└─────────────────────────────┘
```

---

## 🚀 How to Run

```bash
# Clone repository
git clone https://github.com/marcomarcheleno/Student-Satisfaction-NaiveBayes-KNN.git
cd Student-Satisfaction-NaiveBayes-KNN

# Install dependencies
pip install -r requirements.txt

# Run the analysis
python main.py
```

---

## 📁 Project Structure

```
Student-Satisfaction-NaiveBayes-KNN/
│
├── main.py                  # Main script: preprocessing + training + evaluation
├── naive_bayes.py           # Naïve Bayes model implementation
├── knn.py                   # K-NN model implementation
├── data/
│   └── dataset_kepuasan.csv # Survey dataset (100 respondents)
├── results/
│   ├── nb_predictions.csv   # Naïve Bayes prediction output
│   ├── knn_predictions.csv  # K-NN prediction output
│   └── comparison_chart.png # Distribution comparison visualization
├── requirements.txt
└── README.md
```

> ⚠️ *Note: Project structure reflects intended architecture. Code files will be uploaded progressively.*

---

## 📊 Key Findings

**What students are satisfied with:**
- ✅ Administrative staff friendliness
- ✅ Clarity of academic information

**Areas needing improvement:**
- ❌ Service responsiveness
- ❌ Academic communication system

**Algorithm comparison:**
> Naïve Bayes is better suited for this Likert-scale survey dataset because its probabilistic approach produces a more balanced and representative class distribution, while K-NN's distance-based method resulted in over-concentration toward Class 2.

---

## 👥 Authors

| Name | Student ID | Institution |
|------|-----------|-------------|
| Charlie Parulianta | 45239046 | Kwik Kian Gie School of Business and Informatics |
| **Marco Marcheleno** | 59230168 | Kwik Kian Gie School of Business and Informatics |
| Jason Ronaldo Wijaya | — | Kwik Kian Gie School of Business and Informatics |

---

## 📄 Publication

> **"Kepuasan Mahasiswa IBIKKG terhadap Layanan Akademik Menggunakan Algoritma Naïve Bayes dan K-NN"**  
> Program Studi Sistem Informasi, Institut Bisnis dan Informatika Kwik Kian Gie · 2025

---

## 📚 Key References

1. Dewi Antika et al. — *Naïve Bayes dan SVM untuk Klasifikasi Kepuasan Mahasiswa*, 2025
2. Saurina et al. — *Sentiment Analysis with Naïve Bayes and K-NN Comparison*, 2022
3. Attamimi et al. — *K-NN dalam Analisis Kepuasan Layanan*, 2022
4. Ima. Hendro — *Analisa Kepuasan Mahasiswa terhadap E-Learning*, 2022

---

## 📜 License

This project is for academic purposes. Please cite the authors if you use this work as a reference.

---

<p align="center">
  Made with ❤️ for data-driven educational quality improvement
  <br>
  Institut Bisnis dan Informatika Kwik Kian Gie · 2025
</p>
