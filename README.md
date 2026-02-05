# Mini Project 3: Mall Customer Segmentation

**COMP 9130 - Applied Artificial Intelligence**  
**Team:** [Hsuan Chen Liu], [Jia, Yanson]

---


## Problem Description

A mall wants to understand its 200 customers better to create targeted marketing campaigns. We use unsupervised learning to discover natural customer groups based on age, income, spending patterns, and gender. This approach works because we don't have pre-labeled customer types — we're discovering hidden segments in the data.

## Dataset

**Source:** [Kaggle - Mall Customer Segmentation](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python)

- **Size:** 200 customers
- **Features:** Age, Annual Income (k$), Spending Score (1-100), Gender
- **Preprocessing:** Dropped CustomerID, encoded Gender (Male=0, Female=1), standardized all numerical features with StandardScaler
- **No missing values**

## Project Structure
```
mini-project-3/
├── analysis.ipynb                # Main analysis notebook
├── data/
│   └── Mall_Customers.csv        # Customer dataset
├── requirements.txt
└── README.md
```

## Setup

```bash
# Clone repo
git clone https://github.com/[your-username]/mini-project-3.git
cd mini-project-3

# Install packages
pip install pandas numpy matplotlib seaborn scikit-learn

# Run notebook
jupyter notebook analysis.ipynb
```

Put `Mall_Customers.csv` in the same folder as the notebook.

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

### Dimensionality Reduction

- **PCA:** 57.1% variance captured (PC1: 32.2%, PC2: 25.0%), shows some cluster overlap
- **t-SNE:** Much clearer cluster separation — confirms K=5 is solid
- **Conclusion:** Data has non-linear structure (income-spending interactions are curved). t-SNE validates the 5 clusters are real, not statistical noise.

## Team Contributions
- Hsuan Chen Liu - Data preprocessing, clustering, K selection, cluster analysis
- Jia, Yansong - Dimensionality reduction, anomaly detection, visualizations, integration

