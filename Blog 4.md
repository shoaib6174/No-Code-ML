# Azure Machine Learning Designer
In the previous blog you have seen the steps involved in ML projects. In this blog you will learn about Azure Machine Learning Designer 

Azure Machine Learning designer is a drag-and-drop interface used to train and deploy models in Azure Machine Learning. It has built-in modules for each of the steps mentioned in the previous blog. You can think of these modules as LEGO blocks. You will drag the necessary modules from the list of modules and drop them on a blank canvas. Then you will arrange them in sequence by connecting the output port of one component to an input port of another.
It will look like this- 
<p align="center">
<img alt="Complete Pipeline"  width=70% src="https://user-images.githubusercontent.com/40586752/160236520-3f8d5914-7733-45ef-a7df-5edb4e77729b.png"  >
</p>

This canvas is called a pipeline. You can say building this pipeline through drag-and-drop of modules is equivalent to coding. Once you have got this pipeline, you will submit it to a virtual machine/cluster. Then Azure Machine Learning will run the experiment for you and will return you the result. You will be able to see the metrics by clicking “Score Model” and “Evaluate Model” modules and your machine learning project will be done. You can also deploy this model by dragging and dropping few more modules. 

Don’t worry if it seems a bit overwhelming, once we will go though all the steps it will seem as easy as building a bridge using LEGO blocks. 

## Creating the Environment
In ***blogpost2  you have seen how to create Azure account and Azure Machine Learning Workspace. You need an Azure Machine Learning workspace to use the designer. To get started-

Sign in to https://ml.azure.com, and select the workspace you have already created. If you haven’t checkout- 
***Link

## Defining the problem
You have to find the problem and dataset by yourself. Azure Machine Learning Designer can’t help you there. But you can use the “Sample Dataset” for practice. In this blogpost we will work with the famous titanic dataset. We all are familiar with the titanic incident. In the titanic dataset, we have some details of each of the passengers and whether he/she had survived. We will build a prediction model to predict if a person will survive. It’s a classification problem and we will use Multiclass Logistic Regression algorithm.

## Collect The data
Once you have selected the dataset, you have to register it in Datasets of AML. You will find Datasets in the left pane under Assets of Azure Machine Learning Studio. After clicking Datasets, you will click “Create Dataset” and select the data source.  You can get the data from several sources. Select your source and then fill the necessary information in the form. Here is a gif to show how you will import a dataset from your local computer-
<p align="center">
<img alt="Creating Dataset GIF"  width=70% src="https://user-images.githubusercontent.com/40586752/160236825-107244e7-6b54-40f8-b930-b00e99d71ce9.gif"
     >
</p>


For our example, we have uploaded the titanic.csv dataset from local files and created a Dataset named Titanic. You will be able to drag-and-drop it on the canvas from Datasets. You can download the titanic.csv file from-
To know more about registering datasets please visit-

https://docs.microsoft.com/en-us/azure/machine-learning/how-to-connect-data-ui?tabs=credential

## Getting Started with AML Designer
Now we will go into AML Designer by clicking Designer in the left plane.  We will get the following window-

<p align="center">
<img alt="Creating Dataset GIF"  width=70% src="https://user-images.githubusercontent.com/40586752/160236896-c0445a05-dde9-405d-b7d8-80b98424d563.png"     >
</p>
You can see that there are some prebuild pipelines. You can select one of them and customize it according to your need. But today we will see how to build a pipeline from scratch. Click on the “+” sign from New Pipeline and you will get a blank canvas like this-

