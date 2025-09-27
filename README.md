# Click-Through Rate (CTR) Prediction Project

## 1. Project Overview
This project aims to predict whether a user will click on an online advertisement based on user demographics, browsing behavior, device type, ad position, and time of day.  
The objective is to build a binary classification model to help improve ad targeting and optimize ad placement.

## 2. Dataset
The dataset contains 10,000 entries with the following columns:

- **id, full_name** – user identifiers (dropped for modeling)  
- **age** – numeric, user age  
- **gender** – categorical, Male / Female / Non-Binary  
- **device_type** – categorical, Mobile / Desktop / Tablet  
- **ad_position** – categorical, Top / Side / Bottom  
- **browsing_history** – categorical, Shopping / News / Entertainment / Education / Social Media  
- **time_of_day** – categorical, Morning / Afternoon / Evening / Night  
- **click** – target, 1 = clicked, 0 = not clicked  

## 3. Data Preprocessing
- Handled missing values:  
  - `age` → filled with mean  
  - `gender, device_type, ad_position, browsing_history, time_of_day` → filled with mode  
- Dropped unnecessary columns: `id`, `full_name`  
- Encoded categorical variables using one-hot encoding  
- Final dataset shape: **10,000 rows × 20 features**

## 4. Exploratory Data Analysis (EDA)
- Plotted distributions of categorical features: gender, device type, ad position, browsing history, time of day  
- Checked class balance for the target `click`  
- Visualizations helped understand user behavior patterns

## 5. Modeling
- Split data into training (80%) and testing (20%) sets  
- Models used:  
  - Decision Tree  
  - Random Forest  
  - XGBoost

## 6. Results

| Model          | Accuracy | Observations                                                                 |
|----------------|---------|----------------------------------------------------------------------------|
| Decision Tree  | 0.73    | Better recall for clicks (1), struggles with no-clicks (0)                  |
| Random Forest  | 0.71    | Similar trend as Decision Tree, slightly lower accuracy                     |
| XGBoost        | 0.75    | Best accuracy, predicts clicks well but some no-clicks misclassified       |

Confusion matrices show the difficulty in predicting non-clicks due to class imbalance.
