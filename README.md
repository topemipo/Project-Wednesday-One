# Project Wednesday: Predictive Analysis for Music Genre Classification

**Exploratory Data Analysis & Data Cleaning**

For the people that might need a little more help - Watch this [video](https://www.youtube.com/watch?v=Liv6eeb1VfE) or this [one](https://www.youtube.com/watch?v=xi0vhXFPegw) for a beginner's introduction to EDA. They both contain explanations to most of the functions I used in my own attempt. ChatGPT or any other LLM is also very helpful here but remember, don't just copy and paste without understanding how the code works and how you can write it on your own without any help next time.

Here are the steps you should take for this section :
1. Import your dataset 
2. Check for null values
3. If there are any null values, clear them out. Ensure that they are all gone.
4. Investigate the datatypes contained in the dataset with `info()` and check for the unique genres in the dataset with `value_counts()`
5. Visualize the distribution of Genres unique values

You can always check my attempt of this project on Github if you're not sure of anything.

**Correlation Analysis**

The reason why we carryout correlation anaysis before applying PCA to our datset is because we want to besure if PCA is relevant. If there are no correlations between the variables in the dataset, PCA might not be useful. This is because PCA works by finding patterns in the data, and if the variables aren't related, there aren't any patterns to find. Without correlations, PCA won't help reduce the number of variables or reveal anything new about the data. Someone had ask a question similar to the statement above on Research Gate. 

Here's a [thread](https://www.researchgate.net/post/Do-I-need-a-correlation-analysis-between-variables-before-a-PCA-analysis) of people annswering the question with similar claim that I made. 

For beginners, here's a [video](https://www.youtube.com/watch?v=J7cd1-g1O7A) explaining how to calculate correaltion value between each feature of our datset, and then visualise it using a heatmap.

[365 Data Science](https://learn.365datascience.com/) also has many videos on their platform explaining correlation analysis and how it works. You should definitely check it out.

Here are the steps you should take for this section:
1. Convert the only column with categorical data in our dataset to numerical data with the appropriate encoder.
2. Calculate the correlation value between each feature of our dataset with `corr()` and visualize the result with `heatmap()`
