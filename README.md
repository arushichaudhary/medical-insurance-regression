# Medical Insurance Cost Prediction using Multiple Linear Regression

## Objective
To build a Multiple Linear Regression model that predicts medical insurance charges of customers based on their personal and health-related information (age, sex, BMI, number of children, smoking status, and region).

## Dataset Link
[Medical Cost Personal Insurance Dataset - Kaggle](https://www.kaggle.com/datasets/mirichoi0218/insurance)

> Note: The dataset (`insurance.csv`) is not uploaded here. Please download it from the Kaggle link above and place it in the same folder as the notebook before running.

## Libraries Used
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

## Methodology
1. Loaded the dataset and explored its structure (numerical vs categorical features, target variable).
2. Checked for missing values (none found).
3. Encoded categorical columns:
   - `sex` and `smoker` label encoded (0/1)
   - `region` one-hot encoded
4. Split data into 80% training and 20% testing sets.
5. Trained a Multiple Linear Regression model on the training set.
6. Predicted charges for the test set and evaluated the model using MAE, MSE, RMSE and R2 score.
7. Plotted Actual vs Predicted charges to visually check model performance.

## Results
| Metric | Value |
|--------|-------|
| MAE  | 4181.19 |
| MSE  | 33,596,915.85 |
| RMSE | 5796.28 |
| R2 Score | 0.7836 |

**Observations:**
- The model explains about 78% of the variance in insurance charges (R2 ~ 0.78), which is a reasonably good fit for a simple linear model.
- `smoker` status has by far the largest coefficient, meaning smokers are charged significantly more than non-smokers, all else being equal.
- The Actual vs Predicted scatter plot shows the model underpredicts charges for a group of high-cost customers, suggesting the true relationship between the features and charges isn't perfectly linear.

## Conclusion
This project used a Multiple Linear Regression model to predict medical insurance charges based on age, sex, BMI, number of children, smoking status, and region. The model achieved an R2 score of approximately 0.78 on the test set, showing a reasonably good fit. Smoking status turned out to be the strongest predictor of charges by a wide margin, followed by BMI and age, which matches real-world expectations since smoking and obesity are known health risk factors that insurers price for. Region and sex had a comparatively small effect on the predicted charges.

One key limitation of Linear Regression here is that it assumes a linear relationship between features and charges, but the actual relationship, especially between smoking, BMI, and charges, appears non-linear. This causes the model to underpredict costs for high-risk individuals, and a non-linear model like Random Forest could likely capture these interactions better.
