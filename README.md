# Perdictive-Binary-Classification-Model-For-Credit-Card-Approval

#Introduction
Credit card application approvals are important business decisions for financial institutions and bankers based on customer information. With thousands of applications, these institutions utilize data analysis for decision making to evaluate credit card applicants. To better evaluate the prediction performance of binary classification models this paper uses the credit application data taken from the UCI machine learning repository. This project aims to build a classification model using Confusion Matrix to determine if applicants will be approved for credit card or denied using the applicant’s information. I specifically looked at variables such as Years Employed, Age and lastly Approved as target my variable. To test the model, I accessed the accuracy and Roc curve to evaluate the prediction model. 

# Data Source
The dataset is an Australian Credit Card dataset donated by Quinlan, it was used for the Stat log project. The dataset is available in Machine Learning Repository of University of California, Irvine(UCI).  The name of the Financial Institution is not mentioned in the repository for protecting the sensitive customer data. The dataset is anonymized credit card applications with a binary response variable indicating if the application was positive (1) or negative (0). All attribute names and values have been changed to meaningless symbols to protect confidentiality of the data. The dataset is presented without the categorical variables and data points that have missing values. It includes a total of 16 variables, the first 15 variables represent various attributes of the applicant's information such as Gender, Age, Income, Married, Years Employed etc. The remaining variable is a categorical variable that is represented with “+” and “-” symbols which were changed to “1” and “0”, approved/ not approved.  After cleaning the dataset, Histograms, Confusion Matrix and ROC are implemented to predict whether applicants are approved for credit cards or not. 

The variables in the dataset include 
-	Credit Score 
- Married
- Prior Default
- Debt 
- Age 
-	Gender 
-	Years Employed 
-	BankCustomer
- Industry
- Ethnicity 
-	Employed 
-	Driver’s License 
-	Citizen (ship)
-	Zip Code
- Approved 

# Data Cleaning
The raw dataset downloaded from UCI Machine Learning Repository was encrypted for protection of customers and bank information. The encrypted data consisted of symbols and numbers as well as missing values. Through additional research the data was successfully decrypted, and the missing values were deleted to avoid any errors. Lastly, I had to convert categorical variables to numerical variables.



Encrypted Data: 690 Observations 
Gender	chr	“b”, “a”, “a”, “b”, ...
Age	chr	“30.83”, “58.67”, “24.50”, “27.83”, ...
Debt	num	0.000, 4.460, 0.500, 1.540, ...
Married	chr	“u”, “u”, “u”, “u”, ...
BankCustomer	chr	“g”, “g”, “g”, “g”, ...
EducationLevel	chr	“w”, “q”, “q”, “w”, ...
Ethnicity	chr	“v”, “h”, “h”, “v”, ...
YearsEmployed	num	1.25, 3.04, 1.50, 3.75, ...
PriorDefault	chr	“t”, “t”, “t”, “t”, ...
Employed	chr	“t”, “t”, “f”, “t”, ...
CreditScore	num	1, 6, 0, 5, ...
DriversLicense	chr	“f”, “f”, “f”, “t”, ...
Citizen	chr	“g”, “g”, “g”, “g”, ...
ZipCode	chr	“00202”, “00043”, “00280”, “00100”, ..
Income	num	0, 560, 824, 3, ...
Approved	chr	“+”, “+”, “+”, “+”, ...

# Exploratory Analysis
I imported the dataset into Tableau and below I plotted distribution for Approved, Years Employed and Age.

<img width="468" alt="image" src="https://user-images.githubusercontent.com/77355548/208507493-dd6d8b08-9581-4dca-94f8-b06d3e0cce8a.png">

There are a total of 690 applicants. Out of the 690 applications, 383 (55.5%) applications got denied and 307 (44.5%) applications that got approved. 

<img width="468" alt="image" src="https://user-images.githubusercontent.com/77355548/208507579-6894890f-61c5-4130-952a-306815737f64.png">

Following a similar trend most applicants have been working less than two years, and we also have several outliers who have been working for 10 years+. The employment length histogram is positively skewed. 

<img width="468" alt="image" src="https://user-images.githubusercontent.com/77355548/208507625-56fc48f4-fd7a-40fd-a221-44da6c94cf0d.png">

Age is normally distributed, but slightly skewed more towards younger Ages. Which is reasonable for credit card applications.


# Confusion Matrix 
Confusion will help measure all possible combinations of the number of counts values of correct and incorrect predictions. The percentile function was used to compute the confusion matrix of the combined variable to set the threshold for our data set. If the combined variable turns out to be less than ( < ) the threshold it will predict “1” which is approved in our case. If the combined variable turns out to be  greater than or equal to (>=) than the threshold it will predict “0” which is denied.

- True Negative (TP): the actual and the predicted value are negative (0)
- False Positive (FP): the actual value is negative (0) but the predicted value is positive (1)
- False Negative (TN): the actual value is positive (1) but the predicted value is negative (0)
- True Positive (TP):  the actual and the predicted value are positive (1)

# Roc (Receiver Operating Characteristic) Curve 
The quality of our prediction model is measured by computing the total area under the ROC curve. The closer the curve is on the upper right corner of the graph the better it is. The value of True Positives is greater than the value of False Negatives indicated by the high value of Y-axis. The value of False Positives is greater than the value of True Negatives indicated by the high value of x-axis. 
The goal of this model is to classify if an application is approved or not. It should predict either 0 (not approved) or 1 (approved). The values of this model range from 0 to 1. To test the model, Max Accuracy was used to set a set of values and see how well it performs. The value of area under the curve ranges from 0 to 1. To compute the maximum accuracy I used =max (U2:U22) and tuned the model by changing the weight value for the variable 1( years employed). In our case the best ROC curve value starts at -0.125 downwards at 99.5% accuracy.

<img width="468" alt="image" src="https://user-images.githubusercontent.com/77355548/208507878-59b1af13-23c1-4578-95ab-e092487405e8.png">


# Conclusion 
With binary classification model accuracy is not a reliable parameter. Although the accuracy comes out to 100%, relying on accuracy is not a good indicator in this case because the dataset from the UCI Machine Learning Repository is imbalanced. Having more balanced and decrypted data for analysis would be helpful to work with and better indicate correlations between variables.


