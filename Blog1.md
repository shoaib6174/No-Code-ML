Blog 1: Introduction 
-
Importance of ML with application 
-

Why do we need no code ML?
-
We've noticed that many students, teachers, and researchers want to use Machine Learning in their projects or research but lack the necessary coding and Machine Learning knowledge.

We hope that by reading this blog series, they will gain a better understanding of the fundamentals of machine learning and how they can use it in their research without having to know how to code.

We believe that this blog series will make it easier for researchers all over the world to learn ML.


Why this blog series and the Structure of the series 
-

What is ML 
-

Machine Learning (ML) is a subset of Artificial Intelligence (AI). It allows a computer program to learn and improve from data or experience.

Machine learning is different from traditional program. 

In traditional program, we have to put data and program into computer then it will produce an ouput, but in machine learning we put data and output(result) into computer, in order to create a program which can predict the output if they receive this kind of input.

I will give you some example that will help you more understand. 

Example:

Imagine that you are a teacher and a computer program is a kid and you want them to learn about fruits by using flashcards. Each flashcard has a picture of a lemon or apple on them.

Now you teach them which one is apple and which one is lemon, the kids will learn about these two fruits by observing and remembering their attributes like color, size or shape then you shuffle the deck of lemon and apple photos after that you choose a card from the deck, it's a picture of lemon and ask them "What is on the card" but the kids said it was an apple. You know that's not the correct answer so you give them negative feedback and start to teach them again.

After repeating these processes, teach/ try / give feedback, the kid gives you more accurate answer, and they are able to classify lemon and apple.

[kid process]

Machine Learning concept is similar to how kids learn. For machine learning, we have to give input data to the model (like Attribute of lemon and apple ) then it will turn these data into set of number or machine language (like kid's memory) we call these sets of number "Feature" and we will give them the correct answer by entering these answer in the numbers, we call these numbers "Lable". 

After these processes, we will train the model, so the computer can distinguish cats and dogs according to their features.

[computer process] 




Types of ML algorithms
-
There are three main machine learning algorithms.

1. Supervised Learning 
		
For this algorithm, the model will learn from the data that we gave.
		
For example, you’re the developer who wants to build a machine learning model that will predict types of drinks using color. 
There are 3 types of drinks. Drink A is Blue, Drink B is Green, Drink C is Orange.
From these data, Color will be the feature, and Types of drinks will be the label.
The model will use features associated with labels to predict the types of drinks. Next time, if there is a blue drink, the model will predict it to be Drink A. 

Furthermore, Supervised Learning can be devided into two sub categories.

1.1 Regression

Regression is an algorithm which is used to find relationship between two or more values such as independent and dependent valuable. The output of this algorithm will be real number or continuous value. The examples of problems that you can use regression to resolve are predict stock prices, age of person or even chance of raining.

For Regression, it can be divided into the following types:
- Linear Regression 
- Neural Network Regression
- Support Network Regression
- Support vector Regression
- Decision Tree Regression
- Lasso Regression
- Ridge Regression

1.2 Classification

Classification is an algorithm that allows the model to learn from the given dataset or observation. It must draw a conclusion from the observed value and identify which category that value belongs to. This type of algorithm will be used to predict discrete values like Yes or No, Spam email or Not.

For classification, it can be divided into the following types:
- Naïve Bayes
- K-Nearest Neighbours
- Support Vector Machines
- Decision Tree Classification
- Random Forest Classification

![IMG_0849](https://user-images.githubusercontent.com/96424191/160169107-7e3c7c40-6b2b-47b0-93b5-9cb76df5486f.jpg)

The terms "regression" and "classification" are not interchangeable. First, we will predict a continuous quantity for linear regression, but a discrete class label for classification. The outputs differ as well; the result of linear regression is a value, whereas the result of classification is a non-value output, such as yes or no dog or cat.

Learn more: https://www.sciencedirect.com/topics/computer-science/supervised-learning

2.2 Unsupervised Learning 
		
The model in this algorithm will learn from patterns. 
	
This type of method will enable the model to detect data patterns on its own.
		
If you have data on student grades and hours of study, you can enter it into the model, which will work, and then turn it into a graph, 	with the x-axis and y-axis representing hours of study and grades, respectively. Each student's data will be plotted into the graph, and you will 	notice that there are clusters of data, which we can interpret. First, students with a high study hour tend to earn a good mark, whereas those with a 	lesser study hour tend to get a poorer grade.	
		
Learn more: https://towardsdatascience.com/unsupervised-learning-and-data-clustering-eeecb78b422a

2.3 Reinforcement Learning 
	
The model in this algorithm will learn from feedback.
	
It's as if you took a photo of a chihuahua and a muffin and used it to teach a model to recognize chihuahuas and muffins. If you show the machine a snapshot of the muffin with the model saying "it's Chihuahua" and give it negative feedback, the system will learn from it and increase its accuracy. Finally, it can distinguish between chihuahua and muffin in the image.
	
Learn more: https://www.coursera.org/specializations/reinforcement-learning

Regression model with parameters
-

Linear regression

Linear Regression is the simplest form of machine learning algorithm to grasp; it uses a xy graph and a straight line called the "Regression line" to attempt to explain the relationship between two variables.

![IMG_0848](https://user-images.githubusercontent.com/96424191/160169084-9e1c6f61-fac1-420a-9ed2-186d49b0cb63.jpg)

As shown in the diagram, data for shirt size (x-axis, independent value) and shirt price (y-axis, dependent value) are plotted onto a graph and draw a line, then we will measure the distances between each point and our line then sum it up, our Regression line will be the one that has shortest distance.

Classification model with parameters
-

K-Nearest Neighbour

K-Nearest Neighbour is a simple algorithm which is used to classify data. Its concept is just like "The similar thing will be close to each other". This is the example that will help you more understand. 

For example, you have three groups of data on the graph then there are new point add to the graph, we have to find out that which one of these three group is our new point should be with. So, we have to find k nearest neighbour of the point.

![IMG_599E95E65959-1](https://user-images.githubusercontent.com/96424191/160191365-a5969eb6-4b01-466b-9ef6-160b0449d11e.jpeg)

To find the k value, first we have to calculate the distances between our given point and other points then sort the distance from the nearest to the furthest. 

![IMG_910C889AE8A6-1](https://user-images.githubusercontent.com/96424191/160191463-47bab16f-404d-45cc-b28d-bfffce3c2d1d.jpeg)

After sorting these values, we will assign our new point to the class that most common among k nearest neighbor. Amount of k value also affect the model, smaller k value cause lower bias and higher variance and overfitting but larger k value casue higher bias, lower variance and underfitting. So, you should choose the k value that keep balance between large and small k value.

![IMG_86B58E3A3F4E-1](https://user-images.githubusercontent.com/96424191/160191992-26b2b498-3207-434f-bb18-441233016143.jpeg)

