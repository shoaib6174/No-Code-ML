# Azure Machine Learning Designer
In the previous blog you have seen the steps involved in ML projects. In this blog you will learn about Azure Machine Learning Designer 

Azure Machine Learning designer is a drag-and-drop interface used to train and deploy models in Azure Machine Learning. It has built-in modules/components for each of the steps mentioned in the previous blog. You can think of these components as LEGO blocks. You will drag the necessary components from the list of components and drop them on a blank canvas. Then you will arrange them in sequence by connecting the output port of one component to an input port of another. This sequence of componenets is called a pipeline. It will look like this- 
<p align="center">
<img alt="Complete Pipeline"  style='border: 5px solid black' width=50% src="https://user-images.githubusercontent.com/40586752/160236520-3f8d5914-7733-45ef-a7df-5edb4e77729b.png"  >
</p>

 You can say building this pipeline through drag-and-drop of modules is equivalent to coding. Once you have got this pipeline, you will submit it to a virtual machine/cluster. Then Azure Machine Learning will run the experiment for you and will return you the result. You will be able to see the metrics by clicking “Score Model” and “Evaluate Model” modules and your machine learning project will be done. You can also deploy this model by dragging and dropping few more modules. 

Don’t worry if it seems a bit overwhelming, once we will go though all the steps it will seem as easy as building a bridge using LEGO blocks. 

## Creating the Environment
In **blogpost2**  you have seen how to create Azure account and Azure Machine Learning Workspace. You need an Azure Machine Learning workspace to use the designer. To get started-

Sign in to https://ml.azure.com, and select the workspace you have already created. If you haven’t checkout- 
***Link***

## Defining the problem
You have to find the problem and dataset by yourself. Azure Machine Learning Designer can’t help you there. But you can use the “Sample Dataset” for practice. In this blog we will work with the famous titanic dataset. We all are familiar with the titanic incident. In the titanic dataset, we have some details of each of the passengers and whether he/she had survived. We will build a prediction model to predict if a person will survive. It’s a classification problem and we will use Multiclass Logistic Regression algorithm.

## Collect The data
Once you have selected the dataset, you have to register it in **Datasets** of AML Workspace. You will find **Datasets** in the left pane under Assets section of Azure Machine Learning Studio. After clicking Datasets, you will click **Create Dataset** and select the data source.  You can get the data from several sources. Enter your source and then fill the necessary information in the form. Here is a gif to show how you will import a dataset from your local computer-
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
<p align="center">
<img alt="Preview Titanic Dataset"  width=70% src="https://user-images.githubusercontent.com/40586752/160237287-19806353-6706-4b5b-9538-555bf7b405a1.png" >
</p>


## Data Processing
AML Designer has several components for data processing. Hover your mouse pointer on each of them to know their function and you can also check documentation to Learn More.

<p align="center">
<img alt="Data Tramsformation Components"   src="https://user-images.githubusercontent.com/40586752/160237437-b16787c8-0cc4-4791-8a2f-84ed5c956aa8.png">
</p>

For our example, at first, we will use **Select Columns in Dataset** component. 
-	Drag the **Select Columns in Dataset** component onto the canvas. Drop the component below the dataset component.
-	Connect the **Titanic** dataset to the **Select Columns in Dataset** component. Drag from the dataset's output port, which is the small circle at the bottom of the dataset on the canvas, to the input port of **Select Columns in Dataset**, which is the small circle at the top of the component.
-	
<p align="center">
<img alt="Connecting Components"   src="https://user-images.githubusercontent.com/40586752/160237625-4105b27c-2e07-4225-a635-c3a0a838d6f7.gif">
</p>

-	Now click on **Select Columns in Dataset** component and a component details pane will appear in the left. Select **Edit Column**. 
-	You can select columns **By rules** or **By name**. Select **By name** and click the plus sign beside the column name in **Available columns**. The added columns will be moved to **Selected columns**. 
-	Click **Save**.
	
For this example, we have selected the following columns-

<p align="center">
<img alt="Selecting Columns"   src="https://user-images.githubusercontent.com/40586752/160237840-e1bc71bb-bc75-4565-83be-89a1701f21b3.png">
</p>

We have also used the **Clean missing data** component. 


-	In the component palette to the left of the canvas, expand the section **Data Transformation**, and find the **Clean Missing Data ** component. 
-	Drag the **Clean Missing Data** component to the pipeline canvas. 
-	Connect it to the **Select Columns in Dataset ** component.
-	Click the Clean Missing Data component and then select **Edit Column** from the component details pane.
-	In the Columns to be cleaned window that appears, expand the drop-down menu next to **Include**. Select, **All columns ** and click **Save**. 
-	Now in the component details pane to the right of the canvas, select **Remove entire row** under **Cleaning mode**.
 
