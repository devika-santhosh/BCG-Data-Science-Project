The client is PowerCo - a major gas and electricity utility that supplies to small and medium sized enterprises.
During the meeting the AD discussed some potential reasons for customer churn.

# Work Plan

 
    1. We need to define and calculate price sensitivity.
    2. Prepare the data and engineer features.
    3. Test our hypothesis using a binary classification model.
    4. Choose a model from one of the tested algorithms based on the model complexity, the explainability, and the accuracy of the models.
    5. Extrapolate the extent to which price sensitivity influences churn.
## EDA
**Price sensitivity is the degree to which demand changes when the cost of a product or service changes.**
![churn](https://github.com/devika-santhosh/BCG-Data-Science-Project/assets/125188753/a9d136d8-47ae-4dbd-be8b-c4245e3d2b8b)
- The visualization shows how many companies churned vs. how many companies did not churn. 
- We can see from this that the churn rate is approximately 10%. This is actually a very good churn rate, the closer the rate is to 0%, the better.
The next series of visualizations were created in an attempt to try and dive deeper into how churn changes based on other factors (using other columns). 

This is useful for us to investigate because it may help us to understand factors that drive churn.
In the notebook we visualize churn vs. sales channel, contract type, number of products, number of years and origin/contract offer.

**For example:**

![sales](https://github.com/devika-santhosh/BCG-Data-Science-Project/assets/125188753/73cfafb8-1b28-4ad3-9283-0efd52b364a7)
- We see that for sales channel, there are some sales channels that yield customers churning but there are also other sales channels that have no customers churning.

For contract type, we see quite an even split for customers churning. This is interesting because this may suggest that contract type is not a driving factor towards churn rate.

Additionally, for some columns their distributions with churn rate included. This is useful for us to understand because based on the distribution of a column, this could affect our feature engineering later.

We look at the distribution of consumption, subscribed power and forecast in the notebook. 

**For example:**
![Consumption](https://github.com/devika-santhosh/BCG-Data-Science-Project/assets/125188753/c0c4d4d0-c80a-4dc1-af1b-f8b00b0c5979)

- We notice that the distribution of consumption is very skewed, this is called a positive skew since it is biased towards lower values on the x axis.
- This is interesting because you may decide to treat this column to reduce the skewness later on during feature engineering. 
- But also because we may want to visualize if there are any outliers within this column. 


To investigate outliers, we use a boxplot. From the boxplot we can see that with the column as it is there are definitely some outliers. Once again this is interesting because we may choose to remove some of these outliers later.
## Feature engineering
- **Average and Maximum Price Changes:** The average and maximum price changes across different periods (peak, mid-peak, off-peak) are calculated to represent the variance of prices throughout the year.
- **Data Transformation:** All data is converted to numeric types for prediction. This includes converting dates into months, boolean columns into binary values, and categorical columns into dummy variables.
- **Distribution Normalization:** Columns with skewed distributions are transformed using the logarithm function to achieve a distribution closer to normal, as this is a common assumption in many prediction models.
- **Correlation Analysis:** Correlations between all columns are plotted to identify highly correlated columns, which may be removed to avoid redundancy in information.

## Modelling and Evaluation
- **Model Evaluation Metrics:** The model’s performance is evaluated using three metrics: accuracy, precision, and recall, to reflect its true performance.
- **Importance of Precision and Recall:** These metrics are crucial in scenarios where false negatives and false positives have significant implications, such as predicting heart failures in patients.
- **Churn Prediction:** The current model accurately identifies clients who do not churn but struggles with identifying those who will. This suggests that the current features are not optimal for predicting churn.
- **Feature Importance Chart:** A chart is produced to visualize the importance of various features within the model. Net margin and consumption over 12 months were found to be important, while price sensitivity features did not significantly drive churn.
## 🏅Certificate of Completion :
![Completion](https://github.com/devika-santhosh/BCG-Data-Science-Project/assets/125188753/4fb58fb5-98ec-4ec8-8e02-c401b8fe9053)
