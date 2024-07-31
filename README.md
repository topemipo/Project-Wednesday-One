# Project Wednesday: Predictive Analysis for Music Genre Classification

### Import all Neccesary Libraires and Modules

I like to import all the libraries and modules I'll need for any project I'm working on before even starting anything, and then add to it if any new ones come up as I go. For this project, you will need modules from the pandas, numpy, seaborn, matplotlib, and scikit-learn libraries.

I'll also suggest you include a line to suppress specific FutureWarning messages from Seaborn to keep the output clean and focused on the relevant results.

### Exploratory Data Analysis & Data Cleaning

For the people that might need a little more help - Watch this [video](https://www.youtube.com/watch?v=Liv6eeb1VfE) or this [one](https://www.youtube.com/watch?v=xi0vhXFPegw) for a beginner's introduction to EDA. They both contain explanations to most of the functions I used in my own attempt. ChatGPT or any other LLM is also very helpful here but remember, don't just copy and paste without understanding how the code works and how you can write it on your own without any help next time.

Here are the steps you should take for this section :
1. Import your dataset 
2. Check for null values
3. If there are any null values, clear them out. Ensure that they are all gone.
4. Investigate the datatypes contained in the dataset with `info()` and check for the unique genres in the dataset with `value_counts()`
5. Visualize the distribution of Genres unique values

You can always check my attempt of this project on Github if you're not sure of anything.

### Correlation Analysis

The reason why we carryout correlation anaysis before applying PCA to our datset is because we want to besure if PCA is relevant. If there are no correlations between the variables in the dataset, PCA might not be useful. This is because PCA works by finding patterns in the data, and if the variables aren't related, there aren't any patterns to find. Without correlations, PCA won't help reduce the number of variables or reveal anything new about the data. Someone had ask a question similar to the statement above on Research Gate. 

Here's a [thread](https://www.researchgate.net/post/Do-I-need-a-correlation-analysis-between-variables-before-a-PCA-analysis) of people annswering the question with similar claim that I made. 

For beginners, here's a [video](https://www.youtube.com/watch?v=J7cd1-g1O7A) explaining how to calculate correaltion value between each feature of our datset, and then visualise it using a heatmap.

[365 Data Science](https://learn.365datascience.com/) also has many videos on their platform explaining correlation analysis and how it works. You should definitely check it out.

Here are the steps you should take for this section:
1. Convert the only column with categorical data in our dataset to numerical data with the appropriate encoder.
2. Calculate the correlation value between each feature of our dataset with `corr()` and visualize the result with `heatmap()`

### Principal Component Analysis (PCA) for Dimensionality Reduction

If the result from our correlation analysis indicates that there is a need for PCA, then that's the next thing we do. PCA is a dimensionality reduction technique that transforms a set of possibly correlated variables into a set of linearly uncorrelated variables called principal components. It helps in reducing the complexity of the data while retaining most of the variation present in the dataset.

I got all the resource i needed to understand PCA and the code to carry it out from [365 Data Science](https://learn.365datascience.com/). You can check out this [video](https://www.youtube.com/watch?v=8klqIM9UvAc&ab_channel=codebasics) too. It gives a bit of help with what you should do. 

Here are the steps you should take for this section:
1. Split the dataset into input and output data
2. Standardize the input data
3. Apply PCA without specifying the number of components or  the percentage of variance to be explained by the selected components
4. Visualise the PCA expalined variance ratio
5. Visualise the cummulative variance to determine the no of components. Note that you need to identify the minimum number of components that collectively account for at least 80% of the total variance.
6.  Reapply PCA with the chosen minimum number of components

NB: You can also just skip steps 3, 4 and 5 and apply the 80% variance criterion directly

### Model Development and Evaluation

Our next task is to implement a Logistic Regression model with a high iteration limit. We'll fit this model to our training data from the PCA-transformed dataset and then use it to predict the target values for the test set. Once we've made predictions, we'll evaluate the model's performance using the `classification_report()` function to assess its effectiveness.

Although exploring and evaluating various machine learning models is beyond the scope of this episode, feel free to experiment with different models, assess their performance, and use appropriate metrics to identify the best-performing model. Additionally, you can explore techniques to further enhance the performance of the chosen model. You could also try and see how the model performs without carrying out PCA.

Here's a [video](https://www.youtube.com/watch?v=HYcXgN9HaTM) on how to implement Logistic Regression and another [one](https://www.youtube.com/watch?v=XiUlqN1Ay0U&ab_channel=MachineLearning) on how to read and understand a classification report.

Here are the steps you should take for this section:

1. Split the input and output data into training and test datasets using a 30% test size and a random state of 42 for reproducibility.
2. Implement a Logistic Regression model with a 1000 iteration limit
3. Change the labels with their original form
4. Produce te performance report
5. Visualise the confusion matrix

### Prediction and Filling Missing Values

We're nearly at the end of this project. All that's left is to use our now trained model to predict what the missing gneres are in our dataset.

Here are the steps you should take for this section:

1. Prepare the input features for the trained model by extracting only the rows from our original datset with missing genres, seperating the input features from the target column (Genre) and then standardizing your input features and reducing the dimensions with PCA
3. Implement the trained model in predicting the genre of the input features
4. Transform the predictions into the original labels
5. Assign these predicted genre labels to the corresponding rows in the original dataset, filling in the missing genre information.
6. Save the dataset with the now filled columns into a new csv file.
