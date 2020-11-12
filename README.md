# Linear_Regression_Explained
This project aims to explain the mechanics of linear regression and dive deeper into it, to understand the underlying meaning and purpose of different aspects of linear regression. My attempt is to explain data science concept in a way that leads to understanding and no need to memorize.
---

A deep dive into Linear Regression
Actions have consequences!!!
Linear Regression is the most popular regression algorithmRegression analysis is a statistical technique which studies the cause effect relationship between the independent variable (explanatory/predictors) and the dependent (outcome/response) variables. 
Cause Effect → An event (cause) that leads to happening of other event(effect).
The underlying objective of regression is to identify the nature of cause-effect relationship between the variables. Based on the kind of relationship, the regression technique is chosen.
Linear Regression
Lets breakdown first, what is meant by linear regression?
Linear regression is one of the oldest, simplest, and most popular regression technique. Linear regression is based on assumption of linear relationship between predictor and outcome variable. In other words, the relationship can be expressed with first order equation. Linear regression is originally statistical technique which is also borrowed by machine learning under supervised learning algorithm. Linear regression works on the ordinary least square (OLS) principle, which is a technique to estimate the noise parameter of linear regression function and try to minimise the Mean squared error.
The equation of line:
𝐲=𝐦𝐱+𝐛 
m=slope of the line;
b=y intercept.
In linear regression, the outcome variable is a function of bias, predictor/s, and error/noise/unknown term. The noise terms takes account of the part that can not be explained by the model. To make the precise prediction, the aim is to minimize this noise as much as possible. 
Simple Linear Regression: Simple linear regression is technique when we are interested in relationship of 1 predictor and outcome variable. 
Simple Linear Regression Equation:
y=βₒ+β₁x+ε 
y= Outcome variable 
x= Predictor variable
βₒ= y intercept (minimum value of the outcome variable when predictor variable is zero)/ Bias
β₁= is the slope coefficient of the line (which show the ratio of change in y value with the change in x value.)
ε= error term
How it works? Let's find out!

There are two important parameters in linear regression Bias(βₒ) and slope (β₁). The parameter estimation is done by least square method which means that error term in equation (y=βₒ+β₁x+ε) should be minimised.
To calculate error:
Error or noise in the regression lineSum of squared errorsStep 1: We start of by calculating the slope (β₁).
alternate method
Step 2: To calculate the bias, plug in the least square estimates of β₁ in the equation.
When we have value of β₁ and βₒ we can plug in the values to obtain the equation
Step 3: Making predictions by plugging in the values of x.
Step 4: To know how good the model is in predicting, we need to find how close the predicted values and recorded values are. This is done by calculating error metrics such as RMSE. RMSE in simple way tell us on an average how wrong/far recorded values are from the predicted values.



This still looks like lot of calculation. Thankfully sklearn library makes implementing the model like a piece of cake!
Get the data (predictor and outcome variable) in arrays and reshape if necessary.
Split the dataset into train and test set.
Define the model
Fit the data

The complete code can be found on my Github.
To ascertain the model reliability, the underlying assumption of linear regression should be checked. In case of finding a violation, corrective measures can be taken. 
Assumptions examining ascertains that a sword is not used in place of needle!
Linear regression model assumptions:
Continuous variables: The measured variable should be on continuous scale.

Linearity: Linear regression is based on the assumption of linear relationship between the independent and dependent variable.
Test: Scatter plot between dependent variable and independent variable.
Solution: Choose non-linear model / non linear data transformation techniques such as Logarithmic, Exponential,Quadratic, Inverse.
Traps: Selection of technique is conditional and should be tested by applying on the data. Residual plots and correlation coefficients should be observed to find improvement in the linearity.

Independent observations / absence of multicollinearity: The independent variables should not be highly correlated to each other.
Test: Correlation matrix, Tolerance (T < 0.1 there might be multicollinearity in the data and with T < 0.01 there certainly),Variance Inflation Factor 
Solution: Remove the independent variable, feature engineering, centring data.
Note: Try and see, which method yields better results.



Absence of noise or outliers: The variables should be free from any significant outliers. Outliers affects the regression analysis negatively by 
leaving large residue behind.
Test: Outliers can be identified during the EDA. 
Solution: Complete case analysis, Data imputation, data transformation
Traps: The selection of technique purely depends on kind of outlier and is discretional. Is the alien value indeed an outlier(true outlier) or the value is correct, but do not belong to the sample of interest.



Gaussian distribution: The predictors and outcome variables should be normally distributed. Normal distribution of variable empowers the model and model makes more reliable prediction.
Test: Histogram, P-P Plot, Durbin Watson Test
Solution: variable transformation (Box-Cox transformation)



Skewness and Kurtosis coeficientsRescaling inputs: Having variables on same scale improves the model capabilities to make reliable prediction. This is more of an improvement step, to bring all values on equivalent scale of measurement.
Test: EDA (variable range comparison)
Solution: Standardization or normalization
Homoscedasticity: The residue variance is the same for all values of predictor. This means that residue variance all along the best fit line is more or less same.
Test: Goldfeld-Quandt Test, Breush-Pagan test, NCV test, residual plot
Solution: Model with new more relevant predictors, variable transformation (Box-Cox transformation).

Normal distribution of residuals: The residuals should be normally distributed.
Test: Histogram, P-P Plot, Durbin Watson Test
Solution: Increase the model complexity, handling the outlier, Data transformation.
Traps: Treatment in response to the this assumption violation is subjected to the nature of the problem.



---

A piece of advice: There are enough libraries that can help you to create a model and fit the data, what is really important that the mechanics (How and Why) of the algorithm is well understood. Else you can see it as a gun in the hand of person who does not know how to handle it and fair chances are of backfiring.
If you find this article useful, don't feel shy to like it. If you don't like please let me know your suggestions to make it better. 
Github| LinkedIn
References:
https://www.statisticshowto.com/durbin-watson-test-coefficient/
https://statistics.laerd.com/spss-tutorials/linear-regression-using-spss-statistics.php
https://www.aasv.org/shap/issues/v15n5/v15n5editor.htm#:~:text=Linear%20regression%20models%20assume%20that,with%20the%20value%20of%20the
https://scikit-learn.org/stable/auto_examples/linear_model/plot_ols.html
https://www.statsmodels.org/devel/examples/notebooks/generated/regression_diagnostics.html
