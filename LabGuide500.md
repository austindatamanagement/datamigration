Updated: December 10, 2018

## Introduction

This lab guide will walk you through the process of exporting tables from ADWC through Datapump.

**_To log issues_**, click here to go to the [github oracle](https://github.com/oracle/learning-library/issues/new) repository issue submission form.

## Objectives

- Export a table using expdp, Datapump.

### **STEP 1**: Export a table using expdp, Datapump to datapump_dir.

- Make sure that you are in **/home/opc/oracle/instantclient_18_3**. 

  Note: You can also export schema by mentioning it as a parameter in expdp command. Check the documentation for more details. 
        [Documentation](https://docs.oracle.com/en/cloud/paas/autonomous-data-warehouse-cloud/user/load-data.html#GUID-30DB1EEA-DB45-49EA-9E97-DF49A9968E24)

- Copy paste the command below, but before that, change the following parameter. 

    - **service_name** : `Name of the service, for this demo we are using yourinstancename_high service. Please recheck the service name from sqldeveloper`

    **expdp admin@service_name tables=CHANNELS dumpfile=DataPumpDemo.dmp**
  
  You can also give object storage location for dump file. 

    ![](images/datapump/compute43.png)
    

### **STEP 2**: Move the Datapump file from DATA_PUMP_DIR to Object Storage:

- Login to sqldeveloper. Change following parameters in the command below:
    
    **credential_name** : `Make sure that you change credential name to your own credential that was created in Lab200, step 2.`
    
    **object_uri** : `Swift URL of your object storage followed by the file name that you want it to be stored.
                      Create the swift URL as follows: https://swiftobjectstorage.**your_region**.oraclecloud.com/v1/**tenancy_name**/**Bucket_Name**/DataPumpDemo.dmp
                      Change the following parameters:
                      your_region : e.g. ca-toronto-1, eu-frankfurt-1, uk-london-1, us-ashburn-1, us-gov-ashburn-1, us-gov-chicago-1, us-gov-phoenix-1, us-langley-1, us-luke-1, us-phoenix-1
                      tenancy_name: Your tenancy name
                      bucket_name: The name of the bucket in which you have stored the dmp file`
    
    **file_name** : `Name of the dump file in data pump directory`
    
    Type the following command :
    
    **BEGIN
    DBMS_CLOUD.PUT_OBJECT(
    credential_name => 'DEF_CRED_NAME',
    object_uri => 'https://swiftobjectstorage.us-ashburn-1.oraclecloud.com/v1/gse000###/DemoBucket/DataPumpDemo.dmp',
    directory_name  => 'DATA_PUMP_DIR',
    file_name => 'DataPumpDemo.dmp');
    END;
    /**

    This will move the .dmp file to object storage. you can also import from Object Storage.



