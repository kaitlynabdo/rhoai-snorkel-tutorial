# Red Hat OpenShift AI (RHOAI) Environment
Red Hat OpenShift AI (RHOAI) combines the scalability and flexibility of containerization with the capabilities of machine learning and data analytics. With Red Hat OpenShift AI, data scientists and developers can efficiently collaborate, deploy, and manage their models and applications in a secure and streamlined environment.

## RHODS installation
RHOAI can be installed from the OpenShift Web Console. Navigate back to the "**Operators**" tab and select "**OperatorHub**". In the text box now type `RHODS` and select the "**Red Hat OpenShift Data Science**" operator and click on "**Install**". 

<img width="940" alt="Screenshot 2024-01-29 at 3 50 28 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/7b9dd95e-e24c-404f-8ecb-6aa51520acdd">

To start the installation press again the blue "**Install**" button. We can check to see if our operator successfully deployed under the "**Operators**" tab and select "**Installed Operators**". 

<img width="1682" alt="Screenshot 2024-01-29 at 4 53 52 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/fc7f5f47-5618-421b-aa3a-1a90a02e4353">

Now that our operator has successfully deployed, click on it and create a new "**Data Science Cluster**" instance. We don't need to make any changes to the default settings, so we'll just click "**Create**".

<img width="719" alt="Screenshot 2024-01-29 at 4 55 57 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/76cf9ba8-8099-4a97-93fc-f2f989f5acf0">

<img width="1127" alt="Screenshot 2024-01-29 at 4 56 30 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/3ade76b6-fbfa-463e-a357-4aa5a4f30787">

Once this has successfully deployed, we'll go to access our RHOAI Dashboard. On the administrator menu, head to "**Networking**" and click on "**Routes**". In Routes, we're going to change the project to "**redhat-ods-application**", which is where we can access the address to our RHOAI application.

<img width="804" alt="Screenshot 2024-01-29 at 3 53 28 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/4dfe1c64-7980-40f3-989b-7a201352ca29">

There should only be one route available, so go ahead and click the address to take you to the RHOAI dashboard. 

<img width="1684" alt="Screenshot 2024-01-29 at 3 53 17 PM" src="https://github.com/kaitlynabdo/rhoai-snorkel-tutorial/assets/45447032/17dde84f-acb4-4bc1-813d-3c32f1f48d25">


## Create Data Science Project
A new window will open. Log in again using your OpenShift credentials (kubeadmin or your identity provider user).

## Project set up
Once we are logged, in the landing page we will see a layout similar to the one we have in the OpenShift Web Console. In the left-handed menu, navigate to the "**Data Science Projects**" tab. Next, click "**Create data science project**". Type your preferred project names; in our case `pokedex` and press "**Create**". This is the namespace where all the resources tailored to this demo will be deployed.

## Create Workbench
Inside our project select "**Create workbench**". This will guide us to the workbench configuration page. Complete the fields to match the following:
- **Name**: *`snorkel`* (insert any preferred name).
- **Image selection**: *`PyTorch`*
- **Version selection**: *`2023.1`*
- **Container size**: *`Small`* 
- **Number of GPUs**: *`0`* (you can add an accelerator if you would like, and it will autopopulate here)
- [X] Check the "**Create new persistent storage**" box.
  -   **Name**: *`snorkel`* (insert any preferred name).
  -   **Persistent storage size**: *`20 GiB`* (we can always extend it later if needed).
     
Once completed the form, please click on "**Create workbench**". You should have something similar to this image:


