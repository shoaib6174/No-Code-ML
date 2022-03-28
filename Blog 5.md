
In the previous blog you have seen, how you can build a ML project by dragging and dropping components in a graphical interface named AML Designer. Though it’s very easy, but you still had to follow all the steps by yourself. You had to choose the data cleaning and transformation rules, machine learning algorithm and its parameters. Then after getting the metrics, you had to evaluate it yourself and if you aren’t satisfied with the result then you had to select new parameters or algorithms. Even if it’s easy but finding the best model can be time consuming and iterative. 

What if I told you there is an automated way where you would just upload the dataset and select a few configurations and then the system will do the rest. Yes, there is, and it is called Automated Machine Learning, also referred to as Automated ML or **AutoML**.

AutoML is the process of automating the time-consuming, iterative tasks of machine learning model development. It will try different data processing methods and a bunch of ML algorithms by itself and return you the best model. Isn’t it amazing? I was astonished when I first came across it. 

In Azure AutoML you don’t have to preprocess and transform the data by yourself. It has a feature called Automatic Featurization. It will impute missing values, handle class imbalance, scale or normalize numeric data, drop high cardinality features, generate more features if necessary. It will also take care of splitting the dataset. 

Azure AutoML has a pool of algorithms for supported tasks. It supports classification, regression, & forecasting. So, you have to select the task that you want to accomplish and select the label/target column. Then you will select a Compute target  Azure AutoML will run all the algorithms in combination with the data processing methods. It will also change the hyperparameters automatically. Once done it will return you the metrics for all the models and the best model. You can also automatically deploy the model as a REST API. 

So, if we summarize, you just have to-
- Upload the dataset
- Select the target/label column
- Select compute target
- Enable Auto Featurization
- Select the task type (classification, regression, or forecasting)

Then you will click run and after some time you will get the best model for your dataset. Doesn’t it sound like dream! It did to me. 

Azure AutoML also provides us flexibility. 
-	You can fix data processing method for columns by configuring featurization settings
-	You can select the algorithms to run instead of running all the available algorithms
-	You can select exit criterion, like- Training job time and Metric score threshold. It will help to save resources. 

Now we will see how we can build a model for our Titanic Dataset using AutoML.
### Get the environment ready
You need an Azure Machine Learning workspace to use the designer. To get started-
-	Sign in to https://ml.azure.com, and select the workspace you have already created. If you haven’t checkout- **Link**
-	Select your subscription and the workspace you created.
-	Select Get started.
-	In the left pane, select Automated ML under the Author section.
-	Select +New automated ML run.

### Select Dataset
If you have a dataset registered in **Datasets** you can use that. Otherwise, you can get a new dataset from local files, datastore, web files or Open Datasets. Here we will show you how to create a dataset from local files-
-	Download the **titanic.csv** from **link**
-	On the **Select dataset** form, select **From local files** from the **+Create dataset** drop-down.
<p align='center'>    <kbd> <img alt='Select Dataset'  width=70% src='https://user-images.githubusercontent.com/40586752/160261606-564cc6be-c4c5-4233-bcf5-1190fc7c7161.png' > </kbd>  </p>

-	On the **Basic info** form, and enter ‘Titanic Dataset’ as name.
<p align='center'>    <kbd> <img alt='Basic Info'  width=70% src='https://user-images.githubusercontent.com/40586752/160261607-1d740cab-8687-48bc-9644-e1f0f40d757a.png' > </kbd>  </p>

-	Select **Next** on the bottom left.
-	On the **Datastore and file selection** form, select the default datastore that was automatically set up during your workspace creation, **workspaceblobstore (Azure Blob Storage)**. 
<p align='center'>    <kbd> <img alt='Pipeline'  width=70% src='https://user-images.githubusercontent.com/40586752/160261609-f511109f-8d8c-48d1-ac00-93793376da9b.png' > </kbd>  </p>

-	Select **Browse files** from the **Browse** drop-down and choose the **titanic.csv** file on your local computer.
-	Select **Next**
-	On the **Settings and preview** form, Select **Next** if you don’t have any changes. It will look like this-


<p align='center'>    <kbd> <img alt='Settings and preview'  width=70%  src='https://user-images.githubusercontent.com/40586752/160261612-51be1615-a6db-4fb9-9a47-d5d5bb48bc19.png' > </kbd>  </p>

-	On the **Schema** form, you can ignore any columns if you want. Here we decided not to include **PassengerId** and **Name** column by toggling the button in **Include** column. You can also change data types here. Once done select **Next**.
<p align='center'>    <kbd> <img alt='Schema'  width=70% src='https://user-images.githubusercontent.com/40586752/160261614-f78e7bed-f896-46f7-9b4f-bd82d5d6b6e1.png' > </kbd>  </p>

-	On the **Confirm details** form, verify the information matches what was previously populated on the **Basic info** and **Settings and preview** forms.
<p align='center'>    <kbd> <img alt='Confirm Details'  width=70% src='https://user-images.githubusercontent.com/40586752/160261616-a3fb718e-f786-441e-ad74-58c67880320b.png' > </kbd>  </p>

-	Select **Create** to complete the creation of your dataset.
-	Once the dataset is created you will be on **Select dataset** form. It may take some time for the dataset list to be updated. Click refresh after very few seconds until it appears on the list.
-	Select your dataset once it appears in the list and then select **Next**.


 ### Configure Run
Now you have to set up your compute target and select the column in your data that you want your model to predict.
In the **Configure Run** form-
-	Select **Create new** under **Experiment name**
-	Enter ‘TitanicSurvialPrediction’ as **New experiment name**
-	Select **Servived** from the **Target column** drop-down menu.
-	Select **Compute Instance** from **Select compute type** drop-down
 <p align='center'>    <kbd> <img alt='Configure Run'  width=70% src='https://user-images.githubusercontent.com/40586752/160261618-e671e17b-bae6-4a46-b4fb-d04698b09b45.png' > </kbd>  </p>

