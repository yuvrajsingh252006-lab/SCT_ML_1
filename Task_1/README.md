# SCT_ML_1 — House Price Prediction using Linear Regression

## 📌 Overview
This project implements a **Linear Regression** model to predict house prices based on three key property features: **square footage**, **number of bedrooms**, and **number of bathrooms**. It was completed as **Task 1** of the Machine Learning internship track.

Linear regression is one of the most fundamental algorithms in machine learning and statistics. It models the relationship between one or more independent variables (features) and a dependent variable (target) by fitting a straight line (or in this case, a hyperplane, since we have multiple features) that minimizes the difference between predicted and actual values.

## 🎯 Objective
Given a house's square footage, number of bedrooms, and number of bathrooms, predict its sale price as accurately as possible using a supervised regression model.

## 🗂️ Dataset
The notebook is built to work with **Kaggle's "House Prices: Advanced Regression Techniques"** dataset, which includes real housing data with features like:
- `GrLivArea` — above-ground living area (square footage)
- `BedroomAbvGr` — number of bedrooms above ground
- `FullBath` — number of full bathrooms
- `SalePrice` — the target variable

For demonstration purposes, the notebook also includes a synthetic data generator so it can run end-to-end without requiring an external file download. Swapping in the real dataset only requires replacing one cell with a `pd.read_csv(...)` call and renaming the relevant columns.

## 🛠️ Tools & Libraries
- **Python 3**
- **pandas** — data manipulation and analysis
- **NumPy** — numerical computations
- **Matplotlib** — data visualization
- **scikit-learn** — model training (`LinearRegression`), train/test splitting, and evaluation metrics

## 🔍 Project Workflow
1. **Data Loading** — Load the dataset (real or synthetic) into a pandas DataFrame.
2. **Exploratory Data Analysis (EDA)** — Examine summary statistics, check correlations between features and price, and visualize relationships using scatter plots.
3. **Train/Test Split** — Split the data into 80% training and 20% testing sets to evaluate the model on unseen data.
4. **Model Training** — Fit a `LinearRegression` model on the training data.
5. **Coefficient Interpretation** — Examine the learned coefficients to understand how much each feature contributes to the predicted price.
6. **Model Evaluation** — Assess performance using:
   - **Mean Absolute Error (MAE)**
   - **Root Mean Squared Error (RMSE)**
   - **R² Score** (coefficient of determination)
7. **Prediction** — Use the trained model to predict the price of a new, hypothetical house.

## 📊 Results
On the demonstration dataset, the model achieved:
- **R² Score:** ~0.89 (explains ~89% of the variance in house prices)
- Reasonable MAE and RMSE values relative to the price range in the dataset

*(Results will differ when run on the real Kaggle dataset — real-world housing data has more noise and unmodeled factors like location, so R² is often somewhat lower, typically in the 0.6–0.8 range for a simple 3-feature model.)*

## 🚀 How to Run
1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/SCT_ML_1.git
   cd SCT_ML_1
   ```
2. (Optional) Download the real dataset from [Kaggle House Prices: Advanced Regression Techniques](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data) and place `train.csv` in the project folder.
3. Open the notebook:
   ```bash
   jupyter notebook linear_regression_house_prices.ipynb
   ```
   Or upload it to [Google Colab](https://colab.research.google.com/).
4. Run all cells in order (Cell → Run All).

## 📁 Project Structure
```
SCT_ML_1/
│
├── linear_regression_house_prices.ipynb   # Main notebook
└── README.md                              # Project documentation
```

## 🧠 Key Learnings
- How to structure an end-to-end supervised regression workflow
- The importance of train/test splitting to avoid overfitting and get an honest performance estimate
- How to interpret linear regression coefficients in a real-world context
- The difference between MAE, RMSE, and R², and when each metric matters
- Why exploratory data analysis is a critical first step before modeling

## 🔮 Future Improvements
- Incorporate additional features (lot size, year built, location/neighborhood, garage size, etc.)
- Handle outliers and missing data more rigorously
- Compare against regularized models like **Ridge** and **Lasso** regression
- Try polynomial features to capture non-linear relationships
- Perform feature scaling and cross-validation for more robust evaluation

## 📄 License
This project is open-source and available for learning purposes.

## 🙋 Author
Completed as part of a Machine Learning internship task.