You can use the **Clean Missing Data ** component multiple times to add different cleaning mode for different columns.
![clean missing data modes](https://user-images.githubusercontent.com/40586752/160238249-69eadc48-d4e1-47cf-be7c-2df06d9d8c2a.png)


-	We have also used the **Normalize Data** component to transform our data. 
-	Drag the **Normalize Data** component to the pipeline canvas. 
-	Connect it to the output of **Clean Missing Data** component. 
-	Then in the component details tab select **Transformation method** and **Columns to transform**. 
For our example, we have selected **MinMax** as **Transformation method** and used in on **Age** column.
 
 ![normalize data](https://user-images.githubusercontent.com/40586752/160238254-91a22cec-f905-497a-a5b4-7430455b30c9.png)

Now we are done with data processing. The canvas will now look like this-
  
![upto data processing](https://user-images.githubusercontent.com/40586752/160238275-8af234a7-719e-4c58-bf7a-0791b8377a33.png)


## Splitting Dataset

For splitting the dataset, you will drag-and-drop **Split Data** component from **Data Transformation** section and connect it with the left port of **Normalize Data** component. Then In the component details pane to the right of the canvas, set the **Fraction of rows in the first output dataset** to 0.7. You don’t have to select any ratio for validation set. AML Designer will do that itself while training. 
This 0.7 option splits 70 percent of the data to train the model and 30 percent for testing it. The 70 percent dataset will be accessible through the left output port. The remaining data will be available through the right output port.
 
![split data](https://user-images.githubusercontent.com/40586752/160238279-16ae14ca-73b7-4033-a724-af9a170fbc7b.png)


## Model Selection and Training
AML Designer has some built in algorithms for you. In the component palette, expand **Machine Learning Algorithms**. This option displays several categories of components that you can use to initialize learning algorithms. You will select the algorithms that’s best suited for your problem. Our example is a classification problem. So we have chosen **Multiclass Logistic Regression** from **Classification Categories** of **Machine Learning Algorithms** section and dragged it onto the canvas. 
Now for training the model-
-	Drag-and-drop the **Train Model** component from **Module Training** section
-	Connect the output of the **Multiclass Logistic Regression** component to the left input of the **Train Model ** component. 
-	Also connect the training data output (left port) of the **Split Data** component to the right input of the **Train Model** component.
![image](https://user-images.githubusercontent.com/40586752/160238293-6b7c74d0-eac9-46e4-a051-90a0c83ce3a0.png)

Now you will select the label column as it is a supervised learning-
-	Select the **Train Model ** component from **Model Training** section. 
-	In the component details pane to the right of the canvas, select **Edit column ** selector. In the **Label column** dialog box, expand the drop-down menu and select **Column names**. 
-	In the text box beside **Column names**, enter the name of the column which contains the labels that your model is going to predict.
 For our example, we have entered **Survived**. Now click **Save**.
 

## Evaluate Model
For evaluating the model, you have to check how your model has done on the test dataset. For that, at first you have to score your model using **Score Model ** component. 
-	Drag-and-drop **Train Model** component from **Model Training**  section onto the canvas below **Train Model**. 
-	Connect the output of the **Train Model** component to the left input port of **Score Model**. 
-	Connect the test data output (right port) of the **Split Data** component to the right input port of **Score Model**.
Now to get the evaluation metrics, find the **Evaluate Model** component and drag the component to the pipeline canvas. Connect the output of the **Score Model** component to the left input of **Evaluate Model**. The final pipeline should look something like this-
 

## Submitting The Pipeline
A pipeline runs on a compute target, which is a compute resource that's attached to your workspace. Before submitting the pipeline you have to specify compute target. For that- 
-	Next to the pipeline name, select the **Gear icon** at the top of the canvas to open the **Settings** pane.
-	In the **Settings** pane to the right of the canvas, select **Select compute target**.
-	Enter a name for the compute resource and click **Save**
It will take some time to create the compute target. Once the compute target is ready-
-	Click on **Submit** at the top of the canvas.
-	In the **Set up pipeline run** dialog box, select Create new.
-	For **New experiment Name**, enter **Titanic** and then click **Submit**
 
It will take few minutes for the pipeline to finish running. You can view run status and details at the top right of the canvas.

## View scored labels

After the run completes, you can view the results of the pipeline run. First, look at the predictions generated by the classification  model.
Right-click the **Score Model ** component and select **Preview data** > **Scored dataset** to view its output.
Here the Scored Labels column represents the prediction of the model for each row of the test dataset-
 

## Evaluate models

Use the **Evaluate Model** to see how well the trained model performed on the test dataset.
Right-click the **Evaluate Model** component and select **Preview data** > **Evaluation results** to view its output.
Here is the evaluation metrics for our experiment- 
 
This is the output of your project. You can see how easily we have built a prediction model using AML Designer. Now you can also deploy this model by dragging and dropping some more components. We will not dive into that but if you interested to see check –
https://docs.microsoft.com/en-us/azure/machine-learning/tutorial-designer-automobile-price-deploy





