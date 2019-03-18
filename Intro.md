# Data Migration with Autonomous Data Warehouse Cloud Service

Welcome to the Data Migration Workshop. This workshop will walk you through the process of configuring Data Pump with Autonomous Data Warehouse Cloud service in Linux Compute Instance... 

## Objectives
- Create Autonomous Data Warehouse Cloud Service (ADWC) instance.
- Create compute instance.
- Configure Linux Environment for Datapump.
- Use impdp to import tables from ADWC into .dmp file.
- Create Object Storage.
- Push .dmp file from data_pump_dir to object storage using dbms_cloud package.
- Import into the ADWC environment from object storage.
- Audit the export done on the table using Unified Auditing.

## Required Artifacts
- The following lab requires an Oracle Public Cloud account with Autonomous Data Warehouse Cloud Service.
- A public and a private ssh keys.
- SFTP Software to transfer files to compute instance - Windows Users. I have used Filezilla.

### **Step 1**: Acquire an Oracle Cloud Trial or Workshop Account

- Bookmark this page for future reference.

- Please click on the following link to create your <a class="trial-link" href="https://bit.ly/2yvpjSH" target="_trial">Free Account</a>, and complete all the required steps to get your free Oracle Cloud Trial Account. When you complete the registration process you'll receive a $300 credit that will enable you to complete the lab for free.  Additionally, you'll have 1000s of hours left over to continue to explore the Oracle Cloud.

  - Soon after requesting your trial you will receive the following email. _You may begin working on Lab 100 before you receive this email_, but you will not be able to start Lab 200 until you have received it.

  ![](images/oraclecode/code_9.png)


### **Step 2**: Navigate to Lab 100

- _You can see a list of Lab Guides_ by clicking on the **Menu Icon** in the upper left corner of the browser window. 
   You're now ready to continue with **Lab 100**.


