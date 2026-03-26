# Black-Friday-Sales-Prediction-5
This project aims to predict the total purchase amount of customers during Black Friday sales. By understanding consumer spending behavior based on demographics and product categories, retail businesses can create highly targeted and personalized promotional offers.

## 📊 The Dataset
The dataset consists of over 500,000 transaction records containing customer demographics and product details.

**Key Features Include:**
* **Demographics:** Age, Gender, Marital Status, City Category, and Years Lived in Current City.
* **Product Info:** Product ID and hierarchical Product Categories.
* **Target Variable:** `Purchase` (The total dollar amount spent by the customer).

## 🚀 Methodology

### 1. Exploratory Data Analysis (EDA) & Memory Optimization
* Analyzed purchasing trends across different genders, age bins, and city categories.
* Optimized data visualizations for big data using direct Pandas aggregations (`value_counts()`) to prevent RAM memory crashes associated with standard Seaborn countplots on 500k+ rows.

### 2. Data Preprocessing
* **Missing Values:** Filled null values in secondary and tertiary product categories.
* **Memory Reduction:** Downcast numerical categories to 32-bit floats to halve the memory footprint.
* **Encoding:** Applied `LabelEncoder` for categorical variables (Gender, Age, City_Category) and `pd.get_dummies` (One-Hot Encoding) for the 'Stay_In_Current_City_Years' feature.

### 3. Machine Learning Modeling
Since the target variable (`Purchase`) is a continuous number, this was framed as a **Regression** problem. The dataset was split 80/20 for training and testing. 

The following models were evaluated:
* Linear Regression
* Decision Tree Regressor
* Random Forest Regressor
* **XGBoost Regressor (Winning Model)**

## 🏆 Results
The models were evaluated using **Root Mean Squared Error (RMSE)**. The **XGBoost Regressor** significantly outperformed the baseline models, achieving the lowest RMSE score (approx. ~2870), making it the most reliable model for forecasting customer spend.

## 🛠️ Tech Stack
* **Language:** Python 3
* **Data Manipulation:** Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn, XGBoost

## 💻 How to Run
1. Clone this repository to your local machine.
2. Ensure you have the required libraries installed: `pip install pandas numpy matplotlib seaborn scikit-learn xgboost`
3. Verify that the `BlackFridaySales.csv` file is located inside the `Data/` directory.
4. Open `Black_Friday_Sales_Prediction.ipynb` in Jupyter Notebook or Google Colab and run all cells.
