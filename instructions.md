# Red Hat OpenShift AI (RHOAI) Environment and Snorkel AI
Red Hat OpenShift AI (RHOAI) combines the scalability and flexibility of containerization with the capabilities of machine learning and data analytics. With Red Hat OpenShift AI, data scientists and developers can efficiently collaborate, deploy, and manage their models and applications in a secure and streamlined environment. Snorkel AI is a data platform that specialies in building and iterating unlabeled data sets to machine learning models. In this tutorial, we will learn how to create a RHOAI environment and walk through 2 Snorkel AI tutorials, one for data labeling and for information extraction. 

## RHODS installation
RHOAI can be installed from the OpenShift Web Console. Navigate back to the "**Operators**" tab and select "**OperatorHub**". In the text box now type `RHODS` and select the "**Red Hat OpenShift Data Science**" operator and click on "**Install**". <br />

<img width="940" alt="Screenshot 2024-01-29 at 3 50 28 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/7b9dd95e-e24c-404f-8ecb-6aa51520acdd"> <br />

To start the installation press again the blue "**Install**" button. We can check to see if our operator successfully deployed under the "**Operators**" tab and select "**Installed Operators**". <br />

<img width="1682" alt="Screenshot 2024-01-29 at 4 53 52 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/fc7f5f47-5618-421b-aa3a-1a90a02e4353"> <br />

Now that our operator has successfully deployed, click on it and create a new "**Data Science Cluster**" instance.  <br />

<img width="719" alt="Screenshot 2024-01-29 at 4 55 57 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/76cf9ba8-8099-4a97-93fc-f2f989f5acf0"> <br />

We don't need to make any changes to the default settings, so we'll just click "**Create**". <br />

<img width="1127" alt="Screenshot 2024-01-29 at 4 56 30 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/3ade76b6-fbfa-463e-a357-4aa5a4f30787"> <br />

Once this has successfully deployed, we'll go to access our RHOAI Dashboard. On the administrator menu, head to "**Networking**" and click on "**Routes**". In Routes, we're going to change the project to "**redhat-ods-application**", which is where we can access the address to our RHOAI application. <br />

<img width="804" alt="Screenshot 2024-01-29 at 3 53 28 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/4dfe1c64-7980-40f3-989b-7a201352ca29"> <br />

There should only be one route available, so go ahead and click the address to take you to the RHOAI dashboard. <br />

<img width="1684" alt="Screenshot 2024-01-29 at 3 53 17 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/17dde84f-acb4-4bc1-813d-3c32f1f48d25"> <br />

## Create a new Data Science Project
Now we're going to set up our Jupyter environment so we can run the Snorkel tutorials by creating a new data science project. In the left-handed menu, navigate to the "**Data Science Projects**" tab. <br />

<img width="805" alt="Screenshot 2024-01-29 at 5 14 24 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/dba1ce44-98b3-4d5a-99c2-6c117cab9899"> <br />

Next, click "**Create data science project**". Type your preferred project names; in our case `snorkel` and press "**Create**". This is the namespace where all the resources tailored to this demo will be deployed. <br />

<img width="1042" alt="Screenshot 2024-01-29 at 5 14 55 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/e6f607b0-8324-4cb1-b506-672fd89f5855"> <br />

## Create Workbench
Inside our project select "**Create workbench**". This will guide us to the workbench configuration page. Complete the fields to match the following:
- **Name**: *`snorkel`* (insert any preferred name).
- **Image selection**: *`PyTorch`*
- **Version selection**: *`2023.1`*
- **Container size**: *`Small`* 
- [X] Check the "**Create new persistent storage**" box.
  -   **Name**: *`snorkel`* (insert any preferred name)
  -   **Persistent storage size**: *`20 GiB`*
     
Once completed the form, please click on "**Create workbench**". You should be taken to the project home page. Once the workbench is has finished provisioning, click **"Open"** to access the workbench. Log-in with your OpenShift credentials and allow the selected permissions. <br />

<img width="1369" alt="Screenshot 2024-01-29 at 5 32 44 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/0a92b4f3-800c-46db-99e1-b6814f80c312"> <br />

## Snorkel.ai tutorials
Now that we're in our Jupyter environment, let's clone the Snorkel.ai repository. On the left, select the git logo and click **"Clone a repository"** and paste the repository URL: [https://github.com/snorkel-team/snorkel-tutorials.git](https://github.com/snorkel-team/snorkel-tutorials.git).<br />

<img width="427" alt="Screenshot 2024-01-29 at 5 44 39 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/bc6ccb68-1ae2-4bb6-a7d9-a6ac35c54c29"> <br />

<img width="537" alt="Screenshot 2024-01-29 at 5 45 33 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/8e5664ef-df82-442c-a6ab-ae5ae2cb808b"> <br />


Now that we've cloned the repository, we're going to try out the *spam* and *spouse* tutorials (tutorials can be found in the directories with the corresponding name). The *spam* tutorial is a data labeling exercise that shows you how to build a training set for classifying YouTube comments as spam or not spam. Its an introductory tutorial and it is one avenue you could perform data labeling within RHOAI utilizing Snorkel. The *spouse* tutorial is a little more complex, it walks through how to utilize Snorkel for information extraction by using keywords and distant supervision. In this tutorial, you will learn how to we can identify and classify someone's spouce utilizing labeling functions and models to do so. This exercise is to demostrate how simple it is to integrate Snorkel's libraries and tools with your RHOAI environment. 


