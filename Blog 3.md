# Getting Started with Azure Machine Learning

The target of this blog series is to learn about how to build machine learning models without coding using **Azure Machine Learning Designer** and **Azure AutoML**. Both of them are services of **Azure Machine Learning**. So before getting started with building models we should know about **Azure** and **Azure Machine Learning**.


Azure is a public cloud computing platform—with solutions including Infrastructure as a Service (IaaS), Platform as a Service (PaaS), Software as a Service (SaaS), and ML as a Service (MLaaS). To know more about Azure and clould computing please visit-

https://azure.microsoft.com/en-us/overview/what-is-cloud-computing/#uses

**Azure Machine Learning** is a cloud service offered by Azure for accelerating and managing the machine learning project lifecycle. **Azure Machine Learning Designer** and **Azure AutoML** are two services of **Azure Machine Learning** for making the ML model building task easier. To use them you will need an Azure account.


## Creating Azure Free Account
A free account is one way to access their services under the Microsoft Customer Agreement, which provides access to all Azure services and does not block customers from building their ideas into production. With the Azure free account, eligible customers receive $200 in credits, which can be used within the first 30 days on most Azure services. In addition, you get free monthly amounts of two groups of services: popular services, which are free for 12 months, and more than 40 other services that are free always. 

A free account is enough for getting started. But for production grade work, you will need more resources and you have to pay for them.
 
We will be showing step by step how to make your own Free Azure account, follow the steps as we break down everything you need to do for you can have access to Azure services.
### How to sign up (Step by step)
1. Go to https://azure.microsoft.com/en-in/free/


![image](https://user-images.githubusercontent.com/98630988/160293129-b018558d-4073-47f9-bf0b-ee8484597452.png)


2. You will press **Start free** button
3. Then it will ask you to log in to your **Microsoft account**, if you don't have one you can create one by your own.
4. Next, you will log in, and it will show the following screen:


![image](https://user-images.githubusercontent.com/98630988/160293365-c56fecd9-efa3-4b09-bf82-e9014466e009.png)


You will have to agree to the following terms for accessing their services.


5. After those selected it will ask you verification by phone, you will need to add your phone, and you will either receive a **text message or a call** depending on what you chose.
6. Finally, it will ask you to verify your identity by card, which you will need to write down your information. Note that they won't charge you for doing so, unless you change your account to pay-as-you-go pricing.
![image](https://user-images.githubusercontent.com/98630988/160293609-66ec4c50-7d95-4c87-a1b0-18f3982331d2.png)
7. By following up these simple steps, you will have access to Azure, and you will create your account. Then you can access to your account by clicking the top right corner of your avatar, or simply access by this link: https://portal.azure.com




### Azure free support resource 
Here are some links of Azure basics that will cover everything you require related to their services and for better understatement of Azure.
- [x] [Microsoft Azure Fundamentals: Describe core Azure concepts](https://docs.microsoft.com/en-us/learn/paths/az-900-describe-cloud-concepts/)
- [x] [Azure for Researchers part 1: Introduction to Cloud Computing](https://docs.microsoft.com/en-us/learn/paths/researcher-introduction-to-cloud-computing/)



## Azure for Student 
Some of you may not have acess to credit cards. If you are a student then you can take benefits of Azure for Students.

Azure for Students gives you $100 USD credits for 12 months and access to more than 25 free products, including compute, network, storage, and databases. Any charges incurred during this period are deducted from the credit.


##### The differences between Free Account
You may be confused of what is the distinction between free account and student account, generally they are a similar, yet the benefits are unique, while Azure for Students gives you 100 USD credit for a considerable length of time and admittance to in excess of 25 free items, the Free Account gives you 200 USD in credits, which can be utilized inside the initial 30 days on most Azure services. Also, you get free month-to-month measures of two gatherings of administrations: well known administrations, which are free for quite a long time, and in excess of 40 different services that are free consistently.


### How to Get the Azure for student credits
#### Get it directly using Education Email
For Students who have an Education Email, they can get the Azure Student credits directly from Azure. You will have to access to [Azure for Students](https://azure.microsoft.com/en-us/free/students/?WT.mc_id=academic-0000-cxa), and create an account by using your Student email. It will ask you for academic verification, and you will get access to Azure with your free credits. 


#### Get it from GitHub Student Pack
For students who don’t have an Education Email, they can get the Azure student credits from GitHub Student Pack by using an ID card and GitHub Account.
Here is a step-by-step guide of how to [Apply for a student developer pack](https://docs.github.com/en/education/explore-the-benefits-of-teaching-and-learning-with-github-education/use-github-for-your-schoolwork/apply-for-a-student-developer-pack)


## Create a workspace
An Azure Machine Learning workspace is a foundational resource in the cloud that you use to experiment, train, and deploy machine learning models. It's needed to work with **Azure Machine Learning Designer** and **Azure AutoML**. It ties your Azure subscription and resource group to an easily consumed object in the service. Now let's see how to create it.


Once you have got your subscription-

- Sign in to https://portal.azure.com by using the credentials for your Azure subscription.


- In the upper-left corner of the Azure portal, select the three bars, then **+ Create a resource**.

![Create a resource.](https://user-images.githubusercontent.com/40586752/160423868-6968ac9a-861a-46d9-8e87-d1d09101fc48.png)


- Use the search bar to find **Machine Learning**.

- Select **Machine Learning**.


- In the Machine Learning pane, select **Create** to begin.
![image](https://user-images.githubusercontent.com/40586752/160424640-5911cc7f-f909-4b8a-b452-307c91b043cc.png)

- In the **Basics** of **Create a machine learning workspace** form select your subscription from **Subscription** drop-down menu
- Select **Create new** to create a new **Resource Group** . Then provide a name for your resource group. We entered "NoCodeML**. Then select **OK**.
- Enter **Workspace Name**, **Region**
- For **Storage Account** select **Create new**. In the **Create new storage account** from enter **Name** and select 
**Locally-redundant storage (LRS)** from **Replication** drop-down menu. Select **Save**.

- For **Key Value** and **Application insights** select **Create new**. Then in the form enter **Name** of your choice and select **Save**.
- For **Container registry** select **Create new** and enter **Name** in the form. Select **Basic** from **SKU** drop-down menu. Select **Save** 

The **Basics** form will now look like this- 
![Create ML Workspace](https://user-images.githubusercontent.com/40586752/160427739-70fd6e07-69ed-4282-823a-f8884895af63.png)


- Select **Review + Create** to create the workspace. Once the validation is passed, select **Create**.

It can take several minutes to create your workspace in the cloud. When the process is finished, a deployment success message appears.

To view the new workspace, select Go to resource. From the portal view of your workspace, select Launch studio to go to the Azure Machine Learning studio.

Now you are ready for working with **Azure Machine Learning Designer** and **Azure AutoML**. 