-	Select **+ New** to create a new compute instance
-	 In the **Create compute Instance** form, select a virtual machine from the recommended list. We have selected **Standard_DS11_v2** as our dataset is very small. Now click **Create**. It will take a couple of minutes to complete.
<p align='center'>    <kbd> <img alt='Create Compute Instance'  width=70% src='https://user-images.githubusercontent.com/40586752/160261620-46d2791a-1356-4615-a586-c6d4ee8d75a6.png' > </kbd>  </p>

-	 After creation, select your new compute target from the drop-down list and Select **Next**


### Select task and settings
Here you have to select the task type for the experiment and additional configuration and featurization settings. Our task is a classification task, so select **Classification** in the **Select task and settings** form. Now you can click **Next** but we want to play with and additional configuration and featurization settings.

<p align='center'>    <kbd> <img alt='Select task and settings'  width=70% src='https://user-images.githubusercontent.com/40586752/160261626-22086ae5-0bd0-4361-a11c-abaafbfc84a7.png'> </kbd>  </p>

-	Select **View featurization settings**
<p align='center'>    <kbd> <img alt='featurization settings'  width=70% src='https://user-images.githubusercontent.com/40586752/160261627-d9c0111a-dc3a-478a-af39-e4da16d14909.png'> </kbd>  </p>

-	In the **Featurization** form, we can exclude columns, change feature type and imputation method. 

-	We have excluded Ticket, Fare, Cabin and Embarked columns. You have also selected feature type for some columns. You can see the changes in below-
 
-	Click **Save**


In additional configuration. we can change **Primary Metric**, select allowed or blocked models and set **Exit criterion**.
-	Select **View additional configuration settings**
-	Select **Accuracy** as primary metric from **Primary Metric**
-	Unselect **Use all supported models**
-	In **Allowed models**, we can select the models we want to try. We have selected Logistic Regression, Decision Tree, XGBBoostClassifier, KNN, SVM.
-	In **Exit criterion** set ** Training job time (hours)** to **0.5** and ** Metric score threshold** to **0.95**. Its important to select **Exit Criterion** so that the experiment doesn’t run for a very long time.
 <p align='center'>    <kbd> <img alt='additional configuration settings'  width=70% src='https://user-images.githubusercontent.com/40586752/160261638-c52ae1f1-16e5-4664-b8f0-dc839d46266d.png' > </kbd>  </p>

-	Select **Save**
-	Select **Next** from **Select task and settings** form.


### Validate and Test
In the **Validate and test** form, you can select validation type but it’s optional.  
<p align='center'>    <kbd> <img alt=' Validate and Test'  width=70% src='https://user-images.githubusercontent.com/40586752/160261643-f7b9e3a6-ab8b-441d-bafb-e7310997e967.png' > </kbd>  </p>

Here we have selected **Validation type** to **Train-validation split** and **Percentage validation of data** to **20**. So, it will use 20% entries of our **Titanic Dataset** for testing the model performance.

### Run experiment 
To run your experiment, select **Finish**. The **Run details** screen opens with the **Run status** at the top next to the run number. This status updates as the experiment progresses. Notifications also appear in the top right corner of the studio, to inform you of the status of your experiment.
 

### Explore models
Navigate to the **Models** tab to see the algorithms (models) tested. By default, the models are ordered by metric score as they complete. For this tutorial, the model that scores the highest based on the chosen **Accuracy** metric is at the top of the list.

While you wait for all of the experiment models to finish, select the Algorithm name of a completed model to explore its performance details.

The following navigates through the Details and the Metrics tabs to view the selected model's properties, metrics, and performance charts.
![run-detail (1)](https://user-images.githubusercontent.com/40586752/160436305-db3a4092-c14d-46de-9cdd-fcb81d9a9448.gif)


### Model explanations
While you wait for the models to complete, you can also take a look at model explanations and see which data features (raw or engineered) influenced a particular model's predictions.

These model explanations can be generated on demand, and are summarized in the model explanations dashboard that's part of the Explanations (preview) tab.

To generate model explanations-

- Select the **Models** tab.
- Select a model
- Select the Explain model button at the top. On the right, the Explain model pane appears.
- Select the compute terget that you created previously. This compute cluster initiates a child run to generate the model explanations
- Select Create at the bottom. A green success message appears towards the top of your screen.
- Select the Explanations (preview) button. This tab populates once the explainability run completes.
- Select the Aggregate feature importance tab on the right. This chart shows which data features influenced the predictions of the selected model.

In our example gender appears to have the most influence on the predictions of this model which was true for the titanic accident as women and childern were priotized.
![image](https://user-images.githubusercontent.com/40586752/160437753-fc5a0a43-fa9d-4717-aa90-6ad1905ce7e7.png)

You can use the best model to show the outcome of your research or you can deploy it in production. 
 To deploy a model-
 - Select that model from **Models** to open the model-specific page.
 - Populate the Deploy a model pane as follows: 
     - Deployment name:	my-automl-deploy
     - Compute type: Azure Container Instance (ACI)
     - Enable authentication:	Disable
     - Use custom deployments:	Disable
- Select Deploy.
A green success message appears at the top of the Run screen, and in the Model summary pane, a status message appears under Deploy status. Select Refresh periodically to check the deployment status. So it was that easy to deploy the model. How to consume the model as web service is beyond the scope of this blogpost. Developer will take care of that.


## Conclusion

We have reached the end of this blog series. The purpose of this blog sereis is to familiarize you with the concepts machine learning and showing you how you can build a machine learning model by yourself. We hope this blog series will help you to incroparate machine learning in your research work. 
