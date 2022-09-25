# Telco customer churn: Project Overview

**Tags: XGBoost, dummy classifier, randomSearchCV, EDA, feature engineering, feature modeling,**

This notebook is based on StatQuest with Josh Starmer's webinar called XGBoost in [Python from Start to Finish](https://www.youtube.com/watch?v=GrJP9FLV3FE).

- Dropped redundant and after churn columns.
- Did the EDA and generated insights.
- Created one new column to get a better picture of the data.
- Encoded categorical variables to fit in the model.
- Used a dummy classifier to be the baseline for later comparisons.
- Build a non-tuned XGBoost model. 
- Tested XGBoost model with RandomizeSearchCV to boost the hyperparameters.
- Draw recommendations to retain the customer before the churn.

## Code and resources

Platform: Jupyter Notebook

Python version: 3.7.6

Packages: matplotlib, pandas, pandas profiling, numpy, seaborn, sklearn, and xgboost

## Data set

This IBM data set that contains information about a fictional telecommunications company, Telco, which provides internet and phone services in California, USA. There are indications if a customer signed up for their services, stayed, or left the company. You can find this data used in this notebook on Kaggle or access its latest version on IBM's site, both by clicking on the links below.

**Data set URL: https://www.kaggle.com/datasets/blastchar/telco-customer-churn**
**IBM data set the latest version: https://community.ibm.com/community/user/businessanalytics/blogs/steven-macko/2019/07/11/telco-customer-churn-1113**

## Model building

- Used one-hot encoding to convert categorical variables into numerical ones.
- Build a dummy classifier and calculated the AUC as our baseline.
- Built a non-boosted XGBoost model as the base model and check its score using ROC e AUC.
- Boosted XGBoost hyperparameters with RandomizeSearchCV to enhance its performance. The parameters booster were:
    - gamma;
    - learning_rate;
    - max_depth;
    - reg_gamma;
    - scale_pos_weight.

## Model performance

The best parameters were:
- gamma = 1.0;
- learning_rate = 0.1;
- max_depth = 4;
- reg_gamma = 0;
- scale_pos_weight = 1.

The AUCPR metric for this model was 0.66517, and the recall was 0.87.
