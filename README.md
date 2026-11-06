# 📦 Supply Chain Analysis Using Python

## 📌 Project Overview

This project focuses on analyzing supply chain operations using Python to identify delivery delays, evaluate profitability, discover operational bottlenecks, and predict late-delivery risks using Machine Learning.

The project uses the DataCo Supply Chain dataset and applies data cleaning, exploratory data analysis (EDA), feature engineering, data visualization, and a Random Forest classification model.

The goal is to transform raw supply chain data into meaningful business insights that can help improve delivery performance and operational efficiency.

## 🎯 Project Objectives

- Analyze overall supply chain and delivery performance.
- Identify patterns in late deliveries.
- Evaluate order profitability and loss-making records.
- Analyze delivery performance across regions and shipping modes.
- Identify potential operational bottlenecks.
- Perform time-based delivery trend analysis.
- Build a Machine Learning model to predict late-delivery risk.
- Generate actionable business recommendations.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming and analysis |
| Pandas | Data cleaning and manipulation |
| NumPy | Numerical computations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Scikit-learn | Machine Learning |
| Jupyter Notebook | Development environment |

## 📂 Project Structure

```text
Supply-Chain-Analysis-Using-Python/
│
├── notebooks/
│   └── Supply_Chain_Analysis_Project_Using_Python_.ipynb
│
├── data/
│   └── README.md
│
├── images/
│   ├── profitability_analysis.png
│   ├── delivery_performance.png
│   ├── delay_analysis.png
│   ├── regional_analysis.png
│   ├── confusion_matrix.png
│   └── feature_importance.png
│
├── README.md
├── requirements.txt
└── .gitignore
```

## 📊 Dataset Information

**Dataset:** DataCo Supply Chain Dataset

The dataset contains information related to:

- Customer details and segments
- Order information
- Product categories
- Sales and profitability
- Shipping modes
- Order regions and markets
- Scheduled and actual shipping durations
- Late-delivery risk

**Dataset dimensions:**

| Description | Value |
|---|---:|
| Original records | 27,836 |
| Original columns | 53 |
| Records after cleaning | 27,472 |
| Columns after preprocessing | 32 |

Note: The original dataset is not included in this repository. Refer to `data/README.md` for dataset setup instructions.

## 🔍 Project Workflow

### 1. Data Loading and Understanding

- Imported the dataset using Pandas.
- Inspected dataset dimensions and column names.
- Checked missing values and duplicate records.
- Examined data types and statistical summaries.

### 2. Data Cleaning and Preprocessing

- Removed unnecessary columns.
- Excluded canceled orders.
- Converted date columns into datetime format.
- Checked missing values and data consistency.
- Prepared the dataset for further analysis.

### 3. Feature Engineering

Created additional features to improve business analysis:

- Order Processing Time
- Delivery Delay
- Is Delayed
- Order Month
- Order Day
- Order Hour
- Profitability Classification

### 4. Exploratory Data Analysis (EDA)

Performed analysis across multiple business dimensions.

**A. Profitability Analysis**
- Profit vs. Loss distribution.
- Profitability classification.
- Analysis of positive and negative profit ratios.

**B. Delivery Performance Analysis**
- Total delivery records.
- Late-delivery percentage.
- On-time/early delivery percentage.
- Delay distribution.
- 90th percentile delay.

**C. Delay and Profit Analysis**
- Relationship between delivery delays and profitability.
- Profit ratio distribution across delay categories.

**D. Bottleneck Analysis**

Analyzed delivery performance across:

- Order Region
- Customer Segment
- Shipping Mode
- Department Name
- Order Type
- Market

**E. Root-Cause Analysis**

Investigated delivery delays in Central Africa across shipping modes, customer segments, departments, order types, and product categories.

**F. Time-Based Analysis**

Analyzed delivery trends by:

- Order Month
- Day of the Week
- Order Hour

### 5. Machine Learning – Late Delivery Prediction

