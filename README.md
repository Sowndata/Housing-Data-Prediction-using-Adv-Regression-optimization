# Housing-Data-Prediction-using-Adv-Regression-optimization

A US-based housing company named Surprise Housing has decided to enter the Australian market. The company uses data analytics to purchase houses at a price below their actual values and flip them on at a higher price. For the same purpose, the company has collected a data set from the sale of houses in Australia. The data is provided in the CSV file below.

The company is looking at prospective properties to buy to enter the market. You are required to build a regression model using regularisation in order to predict the actual value of the prospective properties and decide whether to invest in them or not.

The company wants to know the following things about the prospective properties:

- Which variables are significant in predicting the price of a house, and
- How well those variables describe the price of a house.

Also, determine the optimal value of lambda for ridge and lasso regression.

**Business Goal**

To model the price of houses with the available independent variables. This model will then be used by the management to understand how exactly the prices vary with the variables. They can accordingly manipulate the strategy of the firm and concentrate on areas that will yield high returns. Further, the model will be a good way for management to understand the pricing dynamics of a new market.

**Data Understanding, Preparation, and EDA**

*converted the target variable to achieve normal distribution using log transformation*

**** target variable with a large spread of values, in turn, may result in large error gradient values causing weight values to change dramatically, making the learning process unstable. If we have skewed data then it may harm our results. So, in order to use skewed data, we have to apply a log transformation over the whole set of values to discover patterns in the data and make it usable for the statistical model.*

**Model Building and Evaluation -**

Built both the model Lasso and Ridge with correct variables and correct alpha values.

Finding and Learnings

- The optimal alpha value for Ridge Regression is: 0.4
The optimal alpha value for Lasso Regression is: 0.0001
Doubled alpha values of Ridge is 0.8 and Lasso is 0.0002.
After doubling the optimal alpha/lambda values for both Ridge and Lasso
Regression, we don't see any significant changes in both metrics and the features
except very minor variations here and there but overall, very similar.
Below table shows the important predictors:

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1efbcbe4-84b9-4cea-914c-ce12898d98f6/Untitled.png)

- The values of R2 Score, RSS and MSE for Lasso Regression are better than Ridge
Regression in this model. In Lasso Regression, we can push the model co-efficient
to actual zero value. This means that the features that have co-efficient value of 0
can be removed from the model. This results in feature selection. Model
complexity also reduces because we can remove features with zero co-efficient.
Thus, it is better to apply Lasso regression over Ridge Regression.

- Below are the initial top five most important predictor variables in the lasso
model-
OverallQual 1.050877
LotArea 0.581986
TotRmsAbvGrd 0.549388
GarageCars 0.413925
BsmtFullBath 0.251360
After removing the above 5 variables from model and creating another Lasso
model, below are the five most important predictor variables now
Fireplaces 0.615778
Neighborhood_StoneBr 0.305846
Neighborhood_NridgHt 0.298273
LandContour_HLS 0.122110
LandContour_Low 0.07194
- A robust and generalized model is a one that has just enough features with low
variance as possible. This means the model must be less complex and any
unprecedented change in one or more features does not significantly alter the
value of the predicted variable.
The OLS (Ordinary least squares) regression model is very sensitive to outliers,
and they induce high variance. To reduce this, we can make use of Ridge and
Lasso regularization that include a penalty term in the Cost function of the model.
The Penalty term will move the co-eff towards zero and this reduces the model
complexity, in turn reducing the overfitting.
So, Regularization will help us to build a model with high variance with a small
trade off in bias. Thus, it helps us build a model which is robust and generalizable
along with good, consistent train as well as test accuracy.
