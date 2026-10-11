# Ford Car Price Prediction Using Linear Regression

## Overview

This learning project uses Linear Regression to predict Ford car prices from vehicle-related features in the Ford car dataset.

## Dataset

- **Source:** [Ford Car Price Prediction dataset on Kaggle](https://www.kaggle.com/datasets/adhurimquku/ford-car-price-prediction)
- **File:** `ford.csv`
- **Kaggle notebook:** [Open notebook](https://www.kaggle.com/code/ayush0428/notebook614e35ec78)

The original notebook uses a Kaggle input path. If running locally, download the dataset from Kaggle and update the file path accordingly.

## Algorithm

**Linear Regression** — a supervised regression algorithm used to estimate a continuous target such as vehicle price.

## Workflow

1. Load and inspect the dataset.
2. Explore and prepare features for modelling.
3. Train a Linear Regression model.
4. Test the trained model.
5. Report evaluation metrics from the notebook.

## Evaluation

The notebook currently reports an R² score of **0.8397** for the one-hot-encoded feature set and **0.7310** for the label-encoded feature set (test split: 33%, random_state=42). These are the values recorded in the saved notebook outputs; rerun the notebook after addressing the preprocessing notes below to confirm the final metrics.

### Preprocessing notes

- The current notebook scales features before the train/test split, which can cause data leakage. Split first, then fit preprocessing only on the training data (ideally using a scikit-learn Pipeline/ColumnTransformer).
- The one-hot-encoded data is converted to integers before scaling, which truncates decimal values such as `mpg` and `engineSize`. Avoid converting the entire encoded DataFrame to `int`.
- The notebook experiments with both one-hot encoding and label encoding. For nominal categories such as car model, fuel type, and transmission, one-hot encoding is generally a more appropriate baseline for Linear Regression.

## Run the Notebook

1. Download `ford.csv` from the linked Kaggle dataset.
2. Open `ford_car_price_prediction.ipynb` in Jupyter Notebook or Google Colab.
3. Update the dataset path to match your environment.
4. Run the notebook cells in order.

## Libraries

List the libraries actually imported by the notebook (for example, Pandas, NumPy, Matplotlib, Seaborn, and Scikit-learn).

## Learning Outcomes

- Practise exploratory data analysis and data preparation.
- Train a baseline regression model.
- Understand why regression evaluation metrics matter.