Implemented a Random Forest Classifier to predict late-delivery risk.

**Model development steps:**

1. Selected relevant independent variables.
2. Defined `Late_delivery_risk` as the target variable.
3. Applied frequency encoding to categorical variables.
4. Split data into 80% training and 20% testing.
5. Applied StandardScaler.
6. Trained a Random Forest classification model.
7. Evaluated model performance using classification metrics.

**Model configuration:**

```python
RandomForestClassifier(
    n_estimators=200,
    max_depth=12,
    min_samples_leaf=10,
    class_weight="balanced",
    random_state=42,
    n_jobs=-1
)
```

## 📈 Key Business Insights

The following results are based on the current notebook implementation.

| Business Metric | Result |
|---|---:|
| Analyzed records | 27,472 |
| Late-delivery percentage | 56.54% |
| On-time/early percentage | 43.46% |
| 90th percentile delay | 3 days |
| Positive profit-ratio records | 80.74% |
| Negative profit-ratio records | 18.64% |
| Break-even records | 0.61% |

### Major Findings

1. More than half of the analyzed records were classified as delayed, highlighting an opportunity to investigate delivery performance.
2. Approximately 18.64% of records had negative profit ratios, indicating areas for profitability improvement.
3. Delivery performance varied across shipping modes, regions, customer segments, and departments.
4. Some product categories and shipping modes in Central Africa showed high observed delay percentages.
5. Time-based analysis provided opportunities to investigate monthly, weekday, and hourly delivery patterns.

## 🤖 Machine Learning Model Performance

The Random Forest model achieved the following evaluation results:

| Evaluation Metric | Score |
|---|---:|
| Accuracy | 73.28% |
| Precision | 91.00% |
| Recall | 59.62% |
| F1 Score | 72.04% |
| ROC-AUC | 81.32% |

**Model interpretation:**

The model achieved high precision, meaning its positive late-risk predictions were relatively reliable. However, recall indicates that some actual late-risk records were missed.

Further model optimization could focus on improving recall and identifying more potentially delayed shipments.

## 💡 Business Recommendations

Based on the analysis, the following actions could help improve supply chain operations:

1. **Improve Delivery Efficiency:** Investigate shipping modes and regions with high delay rates.
2. **Optimize Order Processing:** Review order processing and dispatch operations.
3. **Improve Profitability:** Investigate loss-making products and orders.
4. **Monitor Regional Performance:** Track delivery KPIs across regions and markets.
5. **Predict Delivery Risks:** Use machine learning predictions to support proactive shipment monitoring.
6. **Continuous Monitoring:** Regularly monitor delivery performance and profitability KPIs.

## 🚀 How to Run This Project

### Step 1: Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/Supply-Chain-Analysis-Using-Python.git
```

### Step 2: Navigate to the project directory

```bash
cd Supply-Chain-Analysis-Using-Python
```

### Step 3: Install dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Download and configure the dataset

Place `DataCoSupplyChainDataset.csv` in the project directory or update the dataset path in the notebook.

The original notebook currently uses a Google Colab path:

```python
df = pd.read_csv(
    "/content/DataCoSupplyChainDataset.csv",
    encoding="latin1"
)
```

Update this path according to your local environment.

### Step 5: Run the Jupyter Notebook

```bash
jupyter notebook
```

Open the notebook inside the `notebooks/` folder and execute the cells.

## 📌 Skills Demonstrated

- Data Cleaning and Preprocessing
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Business KPI Analysis
- Data Visualization
- Root-Cause Analysis
- Statistical Analysis
- Machine Learning
- Classification
- Model Evaluation
- Business Insights and Recommendations

## 👨‍💻 Author

**Aman Jayswal**

Aspiring Data Analyst | Python | SQL | Power BI | Excel

[GitHub](https://github.com/Amanjayswal500)

---

⭐ If you find this project useful, consider giving this repository a star!
