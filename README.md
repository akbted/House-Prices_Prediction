# House-Prices_Prediction

## Dataset Description
This project uses the Ames Housing dataset to predict house prices. The dataset includes 79 explanatory variables describing various aspects of residential homes in Ames, Iowa.

### File Descriptions
- `train.csv`: The training set.
- `test.csv`: The test set.
- `data_description.txt`: Full description of each column, originally prepared by Dean De Cock but lightly edited to match the column names used here.
- `sample_submission.csv`: A benchmark submission from a linear regression on year and month of sale, lot square footage, and number of bedrooms.

### Data Fields
Here's a brief version of what you'll find in the data description file: Please refer to the data folder and data_description.txt file attached.

## Notebook Overview
The notebook includes the following steps:

1. **Data Loading**: Load the training and test datasets.
2. **Data Cleaning**: Handle missing values and outliers.
3. **Exploratory Data Analysis (EDA)**: Understand the data through visualizations and statistical analysis.
4. **Feature Engineering**: Create new features and transform existing ones.
5. **Encoding Categorical Data**: Convert categorical variables into numerical format using techniques like one-hot encoding.
6. **Model Building**: Train various regression models to predict house prices:
    - Gradient Boosting
    - Random Forest
    - CatBoost
7. **Model Evaluation**: Evaluate the models using metrics like RMSE.
8. **Submission**: Prepare the submission file for the competition.

## Data Preparation
- **Handling Missing Values**: Missing values were imputed using the median for numerical features and the most frequent value for categorical features.
- **Feature Engineering**: One-hot encoding was applied to significant categorical features.

## Exploratory Data Analysis (EDA)
- **Univariate Analysis**: Distribution of numerical and categorical features was analyzed.
- **Bivariate Analysis**: Relationships between features and the target variable `SalePrice` were explored.
- **Correlation Analysis**: Identified highly correlated features with `SalePrice`.

## Model Building and Evaluation
### Gradient Boosting
- **Model**: GradientBoostingRegressor
- **Parameters**: `n_estimators=100`, `learning_rate=0.1`, `max_depth=3`, `random_state=42`
- **Scores**:
    - Mean Squared Error (MSE): 0.022
    - Root Mean Squared Error (RMSE): 0.150
    - R^2 Score: 0.879

### Random Forest
- **Model**: RandomForestRegressor
- **Parameters**: `n_estimators=100`, `max_depth=10`, `random_state=42`
- **Scores**:
    - Mean Squared Error (MSE): 0.024
    - Root Mean Squared Error (RMSE): 0.155
    - R^2 Score: 0.870

### CatBoost
- **Model**: CatBoostRegressor
- **Parameters**: `iterations=1000`, `learning_rate=0.1`, `depth=10`, `random_seed=42`
- **Scores**:
    - Mean Squared Error (MSE): 0.020
    - Root Mean Squared Error (RMSE): 0.141
    - R^2 Score: 0.890

## Performance and Error Visualization
The performance of the models was visualized using bar charts for MSE, RMSE, and R^2 Score.

## Testing
- **Handling Missing Values**: Missing values in the test data were imputed using the most frequent value.
- **One-Hot Encoding**: Applied to significant categorical features in the test data.
- **Prediction**: The `SalePrice` was predicted using the CatBoost model.

## Submission
The `Id` and `SalePrice` columns were saved to a new CSV file for submission.

## Evaluation
### Goal
Predict the sales price for each house. For each Id in the test set, you must predict the value of the SalePrice variable.

### Metric
Submissions are evaluated on Root-Mean-Squared-Error (RMSE) between the logarithm of the predicted value and the logarithm of the observed sales price. (Taking logs means that errors in predicting expensive houses and cheap houses will affect the result equally.)