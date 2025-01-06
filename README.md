# <span style="color:Navy">**MLM Project 2: Supervised Learning Models on Import-Export Dataset using Python**</span>

---

## <span style="color:Navy">**PROJECT CONTENTS:**</span>
1. Project Information
2. Description of Data
3. Data Sampling
4. Project Objectives | Problem Statements
5. Exploratory Data Analysis
6. Model Evaluation
7. Observations | Findings
8. Managerial Insights | Recommendations
9. Key Features and Contributions

---

## 1. <span style="color:Navy">**Project Information**</span>
- **Title**: Data Exploration with Python using Pandas & Numpy Libraries  
- **Prepared By**: Amitanshu Tiwari (055054)

---

## 2. <span style="color:Navy">**Description of Data**</span>
- **Data Source**: [Imports-Exports Dataset](https://www.kaggle.com/datasets/chakilamvishwas/imports-exports-15000)
- **Data Columns Description**:
  - **Transaction_ID**: Unique identifier for each trade transaction.
  - **Country**: Country of origin or destination for the trade.
  - **Product**: Product being traded.
  - **Import_Export**: Indicates whether the transaction is an import or export.
  - **Quantity**: Amount of the product traded.
  - **Value**: Monetary value of the product in USD.
  - **Date**: Date of the transaction.
  - **Category**: Category of the product (e.g., Electronics, Clothing, Machinery).
  - **Port**: Port of entry or departure.
  - **Customs_Code**: Customs or HS code for product classification.
  - **Weight**: Weight of the product in kilograms.
  - **Shipping_Method**: Method used for shipping (e.g., Air, Sea, Land).
  - **Supplier**: Name of the supplier or manufacturer.
  - **Customer**: Name of the customer or recipient.
  - **Invoice_Number**: Unique invoice number for the transaction.
  - **Payment_Terms**: Terms of payment (e.g., Net 30, Net 60, Cash on Delivery).
- **Data Type**: Panel Data (longitudinal data).
- **Variables**:
  - Integer: Quantity, Customs_Code, Invoice_Number
  - Float: Value, Weight
  - Text: 9 categorical variables
  - DateTime: Date

---

## 3. <span style="color:Navy">**Data Sampling**</span>
- **Dataset Sample**: From 15,000 records, a sample of 5001 entries (`at54_sample`) was extracted.
- **Variables**:
  - Index Variables: Transaction_ID, Invoice_Number
  - Categorical Variables:
    - Nominal: Country, Product, Import_Export, Category, Port, Shipping_Method, Supplier, Customs_Code, Customer
    - Ordinal: Payment_Terms
  - Non-Categorical Variables: Quantity, Value, Weight

---

## 4. <span style="color:Navy">**Project Objectives**</span>
1. Classification of the dataset into segments, clusters, or classes using supervised learning algorithms.
2. Identification of important variables or features and their thresholds for classification.
3. Determination of the most appropriate classification model based on performance metrics.

---

## 5. <span style="color:Navy">**Exploratory Data Analysis**</span>
### 5.1 Data Preprocessing
- No missing data treatment was required as there were no missing values.
- Ordinal Encoder was used for encoding categorical variables.
- Min-Max Scaler was applied to scale numerical variables.

### 5.2 Descriptive Statistics
- **Non-Categorical Variables**:
  - Central Tendency: Minimum, Maximum, Mean, Median, Mode
  - Dispersion: Range, Standard Deviation, Skewness, Kurtosis
  - Correlation Matrix
- **Categorical Variables**:
  - Count, Frequency, Proportion, Mode

### 5.3 Data Visualization
- Visualized using bar charts, heatmaps, histograms, and correlation matrices.

### 5.4 Inferential Statistics
- Categorical Variables: Test of Homogeneity (Chi-sq)
- Non-Categorical Variables: Test of Normality (Shapiro-Wilk, Kolmogorov-Smirnov, Anderson-Darling, Jarque-Bera)

### 5.5 Machine Learning Models
- Logistic Regression (LR)
- Support Vector Machines (SVM)
- Stochastic Gradient Descent (SGD)
- Decision Trees (DT)
- K-Nearest Neighbors (KNN)
- Naive Bayes (NB)
- Bagging: Random Forest
- Boosting: XGBoost

---

## 6. <span style="color:Navy">**Model Evaluation**</span>
### 6.1 Performance Metrics
| Model                 | Accuracy  | Precision | Recall | F1-Score |
|-----------------------|-----------|-----------|--------|----------|
| Logistic Regression   | 0.3298    | 0.33      | 0.33   | 0.32     |
| Support Vector Machine| 0.3324    | 0.33      | 0.33   | 0.33     |
| Decision Tree         | 0.3331    | 0.33      | 0.33   | 0.33     |
| K-Nearest Neighbors   | 0.3198    | 0.32      | 0.32   | 0.31     |
| Naive Bayes           | 0.3112    | 0.31      | 0.31   | 0.30     |
| Random Forest         | 0.3491    | 0.35      | 0.35   | 0.34     |
| XGBoost               | 0.3438    | 0.34      | 0.34   | 0.34     |

The table outlines the evaluation metrics for different machine learning models:

1. **Accuracy**:
   - Reflects the proportion of correctly classified instances among all instances.
   - **Random Forest** achieves the highest accuracy (34.91%), followed by **XGBoost** (34.38%).
   - **Naive Bayes** has the lowest accuracy (31.12%).

2. **Precision**:
   - Measures the ratio of true positive predictions to the total predicted positives.
   - Values are consistent across models, with **Random Forest** and **XGBoost** having slightly better precision.

3. **Recall**:
   - Indicates the ability of the model to identify all relevant instances.
   - Models like **Random Forest** and **XGBoost** outperform others.

4. **F1-Score**:
   - Harmonic mean of Precision and Recall, providing a balanced evaluation metric.
   - **Random Forest** leads with a higher F1-Score (0.34).

### 6.2 Runtime
| Model                 | Runtime (s) |
|-----------------------|-------------|
| Logistic Regression   | 0.0155      |
| Support Vector Machine| 0.9777      |
| SGD                   | 0.0485      |
| Decision Tree         | 0.0534      |
| K-Nearest Neighbors   | 0.0062      |
| Naive Bayes           | 0.0049      |
| Random Forest         | 1.5991      |
| XGBoost               | 0.5870      |

he runtime table highlights the computational speed of each model:

1. **Fastest Models**:
   - **Naive Bayes** (0.0049 seconds) and **KNN** (0.0062 seconds) are the quickest, making them ideal for scenarios where rapid processing is needed.

2. **Slowest Models**:
   - **Random Forest** (1.5991 seconds) and **SVM** (0.9777 seconds) are computationally expensive, requiring significantly more time.

3. **Balanced Models**:
   - Models like **Logistic Regression** (0.0155 seconds) and **SGD** (0.0485 seconds) offer a compromise between speed and computational demand.


### 6.3 Memory Usage
| Model                 | Memory (MB) |
|-----------------------|-------------|
| Logistic Regression   | 0.34        |
| Support Vector Machine| 0.27        |
| SGD                   | 0.18        |
| Decision Tree         | 0.22        |
| K-Nearest Neighbors   | 0.22        |
| Naive Bayes           | 0.11        |
| Random Forest         | 0.61        |
| XGBoost               | 0.85        |

This table evaluates the resource consumption of models in terms of memory:

1. **Least Memory Usage**:
   - **Naive Bayes** (0.11 MB) and **SGD** (0.18 MB) are highly memory-efficient, suitable for resource-constrained environments.

2. **High Memory Usage**:
   - **XGBoost** (0.85 MB) and **Random Forest** (0.61 MB) require more memory but offer better performance.

3. **Moderate Usage**:
   - **Logistic Regression** (0.34 MB) and **Decision Tree** (0.22 MB) balance memory efficiency and performance.


These tables emphasize the trade-offs in model selection:
- **High Accuracy**: Random Forest and XGBoost are preferable but are slower and require more memory.
- **Quick Analysis**: Naive Bayes and KNN are optimal for speed but compromise accuracy.
- **Balanced Use**: Logistic Regression and Decision Tree provide a good balance across metrics.

---

## 7. <span style="color:Navy">**Observations | Findings**</span>
1. **Best Model:** Random Forest with 34.91% accuracy.
2. **Fastest Models:** KNN and Naive Bayes.
3. **Memory Efficient Models:** Naive Bayes and SGD.

---

## 8. <span style="color:Navy">**Managerial Insights | Recommendations**</span>
1. For high accuracy, use Random Forest or XGBoost.
2. For quick analysis, consider KNN or Naive Bayes.
3. Address class imbalance using oversampling, undersampling, or SMOTE.

---

## 9. <span style="color:Navy">**Key Features and Contributions**</span>
- **Important Features:** Country, Product, Quantity, Value, Shipping_Method.
- **Model Contributions:**
  - Random Forest: High accuracy with significant feature utilization.
  - XGBoost: Highlighted Product and Country importance.

---

