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

### Anomalies: 
10 anomalies detected with contamination=0.05, categorized into 3 types:
-**Low Spenders with Average/High Income:** High income but very low spending, possibly frugal high-earners or new customers
-**Older, Very Low Spenders with Low/Average Income:** Elderly customers with low income and spending, likely minimalists or disengaged shoppers
-**Younger, Low Spenders with Low Income:** Budget-conscious young shoppers with limited income

### Business Insights:
The customer segmentation results provide clear guidance for targeted marketing strategies. Cluster 0 (high-income, high-spending young customers) is the core high-value group and should be prioritized for premium product promotions and loyalty programs. Cluster 1 (high-income, low-spending customers) has great potential for upselling, and personalized marketing campaigns can be designed to stimulate their consumption. Cluster 3 (young, low-income, medium-spending customers) is suitable for affordable and trendy product recommendations.
The detected anomalies reveal two key business opportunities and risks. On one hand, the high-income but low-spending anomalies can be targeted with exclusive offers to convert them into regular high-spenders. On the other hand, the elderly low-spending anomalies may need tailored services such as convenient shopping channels to improve their engagement. Additionally, these anomalies can also help identify potential data errors or fraudulent transactions, enhancing the mall's operational risk management.

### Dimensionality Reduction

- **PCA:** 57.1% variance captured (PC1: 32.2%, PC2: 25.0%), shows some cluster overlap
- **t-SNE:** Much clearer cluster separation — confirms K=5 is solid
- **Conclusion:** Data has non-linear structure (income-spending interactions are curved). t-SNE validates the 5 clusters are real, not statistical noise.

## Team Contributions
- Hsuan Chen Liu - Data preprocessing, K selection, cluster analysis, Dimensionality reduction, Technical Report
- Jia, Yansong - Anomaly detection, visualizations, integration and analysis, Technical Report

