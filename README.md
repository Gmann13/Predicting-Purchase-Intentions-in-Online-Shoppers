
# From Browsing to Buying: Predicting Purchase Intentions in Online Shoppers

## Overview
In the rapidly growing e-commerce industry, understanding and predicting consumer behavior is crucial for businesses to optimize their strategies. This project focuses on using machine learning techniques to predict whether an online shopper will make a purchase. By analyzing user session data, this project provides insights that help e-commerce platforms personalize user experiences, improve marketing strategies, and enhance sales conversion rates.

## Importance of Predicting Purchase Intentions
1. **Personalized Marketing**: Enables businesses to tailor their advertisements and recommendations based on user behavior.
2. **Customer Retention**: Identifying potential buyers allows businesses to allocate resources effectively to retain customers.
3. **Competitive Edge**: Data-driven decision-making supports businesses in staying ahead in a competitive market.
4. **Resource Optimization**: Helps prioritize high-value users, improving efficiency in marketing and operational efforts.

---

## Dataset Description
The dataset, sourced from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/468/online+shoppers+purchasing+intention+dataset), contains 12,330 observations and 18 features, including:

1. **Administrative and Informational Pages**: Count and duration of visits.
2. **Product-Related Pages**: Count and time spent on product-related pages.
3. **Bounce and Exit Rates**: Metrics reflecting user engagement.
4. **Page Value**: Monetary value of visited pages before completing a purchase.
5. **Special Day**: Proximity to holidays or events influencing behavior.
6. **Technical Features**: Operating system, browser, region, and traffic type.
7. **Temporal Features**: Session month, weekend indicator.
8. **Target Variable**: **Revenue** (1: Purchase, 0: No Purchase).

---

## Methods and Workflow

### **1. Exploratory Data Analysis (EDA)**
- **Null Values**: Dataset contains no missing values.
- **Distribution Analysis**:
  - Most features are skewed; log transformation was applied to handle skewness.
- **Correlation Analysis**:
  - Used Pearson correlation for numerical features and Cramér’s V for categorical features.
  - Identified redundant features and optimized feature selection.
- **Outlier Analysis**:
  - Outliers were attributed to skewed data rather than noise, so they were retained.
- **Feature Engineering**:
  - Created new features by combining correlated attributes (e.g., average of Bounce and Exit Rates).
  - Dropped less relevant features like redundant counts (Administrative, Informational).

### **2. Machine Learning Models**
1. **Logistic Regression**:
   - A supervised classification algorithm predicting binary outcomes.
   - Achieved a **ROC AUC** score of **0.87**.

2. **Naïve Bayes**:
   - Assumes independence among features.
   - Performed with an **ROC AUC** score of **0.60**.

3. **Support Vector Machines (SVM)**:
   - Hard Margin SVM achieved the best **ROC AUC** score of **0.92**.
   - Soft Margin SVM performed slightly lower with an **ROC AUC** score of **0.89**.

### **3. Hyperparameter Tuning**
- Logistic Regression: Tuned lambda and maximum iterations.
- SVM: Optimized C parameter and number of iterations.
- Bias-Variance Tradeoff: Adjusted hyperparameters to balance overfitting and underfitting.

---

## Key Findings
1. **Session Behavior**:
   - High engagement (more time on Product-Related pages) strongly correlates with purchase likelihood.
2. **Special Events**:
   - Sessions near special days see higher purchase probabilities.
3. **Technical Features**:
   - Returning visitors and specific traffic types indicate higher purchase intentions.
4. **Optimal Features**:
   - Feature engineering and correlation analysis improved model performance by reducing redundancy.

---

## Results
| Model               | ROC AUC Score |
|---------------------|---------------|
| Naïve Bayes         | 0.60          |
| Logistic Regression | 0.87          |
| Hard Margin SVM     | 0.92          |
| Soft Margin SVM     | 0.89          |

---

## Conclusion
The **Support Vector Machine (Hard Margin)** model performed the best, showcasing its ability to effectively handle high-dimensional data and provide accurate predictions. This project highlights the potential of machine learning in transforming e-commerce strategies by providing actionable insights into user behavior.

---

## Future Enhancements
1. **Real-Time Predictions**: Implement models for real-time prediction of user behavior.
2. **Feature Expansion**: Incorporate additional features like social media influence, device type, or promotional codes.
3. **Deep Learning Models**: Experiment with neural networks for more complex behavior prediction.
4. **Scalability**: Apply the model to larger datasets from other e-commerce platforms.

