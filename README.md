                                          Connecting public API to snowflake
                                         
**To connect to any API from snowflake we need to create aa network rule and External access Integration.**

**STEP 1:** CREATE A NETWORK RULE USING INFRA ROLE

CREATE OR REPLACE NETWORK RULE MS_NETWORK_RULE

MODE = EGRESS

TYPE = HOST_PORT

VALUE_LIST = ('www.microsoft.com');      **-- Please change the url according to the requirement**
  
**STEP 2:** CREATE A EXTERNAL ACCESS INTEGRATION USING INFRA ROLE

CREATE OR REPLACE EXTERNAL ACCESS INTEGRATION MS_ACCESS_INTEGRATION

  ALLOWED_NETWORK_RULES = (MS_NETWORK_RULE)
  
  ENABLED = true;
  
**We can load the data into a internal stage and to a table directly from API. For both types we will see the code below.**

**STEP 3:** CREATE A STORED PROCEDURE TO CONNECT TO API AND LOAD THE DATA INTO INTERNAL STAGE

![image](https://github.com/user-attachments/assets/2f4bc509-439a-4c6e-a789-b5aff3a4bf87)

Before creating the store proc, create one internal stage in a DEV environment and schema you want to work on and give that stage name in the code for lines 41 and 46.

![image](https://github.com/user-attachments/assets/db9cdafb-c74d-4d79-aa06-bedff7ddb7f6)

**Note:** You can create the internal stage using the code below also

  CREATE STAGE sample_stage_112024 
	DIRECTORY = ( ENABLE = true );

And give the file name in the line 40 accordingly.

Now you can create the store proc and call the store proc.

**CALL SAVE_TODOS_01()**

Once you call the store proc it fetch the data from the url and write the data in internal stage as .json file format.

![image](https://github.com/user-attachments/assets/c3f7dedb-dea4-4c97-a596-d35da9e1fe6d)

You can download the file and check the data and also you can list the files using list function from stage in snowflake.

**Ex:** list @SAMPLE_STAGE_112024;

Now, we will see how to fetch the data directly into the table.

**CREATE A STORED PROCEDURE TO CONNECT TO API AND LOAD THE DATA INTO TABLE**

![image](https://github.com/user-attachments/assets/aaaa2e27-b40e-4ff2-aafc-7ced011d9dd5)

Change the table name accordingly in line 30 and create a store proc by running the above code. Call the store proc 

**CALL SAVE_TODOS_08()**

Once you call the store proc it will fetch the data from the url into table.

![image](https://github.com/user-attachments/assets/1ce26610-3eb0-4e79-8820-c839be511b5c)





