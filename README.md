# Product Length Prediction Model
## Introduction
The goal of this project is to develop a machine learning model that can predict the length dimension of a product. Accurate product length prediction is crucial for efficient packaging and storing of products in a warehouse, and is also an important attribute that customers use to assess product size before purchasing. However, manually measuring the length of millions of products can be time-consuming and error-prone.

The dataset provided includes product metadata such as title, description, bullet points, product type ID, and product length for 2.2 million products to train and test the model. The task is to build a machine learning model that can predict product length accurately.




## Approach
1. Reading in train and test data as pandas dataframes from CSV files.
2. Preprocessing the data with klib, which includes cleaning column names, dropping missing values, and converting data types. It also checks for and removes duplicates in the data.
3. Filling in missing values with "None".
4. Checking for any remaining missing values and dropping those rows.
5. Visualizing the distribution of the "product_type_id" column with a boxplot.
6. Concatenating the "title", "bullet_points", and "description" columns into a new "text" column.
7. Preprocessing the text data with a function that removes punctuation, converts text to lowercase, tokenizes the text, removes stop words, and lemmatizes the tokens.
8. Encoding and decoding text data with a function that encodes text into ASCII and normalizes the text to remove any non-standard characters.
9. Using regular expressions to remove any special characters.
10. Replacing single quotes with double quotes.
11. plitting text into a list of words and joining the words back together with a single space between each word

## Feature Engineering
### The following feature engineering steps were taken:

1. Used the CountVectorizer library to transform the preprocessed text into a bag-of-words representation.
2. Added the important words and words similar to "size" to the bag-of-words representation.
3. Used the resulting bag-of-words representation as the input features for the machine learning model.


## Evaluation Metric
The evaluation metric for this task is the mean absolute percentage error (MAPE), which is calculated as:

score = max(0, 100 * (1 - metrics.mean_absolute_percentage_error(actual, predicted)))

A score of 100 indicates perfect predictions, while a score of 0 indicates that the model's predictions are completely off.

## Conclusion
In this project, we built a machine learning model that can predict product length from catalog metadata. Our approach involved pre-processing the text data, converting it into numerical vectors, and training several machine learning models. We evaluated the performance of each model using the MAPE evaluation metric. We hope that our model can be useful in predicting product length accurately and efficiently.
