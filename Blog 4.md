# Azure Machine Learning Designer
In the previous blog you have seen the steps involved in ML projects. In this blog you will learn about Azure Machine Learning Designer 

Azure Machine Learning designer is a drag-and-drop interface used to train and deploy models in Azure Machine Learning. It has built-in modules for each of the steps mentioned in the previous blog. You can think of these modules as LEGO blocks. You will drag the necessary modules from the list of modules and drop them on a blank canvas. Then you will arrange them in sequence by connecting the output port of one component to an input port of another.
It will look like this- 
<p align="center">
<img alt="Complete Pipeline"  width=50% src="https://user-images.githubusercontent.com/40586752/160236520-3f8d5914-7733-45ef-a7df-5edb4e77729b.png"  >
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
Once you have selected the dataset, you have to register it in **Datasets** of AML Workspace. You will find **Datasets** in the left pane under Assets of Azure Machine Learning Studio. After clicking Datasets, you will click **Create Dataset** and select the data source.  You can get the data from several sources. Select your source and then fill the necessary information in the form. Here is a gif to show how you will import a dataset from your local computer-
<p align="center">
<img alt="Creating Dataset GIF"  width=70% src="https://user-images.githubusercontent.com/40586752/160236825-107244e7-6b54-40f8-b930-b00e99d71ce9.gif"
     >
</p>


For our example, we have uploaded the **titanic.csv** dataset from local files and created a Dataset named Titanic. You will be able to drag-and-drop it on the canvas from Datasets. You can download the **titanic.csv** file from- **link**
To know more about registering datasets please visit-


https://docs.microsoft.com/en-us/azure/machine-learning/how-to-connect-data-ui?tabs=credential

## Getting Started with AML Designer
Now we will go into AML Designer by clicking **Designer** in the left plane.  We will get the following window-

<p align="center">
<img alt="Creating Dataset GIF"  width=70% src="https://user-images.githubusercontent.com/40586752/160236896-c0445a05-dde9-405d-b7d8-80b98424d563.png" >
</p>

You can see that there are some prebuild pipelines. You can select one of them and customize it according to your need. But today we will see how to build a pipeline from scratch. Click on the **Plus Sign(+)** from **New Pipeline** and you will get a blank canvas like this-

<p align="center">
<img alt="Creating Dataset GIF"  width=70% src="https://user-images.githubusercontent.com/40586752/160237535-044940b0-5673-4e9c-8886-7090974d6332.png" >
</p>


Take some time to get familiar with the environment and **Asset Library**. 


## Import Data
To the left of the pipeline canvas is a palette of datasets and components. Select **Datasets** to view the dataset you have just registered. Select the dataset and drag it onto the canvas. It’s equivalent to importing data. 
You can also use any dataset from **Sample Datasets**. Here is how you will do that-
<p align="center">
<img alt="Drag-and-Drop Dataset"  width=70% src="https://user-images.githubusercontent.com/40586752/160237255-146ac075-0a09-4ec0-ae82-498f4f2543f4.gif" >
</p>

You can preview the data by right clicking on the dataset component in the canvas.
<img alt="Preview Titanic Dataset"  width=70% src="https://user-images.githubusercontent.com/40586752/160237287-19806353-6706-4b5b-9538-555bf7b405a1.png" >
</p>


## Data Processing
AML Designer has several components for data processing. Hover your mouse pointer on each of them to know their function and you can also check documentation to Learn More.


<img alt="Data Tramsformation Components"   src="https://user-images.githubusercontent.com/40586752/160237437-b16787c8-0cc4-4791-8a2f-84ed5c956aa8.png">
</p>

For our example, at first, we will use **Select Columns in Dataset** component. 
-	Drag the **Select Columns in Dataset** component onto the canvas. Drop the component below the dataset component.
-	Connect the **Titanic** dataset to the **Select Columns in Dataset** component. Drag from the dataset's output port, which is the small circle at the bottom of the dataset on the canvas, to the input port of **Select Columns in Dataset**, which is the small circle at the top of the component.

<img alt="Connecting Components"   src="https://user-images.githubusercontent.com/40586752/160237625-4105b27c-2e07-4225-a635-c3a0a838d6f7.gif">
</p>

-	Now click on **Select Columns in Dataset** component and a component details pane will appear in the left. Select **Edit Column**. 
-	You can select columns **By rules** or **By name**. Select **By name** and click the plus sign beside the column name in **Available columns**. The added columns will be moved to **Selected columns**. 
-	Click **Save**.
	
For this example, we have selected the following columns-

<img alt="Selecting Columns"   src="https://user-images.githubusercontent.com/40586752/160237713-990794f1-dab1-479e-8e9a-51b697b06e8e.png">
</p>

We have also used the **Clean missing data** component. 
