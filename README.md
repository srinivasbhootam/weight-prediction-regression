# Weight Prediction Analysis

## Introduction
In this analysis, we set out to predict a person’s weight using height, age, and daily active minutes. We explored how these variables relate to weight, cleaned and prepared the data, trained a linear regression model, and evaluated its performance.

## Exploratory Data Analysis
- Dataset contains 34,633 records.
- **Age** ranges from 19 to 63 years.
- **Height** ranges from 150 to 199 cm.
- **Weight** ranges from 51 to 118 kg.
- **Active Minutes** ranges from 30 to 119 minutes per day.
- Histograms showed roughly normal distributions for each variable.
- Correlation heatmap revealed low correlation values between weight and the features.

## Preprocessing
- Stripped whitespace from column names.
- Renamed `Height (cm)` → `Height`, `Weight (kg)` → `Weight`, `Active_Minutes` → `Active Minutes`.
- Dropped all rows missing any of these key variables.
- Final clean dataset used for modeling.

## Train/Test Split
- Split data into 80% training (27,706 samples) and 20% testing (6,927 samples) with `random_state=42`.

## Model Training
- Trained a `LinearRegression` model on the training set.
- Learned coefficients:
  - Height: -0.0645
  - Age: -0.0111
  - Active Minutes: -0.0046

## Evaluation
- Predictions on the test set yielded a **Mean Squared Error (MSE)** of 472.03.
- Scatter plot of true vs. predicted weights showed predictions clustering around the average weight rather than along the ideal diagonal.

## Interpretation
I got the value of Mean Squared Error as 472.03, With an MSE of 472, our weight predictions tend to be quite far from the actual values. In other words, height, age, and daily active minutes by themselves don’t capture all the factors that determine someone’s weight. You can see in the scatter plot that most predictions hover around the average instead of matching each person’s true weight. To improve accuracy, we would need richer information, such as body composition or dietary habits and potentially more flexible models or regularization techniques.


# Reflection

In this project, I used three simple measures height, age, and daily active minutes to build and test a model that predicts weight. I started by cleaning and exploring the data, then trained a basic linear regression model and checked its error with mean squared error. The result showed that these three factors alone are not enough to predict weight accurately. Going through these steps helped me see how important it is to choose the right features and consider more detailed information for better predictions.


## Conclusion
The current model explains only a small portion of weight variation. Next steps include:
- Engineering additional features such as BMI or nutritional data.
- Trying regularized linear models (Ridge, Lasso) and non-linear algorithms.
- Performing cross-validation and hyperparameter tuning to improve generalization.
