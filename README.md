# Fake-News-Detection-ML
This project explores fake news detection from both a predictive and structural perspective. It compares supervised classification with unsupervised clustering to examine whether high accuracy reflects true semantic separation or dataset bias.

# Detecting Fake News and Discovering Its Latent Structure

## 1. Overview

This project investigates fake news detection (FND) from both **predictive** and **structural** perspectives.

Traditional approaches focus on building supervised models to classify news as fake or true. While these models often achieve high accuracy, this project explores a deeper question:

> Do fake and true news articles form truly separable groups in semantic space?

To answer this, I combine:
- **Unsupervised learning** (K-Means, HDBSCAN, GMM)
- **Supervised learning** (Logistic Regression, Random Forest)
- **Deep learning representations** (GPT embeddings)

The goal is to compare **model performance vs. underlying data structure**.

---

## 2. Methods

### Data Processing
- Combined multiple datasets of fake and true news
- Cleaned and normalized text (lowercasing, removing URLs, whitespace normalization)
- Removed duplicates and missing values

### Text Representation
- **TF-IDF**: captures word frequency and writing style
- **GPT embeddings**: captures semantic meaning and contextual relationships

### Unsupervised Learning
- **K-Means**: partition-based clustering
- **HDBSCAN**: density-based clustering with noise detection
- **GMM (Gaussian Mixture Model)**: probabilistic clustering

---

## 3. Key Findings

### Unsupervised Models
- Clusters reveal **semantic structure**, not clear separation
- Only ~28% of fake news lies in high-purity clusters
- Strong **overlap between fake and true news**
- Suggests fake and true are **not cleanly separable**

### Supervised Models
- Logistic Regression achieves **AUC ≈ 0.99**
- Complex models do not significantly improve performance
- Suggests fake vs. true is **easily separable in embedding space**

---

## 4. Key Insight

> There is a fundamental discrepancy between predictive performance and underlying data structure.

- Supervised learning suggests **easy classification**
- Unsupervised learning reveals **overlapping semantic structure**

This raises the question:

> Are models learning truth — or exploiting dataset patterns?

---

## 5. Literature Insights and Critical Perspective

### Dataset Limitations
- Many datasets are:
  - source-dependent
  - domain-specific (e.g., politics)
  - inconsistently labeled

Models may learn:
- writing style
- source patterns
- rather than factual correctness

---

### Modeling Limitations
- Prior work emphasizes complex deep learning models
- However:
  - simple models already perform extremely well
  - increasing complexity does not improve results significantly

---

### Semantic Structure of Fake News
- Fake and true news share:
  - topics
  - vocabulary
  - narrative patterns

Differences are often:
- subtle
- context-dependent
- stylistic rather than factual

---

### Toward a New Perspective

Fake news detection should move beyond binary classification toward:

- **better datasets** (multi-domain, multimodal)
- **probabilistic modeling** (risk scores instead of hard labels)
- **computational modeling** (e.g., Agent-Based Models)
- **interdisciplinary approaches** (social, cognitive, behavioral)

---

## 6. Repository Structure

```bash
project/
│
├── notebooks/
│   ├── 01_data_cleaning_and_preprocessing.ipynb
│   ├── 02_unsupervised_learning_latent_structure.ipynb
│   └── 03_supervised_models.ipynb
│
├── data/
│   └── [sample_data.csv](https://www.kaggle.com/datasets/stevenpeutz/misinformation-fake-news-text-dataset-79k?select=DataSet_Misinfo_FAKE.csv) 
│
├── results/
│   └── figures/
│
├── README.md

## Literature Insights and Critical Perspective
This project extends beyond model implementation and engages with key limitations in the fake news detection (FND) literature.

### 1. Dataset Limitations
Existing FND research heavily relies on datasets that are:
- source-dependent (e.g., mainstream vs. unreliable websites)
- domain-specific (often political news)
- inconsistently labeled

As a result, models may learn **stylistic or source-based patterns** rather than factual correctness.
This aligns with prior work highlighting that dataset quality is a major constraint in FND (Harris et al., 2024).

---

### 2. Discrepancy Between Supervised and Unsupervised Results
A central finding of this project is the contrast between:

- **Supervised models**:
  - Achieve near-perfect performance (AUC ≈ 0.99)
  - Suggest fake and true news are easily separable

- **Unsupervised models**:
  - Reveal overlapping clusters
  - Show only ~28% of fake news appears in high-purity clusters
  - Suggest fake and true news are **not cleanly separable**

This discrepancy indicates that high classification accuracy may not reflect true semantic separation.

---

### 3. Limitations of Current Modeling Approaches
Prior literature emphasizes increasingly complex models (e.g., CNN, LSTM, transformers) for FND (Mridha et al., 2021).
However, this project shows:

- Simple models (logistic regression) already achieve strong performance
- Increasing model complexity does not significantly improve results
- Representation (embeddings) and dataset structure matter more than model choice

---

### 4. Semantic Overlap and Narrative Structure
Unsupervised analysis reveals that:
- Fake and true news share similar topics and vocabulary
- Clusters reflect **narrative themes and rhetorical styles**
- Differences are often subtle (framing, tone, context)

This suggests that misinformation exists along a **continuous semantic spectrum**, rather than as clearly separable categories.

---

### 5. Toward a New Perspective on FND
These findings suggest that fake news detection should not be treated purely as a binary classification problem.
Future research should move toward:

- **Better datasets**
  - multi-domain, multi-source, and multimodal

- **Probabilistic modeling**
  - continuous risk scores instead of binary labels

- **Computational modeling approaches**
  - e.g., Agent-Based Models (ABM) to study spread dynamics

- **Interdisciplinary frameworks**
  - incorporating social, cognitive, and behavioral factors

---

### Key Insight
> High predictive performance in fake news detection does not necessarily imply meaningful semantic understanding.  
> Instead, it may reflect dataset artifacts, stylistic patterns, and underlying structural biases.
