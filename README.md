# econ3916-lab16-regularization

# Regularization: Buying Bias to Sell Variance

## Objective
The goal of this lab was to understand how regularization can improve a model's predictions by reducing overfitting, even if it introduces some bias.

## Methodology
- Created a simulated dataset with 200 predictors, but only 5 were actually relevant, and used 105 observations for training.
- Fitted OLS, LASSO, and Ridge regression models and compared their training and test errors.
- Plotted the LASSO coefficient path to see how variables entered the model as the penalty changed.
- Used 5-fold cross-validation to choose the best penalty, with standardization done separately within each fold.
- Compared the variables selected by LASSO against the 5 true predictors.
- Tested how LASSO and Ridge handled two highly correlated predictors.
- Used AI to help write a cross-validation function and tested it over 2 rounds against the expected results.

## Key Findings

LASSO performed the best out of the three models. OLS had a test MSE of 12.9587, Ridge had 10.1128, and LASSO had 1.4219. This showed that regularization can improve predictions by reducing overfitting, especially when most predictors are irrelevant.

Looking at the LASSO coefficient path, all 5 true predictors entered by step 6, while the first noise variable entered at step 17. Using 5-fold cross-validation, the best lambda was 0.1995 with a CV MSE of 1.5502.

LASSO selected all 5 true predictors but also included 11 false positives. This showed me that even if a model predicts well, it does not necessarily select only the correct variables.

When I tested two highly correlated predictors, LASSO gave one predictor a coefficient of 4.462 and the other 0. Ridge instead split the coefficients between them, assigning 1.618 and 1.609. This helped me understand how the two methods handle correlated variables differently.

For the AI-assisted section, I completed 2 rounds of prompting and checking. Both rounds passed all four checks. For the 21-penalty grid, the best lambda was 0.1995 with a CV MSE of 1.5502. For the 11-penalty grid, the best lambda was 0.1585 with a CV MSE of 1.5810.

Overall, this lab helped me understand why adding a penalty can improve predictions and why standardization matters when using regularization.
