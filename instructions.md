# Red Hat OpenShift AI (RHOAI) Environment
Red Hat OpenShift AI (RHOAI) combines the scalability and flexibility of containerization with the capabilities of machine learning and data analytics. With Red Hat OpenShift AI, data scientists and developers can efficiently collaborate, deploy, and manage their models and applications in a secure and streamlined environment.

## RHODS installation
RHOAI can be installed from the OpenShift Web Console. Navigate back to the "**Operators**" tab and select "**OperatorHub**". In the text box now type `RHODS` and select the "**Red Hat OpenShift Data Science**" operator and click on "**Install**". 



To start the installation press again the blue "**Install**" button. Once the status is `Succeeded`, click on the operator and create a new "**Data Science Cluster**" instance. Once this has successfully deployed, we'll go to access our RHOAI Dashboard. On the administrator menu, head to "**Networking**" and click on "**Routes**". In Routes, we're going to change the project to "**redhat-ods-application**" and click on the address to take you to the RHOAI Dashboard. 

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


