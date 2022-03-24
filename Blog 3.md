# Steps of a Machine Learning Project

This blogpost describes steps involved in a standard machine learning project. Before you know how to build a machine learning model without any code you should know about these steps.

A typical machine learning project has 7 steps. 
1.	Defining the problem
2.	Collecting the data
3.	Preprocessing the data
4.	Splitting dataset
5.	Building models
6.	Evaluating models 
7.	Using the trained model


## Defining the problem
The first step of any machine learning project is defining the problem. You have to select a problem what will be solved using ML. To select a problem the most important step you can take is to start by asking yourself: do I think there’s a pattern? The fundamental assumption that underlies all machine learning problems is that there is a pattern. In this step, you would need some domain knowledge of the problem area. After you have found the problem then you can proceed to the next steps. To know more about problem formulation you can read- 

https://machinelearningmastery.com/how-to-define-your-machine-learning-problem/

## Collecting the data
Data is the most important part of a ML project. After selecting a problem to solve using machine learning you have to collect related data. You can use data collected by other parties. But your project could need you do collect data by yourself through observations and surveys. You should ensure that the data is collected and used in an ethical manner. 

Here you can find a list of publicly available datasets-

https://towardsdatascience.com/top-sources-for-machine-learning-datasets-bb6d0dc3378b

## Data Processing
In most of the cases, raw data is incomplete, noisy, inconsistent, contains errors & outliers. So, it’s crucial to preprocess this data to enhance the quality. Data preprocessing helps to clean, format, and organize the raw data, thereby making it ready-to-go for Machine Learning models. The most common steps of data preprocessing are-
1.	Identifying and handling missing values
2.	Dropping high-cardinality features
3.	Encoding categorical values
4.	Normalization
5.	Feature Engineering


To know more about data preprocessing, you can read the following blogs-

https://monkeylearn.com/blog/data-preprocessing/

https://neptune.ai/blog/data-preprocessing-guide

## Splitting the dataset
Using the whole dataset for training yields poor performance in production because of overfitting. To overcome this, the dataset is split into training, validation and testing subset so the model can generalize better. Here is short description about them-
* Train Dataset: This data is used to train the model
* Validation Dataset: This dataset is used to evaluate the performance of the model while training.
* Test Dataset: This dataset is used to provide an unbiased evaluation of the final model. 

There are several techniques to split a dataset into these subsets. If the size of dataset is between 100 to 10,00,000, then you can split it in the ratio 60:20:20. That is 60% data will go to the Training Set, 20% to the Dev Set and remaining to the Test Set. But there are no fixed rules for choosing this ratio. 

## Model Selection and Training

The performance of machine learning models varies depending on algorithm. You won’t be able to guess which algorithm will work best for your need just by seeing the data. You have to try different algorithms to find which works best for your need.
In the first blog post you have seen that there are several algorithms available for each type of problems. You have to train several models using different hyperparameters and then compare their performance to find the best one. Like for a regression problem you can choose- linear regression, random forest, and support vector machines (SVM) etc. each using different parameters. After the training you will evaluate their performance. 

## Evaluating Models
You will evaluate the performance of models using the test dataset. There are several metrics to evaluate the performance of the models. 
For regression models you can check -  
* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)
* coefficient of determination or R Squared (R2)
*	Adjusted R Squared

Here is a blog post if you want to know what each of these represent –

https://www.analyticsvidhya.com/blog/2021/05/know-the-best-evaluation-metrics-for-your-regression-model/
(You don’t have to understand the code of this blog post. Just try to understand how these metrics are calculated.) 


For classification models you can check- 
*	F1 Score
*	Accuracy
*	Precision
*	Recall
*	Specificity
*	ROC Curve

To know more about these metrics please visit- 

https://towardsdatascience.com/various-ways-to-evaluate-a-machine-learning-models-performance-230449055f15


You also have to check whether the model is overfitting or underfitting the training data. You can’t get a perfect fit, but you want to select a model at the sweet spot between underfitting and overfitting. 
A model is overfitting if it provides good performance on the training data but poor performance to test data. Underfitting refers to a model that can neither model the training data nor generalize to new data. There are several techniques to reduce overfitting or underfitting including changing training data size and model complexity. To know more about overfitting and underfitting read-

https://www.geeksforgeeks.org/underfitting-and-overfitting-in-machine-learning/

https://machinelearningmastery.com/overfitting-and-underfitting-with-machine-learning-algorithms/


## Using the trained model
How the trained model will be used depends on use cases. You can use ML to find pattern in existing data, or to predict future events. Prediction models could be used in production to predict on new input data or in research to show the possibility of using ML in certain problems. 
If you have built the model to use in production, then you will have to deploy the model on a server as an API. Then you will call the API with new input data and the API will return the prediction. 
If the model has been trained for research purposes, then you could show the result of validation set to demonstrate how machine learning in performing to solve that problem.


These are the steps of a standard machine learning project. In traditional setup, you had to write codes to in all the steps after collecting the data. But in this blog series we will show you how you can complete a machine learning project without writing any code. Bear with us. 


 



