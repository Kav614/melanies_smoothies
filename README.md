                                Setting Up DataGrip for Snowflake

This guide provides step-by-step instructions to configure DataGrip to connect to a Snowflake environment.
 
Prerequisites:
- DataGrip installed on your system.
- Snowflake account and user credentials.
 
Setting up DataGrip for Snowflake:
1.	Install DataGrip
2.	Install Necessary Plugins:
     •	Open DataGrip
     •	Go to Plugins.
     •	Install the following plugins if not already available:
            Azure Devops
  	![image](https://github.com/user-attachments/assets/f4e5ac75-5590-420c-b6d3-daeb79188640)
     •	Restart DataGrip if prompted.
3.  Create a new sample project first to get into Data Grip 
    ![image](https://github.com/user-attachments/assets/872d1870-7662-4ceb-81c4-113f26301088)
4.  Next Clone the Repository in Visual Studio 2022
     If you haven’t already cloned your repository, start by cloning it to your local system:
     •	Git link:  https://dev.azure.com/biclarionhg/Data%20Engineering%20Kanban/_git/SnowflakeDatabases 
     •	Path: C:\Source\Snowflake\SnowflakeDatabases
    ![image](https://github.com/user-attachments/assets/f949ad0f-e28e-4c32-ad2f-846c2cf539de)
    After that open DataGrip and The project will display over there.
5. Open DataGrip and Connect to Snowflake:
     •	Open Database Explorer in DataGrip.
     •	Click on +(Add) > Data Source > Snowflake.
   ![image](https://github.com/user-attachments/assets/336d6b4f-a810-4f62-a4cd-931810546b63)
     •	Configure the Connection
          o	Username and Password: Enter your Snowflake credentials.
          o	Warehouse: Specify the warehouse you want to connect to (eg. ‘COMPUTE_WH’).
          o	Database: Enter the default database (eg. ‘TEST_DB’).
          o	Host: OK21198.UK-SOUTH.AZURE.SNOWFLAKECOMPUTING.COM
          o	Role: SNOWFLAKE_RBAC_AS_DA_DATAENGINEER_DEV
          o	Schema: Specify the schema (eg. ‘PUBLIC’).
   ![image](https://github.com/user-attachments/assets/92c42e61-1889-4d6d-9b92-c5c8027ac606)
    •	Click Test Connection to verify that DataGrip can connect to Snowflake. If the connection succeeds, you’ll see a confirmation.
6. Save the Configuration  
    •	Once the connection test is successful, click OK to save the configuration.
7. Once again open the snowflake connection and select the schemas
   ![image](https://github.com/user-attachments/assets/2f1bce4e-facf-42eb-9fc1-76090ebc4d0e)
8. Troubleshooting
    •	Connection Timeouts: Check your network and Snowflake permissions.
    •	Invalid Credentials: Double-check your account identifier, username, and password.

                      Working with Feature Branches in Git for Snowflake Development
 This guide explains how to create and manage a feature branch in Git for Snowflake project.

1. Create a New Feature Branch in DataGrip
   •	Open the Git tab in DataGrip.
   •	Select Branch > New Branch
   ![image](https://github.com/user-attachments/assets/0f3d29a4-ec6e-433a-8427-9240a6544bf7)
   •	Naming convention: ‘feature/<feature-name>’
   
   ![image](https://github.com/user-attachments/assets/bb87a66e-638d-4678-b813-04bc6c0a9fae)
   
   •	Ensure you are now on your new branch
   ![image](https://github.com/user-attachments/assets/f97437c4-2d1c-4882-a193-eac27a8c1012)
2. Make Changes on the Feature Branch 
   •	Implement Changes related to the feature or ticket.
   ![image](https://github.com/user-attachments/assets/ed62c10a-c3b9-4eb7-abee-fb4c44f0cb9b)
   •	Regularly commit and push your changes to your branch:
        o	Select the files and Commit
   ![image](https://github.com/user-attachments/assets/d950a041-c66e-4cf9-8d34-edcc5ed36704)

                              Merging Feature Branch to Main Branch
   
1. Create a Pull Request (PR)
   •	Go to your repository on Azure Devops.
   •	Locate the new feature branch and create a pull request to merge it into the ‘main/master’ or ‘development’ branch.
   •	Add reviewers if needed.
2. Merge the Pull Request
   •	After review and approval, merge the PR into the target branch. You can delete the feature branch once it’s merged. 

                                Monitoring the Release Process

Key Components of Release Monitoring
1. Tracking Deployment Steps  
   •	Monitor each step of the deployment pipeline to ensure every process is executed as expected.
   ![image](https://github.com/user-attachments/assets/5cb58787-eb5f-40b7-87b9-087d3fb036da)
   There are 3 steps to the pipeline
   •	First after it is released to UAT. Confirm that the release meets expected quality standards and performs as intended in UAT.
   •	Get approval for the production release.
   •	Confirm that the release meets expected quality standards and performs as intended in production.
2. Error Logging and Alerting  
   •	If any error occurs, check the error and change it accordingly


   












     

