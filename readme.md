# Customer Value Maximization Pipeline with Segmentation

> Practical pipeline that turns raw transaction logs into actionable customer intelligence using RFM and clustering.

---

## Project Overview

I started this project with a simple question:

> “How can a business truly understand its customers—not just by looking at transactions, but by recognizing real behavior patterns?”

To answer that, I built a **Customer Value Maximization Pipeline**.

It takes raw transaction logs, cleans and transforms them, builds RFM features, compares multiple clustering algorithms, identifies customer segments, and extracts insights a business can actually use.

It’s a practical tool designed to help businesses boost retention, increase revenue, and treat every customer based on their true value.

---

**[READ THE FULL REPORT (PDF)](/Report.pdf)**

## Objectives

The project focused on three core goals:

1. **Transform raw sales data into meaningful customer intelligence** using Recency, Frequency, and Monetary Value (RFM).
2. **Test multiple clustering algorithms** to find the segments that reflect real customer behavior, not arbitrary math.
3. **Extract actionable insights** that a business can immediately apply—upselling, retention, VIP identification, win-back campaigns, and more.

**CORE OBJECTIVE:** To showcase the real power of Data Science: turning messy data into decisions that move businesses forward.

---

## Table of Contents

- [Customer Value Maximization Pipeline with Segmentation](#customer-value-maximization-pipeline-with-segmentation)
  - [Project Overview](#project-overview)
  - [Objectives](#objectives)
  - [Table of Contents](#table-of-contents)
  - [The Business Problem — Why This Matters](#the-business-problem--why-this-matters)
  - [Tech Stack](#tech-stack)
  - [Data Preparation \& Feature Engineering](#data-preparation--feature-engineering)
  - [Model / Algorithm Comparisons](#model--algorithm-comparisons)
    - [1. K-Means Clustering](#1-k-means-clustering)
    - [2. Hierarchical Clustering](#2-hierarchical-clustering)
    - [3. DBSCAN](#3-dbscan)
  - [Key Business Insights](#key-business-insights)
  - [Project Capabilities](#project-capabilities)
  - [Real-World Impact: What This Project Does for a Business](#real-world-impact-what-this-project-does-for-a-business)
  - [How to Run the Project](#how-to-run-the-project)
  - [Author](#author)

---



## The Business Problem — Why This Matters

Most companies look at customers as one huge spreadsheet of transactions. But in reality:

- Some customers are loyal repeat buyers.
- Some show up once, spend big, and never return.
- Some used to love the brand but are drifting away.
- Some are just getting started.

Treating all of them the same means wasted money and missed opportunities.

This project solves that problem by identifying who the customers really are, where they stand in the lifecycle, and how much value each one brings.

In other words: it gives businesses the power to talk to the right customer with the right message at the right time.

---

## Tech Stack

| Category | Technology | Primary Usage in Code |
|---|---:|---|
| Programming Language | Python | Core execution environment for data generation, processing, and modeling |
| Data Manipulation | pandas | Reading/writing CSVs, DataFrame operations, cleaning, RFM calculation (`.groupby().agg()`) |
| Numerical Computing | NumPy | Random generation, numeric transforms (`np.log1p`, etc.) |
| Data Visualization | Matplotlib | Static plots (histograms, elbow plots, scatter plots) |
| Statistical Visualization | Seaborn | Heatmaps, KDE histograms, pair plots, boxplots |
| Machine Learning | scikit-learn | KMeans, DBSCAN, PCA, scaling (`StandardScaler`), metrics (silhouette, Calinski–Harabasz, Davies–Bouldin) |
| Hierarchical Clustering | SciPy | `linkage` (Ward) and `fcluster` for dendrogram-based clustering |

---

## Data Preparation & Feature Engineering

Raw data never comes ready to use — features must be engineered carefully.

- **Cleaning the transaction dataset**
  - Remove duplicates
  - Handle missing values
  - Ensure consistent customer IDs
  - Convert data types
- **Building RFM metrics**
  - **Recency** — how recently a customer bought
  - **Frequency** — how often they purchased
  - **Monetary** — how much they spent

  These three numbers summarize most of what a business needs to know about customer behavior.

- **Log transformations** to reduce the impact of extreme values (e.g., one-time large purchases).
- **Standard scaling** so each metric contributes equally to clustering algorithms.

---

## Model / Algorithm Comparisons

Three clustering algorithms were explored to understand customer groups from different angles.

### 1. K-Means Clustering
- Best overall balance: simple, fast, easy to interpret.
- Produced three clear customer segments.
- **Highest silhouette score** observed: `0.3125`.

### 2. Hierarchical Clustering
- Provided a more detailed view and hierarchical relationships between segments.
- Identified an **“At-Risk Loyalist”** group that K-Means diluted.
- Useful for visualizing segment relationships with a dendrogram.

### 3. DBSCAN
- Good at detecting irregular behavior and outliers.
- Flagged **49 noise customers**, including the dataset’s top spender.
- Revealed extreme or one-off purchase patterns not belonging to stable segments.

**Final Selection:** K-Means (3 clusters) — chosen for clarity, stability, and business-friendly interpretation.

---

## Key Business Insights

1. **Loyal High Spenders** (47% of customers)
   - Highest frequency, highest spending, recently active.
   - → Recommend: VIP programs, early access, exclusive rewards.

2. **Recent Mid-Tier Buyers** (22%)
   - Healthy spending and likely to become loyal.
   - → Recommend: upsells and personalized recommendations.

3. **At-Risk Customers** (31%)
   - Long time since last purchase, low spending, disengaging.
   - → Recommend: targeted discounts and win-back campaigns.

4. **The "Noise" Customers**
   - Extremely unusual buying behavior (one-off bulk purchases or data anomalies).
   - → Recommend: manual review, especially for top spenders.

---

## Project Capabilities

This pipeline can:

- Segment customers using multiple algorithms
- Detect outliers and exceptional behaviors
- Generate insights for marketing, sales, and retention teams
- Scale to larger datasets
- Adapt to other industries (retail, e-commerce, SaaS, banking)

It's built to be reused and modified — not a one-off experiment.

---

## Real-World Impact: What This Project Does for a Business

- Increase revenue by focusing on highest-value customers
- Reduce churn by identifying at-risk segments early
- Personalize marketing based on customer behavior
- Spend smarter on promotions
- Improve customer satisfaction through targeted engagement

Instead of blanket marketing, a business can act with precision.

---

## How to Run the Project

1. Clone the repository:

```bash
git clone [https://github.com/yourusername/Customer-Value-Maximization.git](https://github.com/hannanbaig347/customer-value-maximization-pipeline-with-segmentation)
```

2. Navigate to the folder:

```bash
cd Customer-Value-Maximization
```

3. Install the required packages:

```bash
pip install -r requirements.txt
```

4. Open the notebook:

```bash
jupyter notebook
```

Run the pipeline step-by-step inside the notebook. The notebook contains cells for data cleaning, RFM calculation, visualization, clustering experiments, and summary outputs ready for export.

---

## Author

- **Author:** Hannan Baig
- **Education:** MS Computer Science (NUST)
- **Work / Focus:** Thesis on AI-driven Air Pollution Estimation | Data Science at Kangaroo Ventures

**Contact**

- Email: `muhammadhannanbaig@gmail.com`
- GitHub: `github.com/hannanbaig347`
- LinkedIn: [`Hannan Baig`](https://www.linkedin.com/in/hannan-baig-b10320325/)

