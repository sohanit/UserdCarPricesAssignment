### **README: Used Car Price Prediction and Analysis**

#### **Project Overview**
This project aims to identify the key drivers of used car prices in the market and build predictive models to estimate car prices based on various attributes. Using a dataset of used car listings, we performed data cleaning, feature engineering, exploratory analysis, and machine learning modeling to address the business question: *What factors drive used car prices?*

---

#### **Dataset**
- **Source**: `vehicles.csv`
- **Columns**:
  - `price`: Target variable representing the car's price.
  - `age`, `odometer`, `condition`, `manufacturer`, `fuel`, `drive`, etc.: Features used for analysis and modeling.

---

#### **Steps Followed**

1. **Data Cleaning**:
   - Removed rows with missing critical features (e.g., `price`, `year`, `odometer`).
   - Imputed missing values for categorical (`drive`, `condition`) and numeric (`cylinders`) columns.
   - Handled outliers in numeric columns like `price` and `odometer`.

2. **Feature Engineering**:
   - Created new features, such as:
     - `age`: Derived from the car's year of manufacture.
     - `is_luxury`: Binary feature indicating whether the manufacturer is a luxury brand.
   - Normalized categorical columns (e.g., `condition`) for consistency.

3. **Exploratory Data Analysis (EDA)**:
   - Analyzed relationships between features (e.g., `age`, `odometer`, `condition`) and price using scatterplots and boxplots.
   - Identified that **age** and **odometer** are the strongest predictors of price.

4. **Modeling**:
   - Built multiple regression models to predict car prices:
     - Linear Regression
     - Ridge Regression
     - Lasso Regression
     - Random Forest Regressor
   - Used cross-validation and hyperparameter tuning (via RandomizedSearchCV) to optimize model performance.

5. **Key Results**:
   - The Random Forest model performed best with an $$ R^2 $$ score of **0.850**, MAE of **$2,873**, and MSE of **$27,848,130**.
   - Feature importance analysis revealed that:
     - **Age** (49%) and **Odometer** (14%) are the most influential features.
     - Other important features include drivetrain (`drive_fwd`), engine characteristics (`cylinders`, `fuel_diesel`), and condition.

---

#### **Key Findings**
1. **Top Drivers of Price**:
   - Newer cars with lower mileage command higher prices.
   - Cars in better condition (`excellent`, `like new`) are priced higher than those in fair or salvage condition.
   - Luxury brands (e.g., BMW, Audi) have a premium value but are less influential compared to age/mileage.

2. **Model Performance**:
   - Random Forest outperformed linear models due to its ability to capture nonlinear relationships between features and price.

3. **Business Insights**:
   - Sellers should highlight low mileage, good condition, and luxury branding to maximize resale value.
   - Buyers can use this model to assess whether a listed price is reasonable based on key attributes.

---

#### **How to Use This Project**
1. Clone this repository or download the dataset (`vehicles.csv`).
2. Install required Python libraries:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
   ```
3. Run the provided code scripts for data cleaning, EDA, and modeling.

---

#### **Future Work**
1. Test additional models like Gradient Boosting or XGBoost for potential performance improvements.
2. Perform clustering analysis to segment the market into distinct groups based on price ranges and attributes.
3. Incorporate external data (e.g., regional demand trends) for more robust predictions.

---

#### **Acknowledgments**
- Dataset provided as part of the assignment.
- Analysis performed on Thursday, January 30, 2025.

For questions or feedback, please contact sohanit@gmail.com.
