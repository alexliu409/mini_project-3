# Mall Customer Segmentation
## Overview
This project segments mall customers using unsupervised learning to enable targeted marketing strategies. The analysis includes clustering, dimensionality reduction, and anomaly detection to discover customer patterns.

## Problem Description and Motivation
Shopping malls struggle with inefficient marketing when treating all customers the same. Different customer groups have different needs, spending habits, and preferences.

### Key Challenges
- **Segmentation**: Identifying distinct customer groups without labels
- **Targeting**: Understanding what makes each segment unique
- **Resource Allocation**: Focusing marketing budget on high-value customers
- **Anomaly Detection**: Finding unusual customers (VIPs or potential issues)

### Project Goals
This project uses unsupervised learning to:
1. Discover natural customer segments based on behavior
2. Visualize high-dimensional customer data in 2D
3. Identify unusual customers requiring special attention
4. Provide actionable marketing recommendations for each segment

By analyzing demographics and spending patterns, we help malls make data-driven marketing decisions.

## Project Structure
```
mini-project-3/
├── analysis.ipynb                # Main analysis notebook
├── data/
│   └── Mall_Customers.csv        # Customer dataset
├── requirements.txt
└── README.md
```

## Setup Instructions

### 1. Clone or Download the Project
```bash
cd /path/to/mini-project-3
```

### 2. Create Virtual Environment (Recommended)
```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Get the Dataset
Download from [Kaggle](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python) and place in `data/` folder.

### 5. Run the Analysis
```bash
jupyter notebook analysis.ipynb
```
Run all cells sequentially.

## Results Summary

### Customer Segments (K=5)
| Segment | Size | Age | Income | Spending | Strategy |
|---------|------|-----|--------|----------|----------|
| Young Premium | 39 | 33 | $86k | 82 | VIP programs |
| Rich Low-Spenders | 29 | 37 | $90k | 18 | Survey barriers |
| Mature Average | 43 | 50 | $49k | 40 | Loyalty programs |
| Young Spenders | 54 | 25 | $40k | 61 | Payment plans |
| Older Conservative | 35 | 56 | $54k | 37 | Senior discounts |

### Key Findings
- **Biggest Opportunity**: Cluster 1 (Rich Low-Spenders) - high income but minimal spending. Converting 15-20% could significantly boost revenue.
- **Best Customers**: Clusters 0 and 3 - young and engaged. Focus retention here.
- **Anomalies**: 10 detected (5%) - mostly frugal wealthy and elderly minimal shoppers, not errors.

### Methods Used
- **K-Means Clustering**: Optimal K=5 chosen balancing metrics and business practicality
- **Dimensionality Reduction**: PCA, t-SNE, UMAP for visualization
- **Anomaly Detection**: Isolation Forest with 5% contamination

## Team Contributions
- Hsuan Chen Liu - 
- Jia, Yansong - 
