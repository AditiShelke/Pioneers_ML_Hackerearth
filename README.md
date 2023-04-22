# Product Length Prediction Model
## Introduction
The goal of this project is to develop a machine learning model that can predict the length dimension of a product. Accurate product length prediction is crucial for efficient packaging and storing of products in a warehouse, and is also an important attribute that customers use to assess product size before purchasing. However, manually measuring the length of millions of products can be time-consuming and error-prone.

The dataset provided includes product metadata such as title, description, bullet points, product type ID, and product length for 2.2 million products to train and test the model. The task is to build a machine learning model that can predict product length accurately.




## Approach
1. Cleaned the column names, dropped missing values, and converted data types using the klib library.
2. Checked for duplicates and removed them from the dataset.
3. Combined the 'TITLE', 'BULLET_POINTS', and 'DESCRIPTION' columns into a new 'text' column.
4. Applied text processing techniques to the 'text' column to remove punctuation, tokenize, remove stop words, and lemmatize the text.
5. Extracted important words (adjectives) from the preprocessed text using the nltk library.
6. Found words similar in meaning to "size" using the gensim library.
7. Converted the text column from lists to strings and stored the results in a new column.

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
