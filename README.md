# Mall Customer Segmentation Project
**COMP 9130 - Mini Project 3**

---

## Problem Description

### Business Problem
The mall wants to segment customers for targeted marketing instead of treating everyone the same.

### Why Unsupervised Learning?
We don't have customer labels. Unsupervised learning finds natural groups, spots unusual customers, and shows hidden patterns.

---

## Project Structure

```
mini-project-3/
├── data/Mall_Customers.csv
├── analysis.ipynb
├── requirements.txt
└── README.md
```

## Dataset

**Source:** [Kaggle Mall Customers](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python)  
**Size:** 200 customers, 5 features

### Features
- CustomerID: Unique ID (not used)
- Gender: Male/Female
- Age: 18-70 years
- Annual Income (k$): Income in thousands
- Spending Score (1-100): Mall rating of spending behavior

### Preprocessing
- Gender encoded (Male=0, Female=1)
- Dropped CustomerID
- Standardized all features with StandardScaler

---

## Setup

### Install
```bash
pip install numpy pandas matplotlib seaborn scikit-learn umap-learn jupyter
```

### Run
```bash
jupyter notebook analysis.ipynb
```

---

## Results

### Optimal K: 5
**Why:** K=5 (silhouette: 0.304) is more practical than K=10 (silhouette: 0.421). Five segments are manageable for marketing teams.

### Customer Segments

| # | Name | Size | Age | Income | Spending | Strategy |
|---|------|------|-----|--------|----------|----------|
| 0 | Young Premium | 39 | 33 | $86k | 82 | VIP programs |
| 1 | Rich Low-Spenders | 29 | 37 | $90k | 18 | Find out why |
| 2 | Mature Average | 43 | 50 | $49k | 40 | Loyalty deals |
| 3 | Young Spenders | 54 | 25 | $40k | 61 | Payment plans |
| 4 | Older Conservative | 35 | 56 | $54k | 37 | Senior discounts |

### Anomalies: 10 found (5% contamination)

**Types:**
- **Frugal Rich (3):** High income but very low spending
- **Elderly Minimal (6):** Older people who rarely shop
- **Budget Youth (1):** Young with very low spending

**Where:** Most in Cluster 1 (10.3%) and Cluster 4 (8.6%)

### Key Findings

**Biggest Opportunity:** Cluster 1 has money but doesn't spend. Survey them to find out why. Could increase revenue 15-20%.

**Best Customers:** Clusters 0 and 3 are young and engaged. Keep them happy for long-term success.

**Anomalies:** Mostly real patterns (careful elderly, cautious rich) not data errors. Need special treatment.

---

## Team Contributions

**[Your Name]:**
- Data loading and preprocessing
- K-means clustering
- K selection and cluster analysis
- README

**[Partner Name]:**
- PCA, t-SNE, UMAP
- Anomaly detection
- Integration analysis
- Visualizations

---




**Questions?** Contact [your-email]
