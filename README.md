Model for Predicting Sales in a Retail Network

The first step involves creating a predictive econometric model written in the Python environment.

The primary method for daily sales forecasting is the application of linear regression using a large volume of preprocessed input data.

Input Data Preprocessing

Among the preprocessed input data is the dependent variable. In our case, it consists of historical daily sales data for the period:
[January 2018 – June 2022]. This data is stored in the file input_data_original (in the folder “input”), which is loaded into the model in the first block.

The next step involves loading independent variables, such as risk trends, weekdays, holidays, other events, and data for weather from the years 2018–2022. Considering the specifics of the dataset, missing data is not directly forecasted. Instead, the variables are shifted to specific time ranges, for example, a [-3;+3] day interval, which allows the dynamics before and after the observed event to be captured precisely.

The independent variables are stored in the file independent_variables in the “input” folder.

Training and Test Sets

At the beginning of the second block, we specify the sizes of the training and testing sets:
 • train_set_days_1 – start of the training set.
 • train_set_days_2 – end of the training set.
 • test_set_days_1 – start of the test set.
 • test_set_days_2 – end of the test set.

You need to specify the serial numbers of the days for each item.

Four data samples are subsequently created:
 • Y_train – training sample of the dependent variable.
 • X_train – training sample of independent variables.
 • X_test – testing sample of independent variables.
 • Y_test – testing sample of the dependent variable.

Regression Model and Output

Based on these dataframes, a linear regression is executed, the resulting coefficients of which are multiplied by the corresponding matrix of independent variables in the testing sample. The SUM of these values results in a forecast of daily sales.

The regression outputs the actual sales data and their forecast, which is saved in the Excel file forecasted_sales located in the “output” folder.

The left-hand part of the code and the model are accompanied by technical notes detailing the process. Each part of the script is thoroughly described to ensure maximum clarity.
