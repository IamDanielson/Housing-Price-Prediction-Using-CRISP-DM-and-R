# Housing-Price-Prediction-Using-CRISP-DM-and-R
This project utilizes the CRISP-DM framework to analyze a structured housing dataset and forecast residential property prices. Implemented in R, it involves building and evaluating various regression models to identify optimal approaches for predicting property sale values and uncovering investment potential.

 # CRISP-DM Phases
# 1. Business Understanding
Goal: Maximize investment returns by predicting house sale prices and identifying properties likely to appreciate in value.

# Success Indicators:

High-accuracy price predictions (low MAE)

Identification of high-potential investment opportunities

Understanding seasonal trends for better marketing timing

# 2. Data Understanding
The dataset includes property listings within a common geographical zone.

# Key features:

Proximity to points of interest (e.g., ocean and city center)

Property size, structural quality, and month of sale

Clean dataset with no missing/null values

# Findings:

June has the highest transaction volume, showing seasonal influence on demand

# 3. Data Preparation & Feature Engineering
Removed duplicate entries (using PARCELNO)

Dropped irrelevant columns like LATITUDE, LONGITUDE, and demographic indicators

Created new features with strong correlation to sale prices

Applied a correlation threshold (≥ 0.3) to retain impactful variables

# 4. Modelling
Developed eight predictive models with a 70/30 train-test split:

Linear Regression

Support Vector Regression (Linear & Polynomial)

Decision Tree

Random Forest (100, 200, 500 trees)

Gradient Boosting

# 📊 Evaluation Metric: Mean Absolute Error (MAE)

# Model	MAE Performance
Linear Regression	Moderate
SVR (Linear & Poly)	Moderate
Decision Tree	Moderate
Random Forest (100 Trees)	🔥 Best (Lowest MAE) ✅
Gradient Boosting	Competitive

# 5. Model Tuning
Tuned Random Forest using caret::train()

Parameters adjusted: mtry, min.node.size, splitrule = "variance"

Used 5-fold Cross Validation to reduce overfitting

Final model showed slight improvement in accuracy

# 6. Evaluation
The tuned Random Forest model was tested on real data and accurately predicted a property's price (~1.35M)

It met both technical (MAE) and business (investment insight) expectations

# 🚀 Deployment & Usability
# 🧩 Deployment
Save best model as best_model.rds

Deploy using Shiny or Azure ML Web Service

Real-time prediction interface for property input

# 🔄 Data Pipeline
Connect to property listing databases or APIs

Automatically refresh with new listings and market changes

# 🖥️ Interface
User-friendly UI for analysts, investors, and agents

Input fields: land size, build quality, sale month, proximity, etc.

# 📄 Documentation
Includes technical documentation and user manual

Guides on how to use and interpret model outputs

# 🔍 Key Takeaways
Random Forest (100 trees) performed best

Top predictors: Land Area, Living Space, and Build Quality

June is peak sale month; January is lowest

Proximity to city or ocean impacts value

The model generalizes well and is ready for real-world use

# 🛠️ Tools Used
Language: R

Libraries: tidyverse, ggplot2, caret, randomForest, e1071, gbm, rpart

Framework: CRISP-DM

Deployment Tools: Shiny, Azure ML

# 🔮 Future Enhancements
Expand to larger or multi-regional datasets

Integrate geospatial modeling (e.g., spatial interpolation)

Automate tuning using Bayesian optimization

Enhance UI for wider stakeholder access

