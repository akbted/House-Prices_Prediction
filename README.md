# House-Prices_Prediction

## Dataset Description
This project uses the Ames Housing dataset to predict house prices. The dataset includes 79 explanatory variables describing various aspects of residential homes in Ames, Iowa.

### File Descriptions
- `train.csv`: The training set.
- `test.csv`: The test set.
- `data_description.txt`: Full description of each column, originally prepared by Dean De Cock but lightly edited to match the column names used here.
- `sample_submission.csv`: A benchmark submission from a linear regression on year and month of sale, lot square footage, and number of bedrooms.

### Data Fields
Here's a brief version of what you'll find in the data description file: Please the data folder and data_description.txt file attached.

## Notebook Overview
The notebook includes the following steps:

1. **Data Loading**: Load the training and test datasets.
2. **Data Cleaning**: Handle missing values and outliers.
3. **Exploratory Data Analysis (EDA)**: Understand the data through visualizations and statistical analysis.
4. **Feature Engineering**: Create new features and transform existing ones.
5. **Encoding Categorical Data**: Convert categorical variables into numerical format using techniques like one-hot encoding.
6. **Model Building**: Train various regression models to predict house prices
    a. Gradient Boosting 
    b. Random Forest
    c. Multimodal Linear Regression
    d. ANN 
7. **Model Evaluation**: Evaluate the models using metrics like RMSE.
8. **Submission**: Prepare the submission file for the competition.

## Evaluation
### Goal
Predict the sales price for each house. For each Id in the test set, you must predict the value of the SalePrice variable.

### Metric
Submissions are evaluated on Root-Mean-Squared-Error (RMSE) between the logarithm of the predicted value and the logarithm of the observed sales price. (Taking logs means that errors in predicting expensive houses and cheap houses will affect the result equally.)
