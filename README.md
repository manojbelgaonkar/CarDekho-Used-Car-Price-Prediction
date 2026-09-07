# CarDekho Used Car Price Analysis & Prediction

## 📌 Project Overview

This project analyzes used car prices from the CarDekho dataset and builds a machine learning model to predict used car selling prices.

The analysis focuses on how factors such as car age, kilometers driven, fuel type, transmission, ownership, seller type, brand, and car model influence used car prices.

The final Random Forest model with brand and car model features achieved an **R² score of 0.818**.

---

## 🎯 Objectives

- Analyze used car pricing patterns.
- Study the relationship between vehicle age and resale value.
- Analyze the impact of kilometers driven on selling price.
- Compare prices across fuel types, transmission types, owners, sellers, brands, and models.
- Build machine learning models for used car price prediction.
- Compare model performance and select the best-performing model.

---

## 📂 Dataset

The dataset contains used car listings with the following features:

- `name` — Car name
- `year` — Manufacturing year
- `selling_price` — Selling price
- `km_driven` — Kilometers driven
- `fuel` — Fuel type
- `seller_type` — Type of seller
- `transmission` — Manual or Automatic
- `owner` — Ownership category

Source: CarDekho Used Car Dataset

---

## 🧹 Data Cleaning

The original dataset contained **4,340 records**.

Data preprocessing included:

- Removing duplicate records.
- Removing `Test Drive Car` records from the ownership analysis.
- Checking for missing values.
- Creating a `car_age` feature using 2026 as the analysis year.
- Extracting `brand` from the car name.
- Extracting the specific `model` from the car name.
- Grouping low-frequency car models into an `Other` category.

After cleaning, the final analytical dataset contained **3,560 records**.

---

## 📊 Exploratory Data Analysis

Key findings:

- Used car prices generally decrease as vehicle age increases.
- Cars with lower kilometers driven generally have higher selling prices.
- First-owner cars have higher typical selling prices than cars with more previous owners.
- Automatic cars have substantially higher average prices in this dataset.
- Premium brands generally have higher selling prices.
- Specific car models have a strong influence on selling price.

### Age & Resale Value

The dataset does not contain reliable original purchase prices, so exact depreciation percentage could not be calculated.

Instead, vehicle age was analyzed as a proxy for depreciation/resale value.

---

## 🤖 Machine Learning

The following models were evaluated:

1. Linear Regression
2. Random Forest
3. Random Forest + Brand
4. Random Forest + Brand + Model

### Model Comparison

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Linear Regression | ₹2.06L | ₹4.27L | 0.399 |
| Random Forest | ₹1.98L | ₹4.25L | 0.405 |
| Random Forest + Brand | ₹1.53L | ₹3.35L | 0.631 |
| **Random Forest + Brand + Model** | **₹1.02L** | **₹2.35L** | **0.818** |

---

## 🏆 Final Model

The best-performing model was:

**Random Forest + Brand + Model**

Performance on the test set:

- **R²:** 0.818
- **MAE:** approximately ₹1.02 lakh
- **RMSE:** approximately ₹2.35 lakh

An R² of 0.818 means that the model explains approximately **81.8% of the variation in selling prices** in the test dataset.

---

## 🔧 Hyperparameter Tuning

Random Forest hyperparameter tuning was also performed using `RandomizedSearchCV`.

The tuned model achieved:

- R²: 0.815
- MAE: approximately ₹1.01 lakh
- RMSE: approximately ₹2.37 lakh

The original Random Forest + Brand + Model model was selected as the final model because it achieved a higher R² and lower RMSE on the test set.

---

## 💡 Business Insights

- Vehicle age is negatively associated with resale price.
- Higher mileage generally corresponds to lower selling prices.
- Brand is an important predictor of used car prices.
- Specific car models provide additional predictive power beyond brand.
- Premium SUV models such as Fortuner and Endeavour showed relatively high average selling prices in this dataset.
- Adding brand and model features significantly improved machine learning performance.

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

## 📁 Project Structure

```text
CarDekho-Used-Car-Price-Prediction/
│
├── CarDekho_Used_Car_Analysis.ipynb
├── CAR DETAILS FROM CAR DEKHO.csv
├── README.md
└── images/
