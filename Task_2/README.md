# SCT_ML_2 — Customer Segmentation using K-Means Clustering

## 📌 Overview
This project applies **K-Means Clustering**, an unsupervised machine learning algorithm, to group retail customers into distinct segments based on their **purchase history**. It was completed as **Task 2** of the Machine Learning internship track.

Unlike supervised learning (where the model learns from labeled examples), K-Means discovers hidden patterns and natural groupings in data without any predefined labels — making it ideal for customer segmentation, where we don't know in advance what "types" of customers exist.

## 🎯 Objective
Group retail customers into meaningful segments based on their purchasing behavior, so a business can tailor marketing strategies, loyalty programs, and promotions differently for each group (e.g. VIP customers vs. bargain shoppers vs. at-risk/low-engagement customers).

## 🗂️ Dataset
The notebook is designed to work with real retail customer data such as Kaggle's **"Mall Customer Segmentation Data"** dataset, which includes features like:
- Annual Income
- Spending Score

For this project, a synthetic dataset was generated to simulate realistic purchase-history features:
- `annual_spend` — total amount spent per year
- `purchase_frequency` — number of purchases per year
- `avg_basket_value` — average amount spent per purchase

The synthetic data was designed with 4 underlying customer patterns so the clustering algorithm has genuine structure to discover — mirroring what real purchase-history data typically looks like.

## 🛠️ Tools & Libraries
- **Python 3**
- **pandas** — data manipulation
- **NumPy** — numerical computations
- **Matplotlib** — visualization
- **scikit-learn** — `KMeans`, `StandardScaler`, `silhouette_score`

## 🔍 Project Workflow
1. **Data Loading** — Load customer purchase history data.
2. **Exploratory Data Analysis** — Visualize the distribution of each feature (spend, frequency, basket value).
3. **Feature Scaling** — Standardize features using `StandardScaler`, since K-Means relies on distance calculations and is sensitive to features being on different scales.
4. **Determining Optimal K** — Use two methods to choose the right number of clusters:
   - **Elbow Method** — plotting inertia (within-cluster sum of squares) against different values of k
   - **Silhouette Score** — a more objective metric measuring how well-separated and cohesive the clusters are
5. **Model Training** — Fit the final `KMeans` model with the chosen number of clusters.
6. **Visualization** — Plot the resulting clusters against pairs of features.
7. **Segment Interpretation** — Summarize each cluster's average behavior and assign business-friendly labels (e.g. "VIP customers," "bargain shoppers").

## 📊 Results
- The **Elbow Method** and **Silhouette Score** both pointed to **k = 4** as the optimal number of clusters for this data.
- Four distinct, interpretable customer segments emerged:
  - High spend + high frequency → Loyal/VIP customers
  - High spend + low frequency, high basket value → Occasional big-ticket buyers
  - Low spend + low frequency → Low-engagement/at-risk customers
  - Moderate spend + high frequency, low basket value → Frequent bargain shoppers

## 🚀 How to Run
1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/SCT_ML_2.git
   cd SCT_ML_2
   ```
2. (Optional) Swap in a real dataset such as [Kaggle's Mall Customer Segmentation Data](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python).
3. Open the notebook:
   ```bash
   jupyter notebook kmeans_customer_segmentation.ipynb
   ```
   Or upload it to [Google Colab](https://colab.research.google.com/).
4. Run all cells in order.

## 📁 Project Structure
```
SCT_ML_2/
│
├── kmeans_customer_segmentation.ipynb   # Main notebook
└── README.md                            # Project documentation
```

## 🧠 Key Learnings
- The difference between supervised and unsupervised learning
- Why feature scaling matters for distance-based algorithms like K-Means
- How to choose the right number of clusters using the Elbow Method and Silhouette Score
- How to translate raw cluster statistics into actionable business insights
- The value of visualizing high-dimensional groupings in 2D feature-pair plots

## 🔮 Future Improvements
- Use a real-world dataset with more customer features (recency of last purchase, product category preferences, demographics)
- Apply **PCA (Principal Component Analysis)** to reduce dimensionality and visualize clusters in 2D when more features are used
- Compare K-Means against other clustering algorithms like **DBSCAN** or **Hierarchical Clustering**
- Build a simple dashboard to let business stakeholders explore segments interactively

## 📄 License
This project is open-source and available for learning purposes.

## 🙋 Author
Completed as part of a Machine Learning internship task.
