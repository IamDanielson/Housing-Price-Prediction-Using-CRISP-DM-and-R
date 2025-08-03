
# 🏡 Housing Price Prediction Using CRISP-DM and R

This project applies the **CRISP-DM** framework to a structured housing dataset to forecast residential property prices and uncover investment opportunities. Implemented in **R**, it features the development and evaluation of multiple regression models to determine the most accurate approach for predicting property sale values.

---

## 📈 CRISP-DM Phases

### 1. Business Understanding

**Objective:**
Maximize investment returns by predicting house sale prices and identifying properties likely to appreciate in value.

**Success Criteria:**

* Accurate price predictions (low MAE)
* Identification of high-potential investment opportunities
* Insights into seasonal sales patterns to guide marketing strategies

---

### 2. Data Understanding

The dataset includes property listings within a specific region.

**Key Features:**

* Proximity to ocean and city centers
* Property size, structural quality, and sale month
* No missing or null values

**Findings:**

* June sees the highest transaction volume, indicating seasonal demand trends

---

### 3. Data Preparation & Feature Engineering

* Removed duplicates using `PARCELNO`
* Dropped irrelevant fields: `LATITUDE`, `LONGITUDE`, `avno60plus`
* Engineered new features based on correlation with sale price
* Applied correlation threshold (≥ 0.3) to retain impactful predictors

---

### 4. Modelling

Eight regression models were developed using a **70/30 train-test split**:

* Linear Regression
* Support Vector Regression (Linear & Polynomial)
* Decision Tree
* Random Forest (100, 200, 500 trees)
* Gradient Boosting

**Evaluation Metric:**
Mean Absolute Error (MAE)

| Model                         | Performance             |
| ----------------------------- | ----------------------- |
| Linear Regression             | Moderate                |
| SVR (Linear & Polynomial)     | Moderate                |
| Decision Tree                 | Moderate                |
| **Random Forest (100 Trees)** | ✅ **Best (Lowest MAE)** |
| Random Forest (200/500)       | Slightly higher         |
| Gradient Boosting             | Competitive             |

---

### 5. Model Tuning

* Tuned **Random Forest** using `caret::train()`
* Parameters: `mtry`, `min.node.size`, `splitrule = "variance"`
* Applied 5-fold cross-validation to reduce overfitting
* Slight improvement in accuracy achieved

---

### 6. Evaluation

* Final model accurately predicted a test property’s price (\~\$1.35M)
* Met both technical (low MAE) and business (ROI insights) objectives

---

## 🚀 Deployment & Usability

### 🧩 Model Deployment

* Saved as `best_model.rds`
* Deployable via **Shiny** app or **Azure ML Web Service**
* Accepts user input to provide real-time price prediction

### 🔄 Data Pipeline

* Connects to property databases or APIs
* Updates automatically with new listings and market trends

### 🖥️ User Interface

* Intuitive UI designed for analysts, investors, and real estate agents
* Input fields: land size, build quality, sale month, proximity to city/ocean, etc.

### 📄 Documentation

* Includes technical documentation and user guide
* Instructions for usage and model interpretation

---

## 🔍 Key Insights

* **Best Model:** Random Forest (100 Trees)
* **Top Predictors:** Land Area, Living Space, Build Quality
* **Sales Trends:** June peaks, January lowest
* **Location Impact:** Proximity to ocean/city strongly influences price
* The model generalizes well and is deployment-ready

---

## 🛠️ Tools & Technologies

* **Language:** R
* **Libraries:** `tidyverse`, `ggplot2`, `caret`, `randomForest`, `e1071`, `gbm`, `rpart`
* **Framework:** CRISP-DM
* **Deployment Tools:** Shiny, Azure ML

---

## 🔮 Future Enhancements

* Extend to multi-regional or larger datasets
* Integrate geospatial modeling (e.g., spatial interpolation)
* Use automated hyperparameter tuning (e.g., Bayesian Optimization)
* Enhance user interface for broader stakeholder adoption

