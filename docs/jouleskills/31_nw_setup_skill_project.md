# Create your first OData Joule Skill


In this example, you use the [Northwind V4 Service](https://services.odata.org/v4/northwind/northwind.svc/) as an OData service.

You can also use sandbox services from the [Business Accelerator Hub](https://api.sap.com/), publicly available S/4Hana Mock services from SAP, or, of course, your SAP backend systems (not described in this mission).

The Northwind service has a limited number of services, small data structures, and a small set of demo data, which makes it suitable for get-started missions. Please note that Joule Studio operates within SAP Process Automation and has limited quotas regarding request and response sizes.

### Create a destination in BTP Cockpit

A Joule Skill with an OData call requires a destination. Create one for your Northwind service.

1. In your BTP Cockpit with Enterprise Account, open the Subaccount where you subscribed to Joule Studio. 

2. Navigate to "Connectivity" --> "Destinations" and choose "Create". Choose to create "From Scratch".

    ![](images_northwind/jskill_setup_01_btp_dest_create.png)

2. Provide the following properties (WebIDEEnabled and other additional properties are optional for other use cases)

    ```Properties
    Name=Northwind_V4
    Type=HTTP
    Description=Northwind V4 Service
    Authentication=NoAuthentication
    ProxyType=Internet
    URL=https\://services.odata.org/v4/northwind/northwind.svc
    sap.applicationdevelopment.actions.enabled=true
    sap.applicationdevelopment.actions.enabled=true
    sap.build.usage=odata_gen
    WebIDEEnabled=true
    ```

    ![](images_northwind/jskill_setup_02_btp_dest_properties.png)


3. Optional: Select "Create From File". Save the properties as Nortwind_V4.properties and import the file.


4. Open your Build Lobby by clicking your SAP Build Process Subscription. Navigate to "Control Tower" --> "Destinations" and open the tile.

    ![](images_northwind/jskill_setup_03_ctower_1.png)

5. Click "Add", select your Northwind Destination, and select "Next"

    ![](images_northwind/jskill_setup_04_ctower_2.png)

6. Keep "All Environments" for now. You can restrict it later if you have more environments.

    ![](images_northwind/jskill_setup_05_ctower_3.png)

7. Go back to "Control Tower" --> "Environments". Choose "Create".

    Provide a Name (Testenv_Northwind) and description(Northwind Test Environment).

    This will be your Joule Instance for testing your skill.

    ![](images_northwind/jskill_setup_06_ctower_env.png)

8. Open your "Lobby" and create a project. Choose "Create".

    Choose "Joule Skill" and select "Next".

    Enter Project Name (TestNorthwindOrders) and Description(Test Joule Skills with Northwind OData services).

    ![](images_northwind/jskill_setup_07_project.png)

You are done with your setup. You can start creating a Jouel Skill.

### Create Actions for Northwind Service

You will call in your Joule skill OData services. In Joule Skills, you must first create these queries as "Actions".

1. Open "Connectors" --> "Actions" and choose "Create".

    ![alt text](images_skills/actions_01_create.png)
 
2. Choose "Live Api" and "OData Destinations".

    ![alt text](images_skills/actions_02_api_source.png) 

3. Select your Northwind destination, which you have already created.

    ![alt text](images_skills/actions_03_northwind.png) 

4. Name your Actions Project. E.g., "Service for Northwind V4". Choose "create".

    ![alt text](images_skills/actions_04_projectname.png) 

5. Enter the actions project. From the list of services, select "get entities from Customers".

     ![alt text](images_skills/actions_05_getcustomer.png) 

6. From the list of services, select also "get entities from related Orders" and "get entities from related Orders_Details".

    ![alt text](images_skills/actions_06_getorders.png) 

7. Select the action "Get entities from Customers". The service offers an input parameter "$search" as OData V4 foresees. 
    Unfortunately, it is not implemented in the Northwind service.
    So you create a small workaround to search for customers with a **$filter** query parameter.

    Add a new custom field. Call it "searchstring" of type string. Choose "Add" and do not forget to "Save".

    ![alt text](images_skills/actions_07_searchstring.png) 

9. Create a value for "$filter". Click on "Value" and scroll down the pop-up window to "Value". Click the "Condition Editor" icon.

    ![alt text](images_skills/actions_08_filter.png) 

10. Northwind does also not support "contains" or "substring" in $filter. So, create a condition that comes close to it. In the Condition Editor, create 2 conditions and connect them with "OR". 

    Select columns "Company Name" and "CustomerID", the condition "greater than or equal" (so you get more results and you don't need an exact match), and the criteria in your input field "serachstring".

    Click "OK".

    ![alt text](images_skills/actions_09_conditions.png)

11. Conditions are applied. Click "Save".

     ![alt text](images_skills/actions_10_conditions2.png) 

12. Test it. Provide "searchstring" "ALFKI" or "Alfred" or sth. else. Check the result. It works. With this filter, you will not get precise results, but it is sufficient for Joule, which will automatically filter out mismatches.

     ![alt text](images_skills/actions_11_test.png) 

13. Select service "Get entities from related Order_Details". Add the additional field "$expand. The $expand system query option specifies the related resources to be included in line with retrieved resources.

     ![alt text](images_skills/actions_12_expand.png) 

14. Click into the field "Value". In the pop-up window, select "**Product**". This will expand the list "Product" in line with "Order Details".

     ![alt text](images_skills/actions_13_expandproduct.png) 

15. Joule Skills can only show in line entities that are "flattened". Navigate to "Output", open "value", and activate the "Flattened" icon for "Product".

     ![alt text](images_skills/actions_14_productflattened.png) 

16. Test it. For example, with Order ID "10643". You can see the flattened result for the Product Details. 

     ![alt text](images_skills/actions_15_testorder.png) 

14. Release your Skill and provide some release description (optional).

     ![alt text](images_skills/actions_16_release.png) 

15. Switch the Actions View to the "Released" version and click "Publish". The Action can now be consumed from a Joule Skill.

     ![alt text](images_skills/actions_17_publish.png) 


### Create a Joule Skill

1. Navigate to "Lobby" and open your project, which you have already created. Select "Create" --> "Joule Skill".

    ![alt text](images_skills/jskill_01_createskill.png) 

2. Name it, e.g., "Get Food Customers".

    The Description is now important. It will be used by Joule Skills when to use this specific Skill for a specific question in the Joule environment.

    Provide, for example: "Get Food Customers and show all Customer information, including CustomerID".

    Select "Create".

    (Note: The description does not influence the response from Joule.)

    ![alt text](images_skills/jskill_02_create2.png) 

3. The Editor for the Joule Skill "Get Food Customers" opens.

    Select the "Trigger" step and then the "General" tab.

    Note, that you "Allow Joule to generate a response". Means Joule will generate a response UI, based on the Output Parameters you will define.

    You can also switch it off, but then you have to create your individual "response message" (this is not part of this tutorial).

    ![alt text](images_skills/jskill_03_general.png) 

4. Select the "Trigger" step and then the "Parameters" tab. Remember, you added the option to provide a "searchstring", so map searchstring as an Input Parameter.

    Select "Configure" Skill Inputs.

    ![alt text](images_skills/jskill_03_parameter.png) 

5. Provide a Skill Input. E.g. "searchterm". It is not "required" for the service, just optional.

    ![alt text](images_skills/jskill_04_inputpara.png) 

6. Select "Skill Outputs" --> "Configure". 

    As you have decided to let Joule generate the response, Joule needs to know whether it should provide a response and how to structure it. Create a data structure for it.

    For the response, create a "Customer List" of type "any", "Required", and "List". You want to have it in the response.

    Create an Output "Customer ID", type "any", "Required". You always want to see the Customer ID in the response. Joule should not decide.

    ![alt text](images_skills/jskill_05_outputpara.png) 

7. Click on the **+** icon after "Trigger". Next, you want to call the cation you created. Click "Call Action".

    ![alt text](images_skills/jskill_06_addcallaction.png) 

8. Add "Get entities from Customers".

    ![alt text](images_skills/jskill_07_addcustomers.png) 

9. Create a destination variable. It's just a placeholder for later mapping to the physical destination. Select it again after you created it.

    ![alt text](images_skills/jskill_08_createdestvar.png) 

10. Go to "Inputs" and map the Input Parameter "searchterm" you just created.

    You may also inspect the "Outputs", which will be generated from the service.

    ![alt text](images_skills/jskill_09_inputparamapping.png) 

11. Go to "End". Map your "Skill Outputs". For the Output "Customer List" map "list-value" from the action result set. 

     ![alt text](images_skills/jskill_10_outputparamapping.png) 

12. Map "CustomerID" to "Customer ID" in order to instruct Joule to always show it.

     ![alt text](images_skills/jskill_11_outparamapping2.png) 

13. "Save" your Joule Skill and "Release". 

     ![alt text](images_skills/jskill_12_release.png) 

14. Switch to the release version (which you cannot edit anymore) and "Deploy" it.

     ![alt text](images_skills/jskill_13_deploy.png) 

15. Choose your "Northwind Test Environment" and Environment.   

     ![alt text](images_skills/jskill_14_deploy2.png) 

16. Map your project destination variable to your physical destination.

     ![alt text](images_skills/jskill_15_deploymapdest.png) 

17. The result should be a deployed Joule Skill.

     ![alt text](images_skills/jskill_16_deployresult.png) 

### Test your Joule Skill in a Standalone Environment

1. Go to "Control Tower" --> "Environments" and click your Test Environment.

    ![alt text](images_skills/jskill_17_testenv.png) 

2. Select the tab "Joule" and "Launch" your Joule Standalone Environment.

    ![alt text](images_skills/jskill_18_testenvlaunch.png) 

3. Joule opens. Note the small icon in the top right opens the "Request Logs".

   ![alt text](images_skills/jskill_23_test_emptyjoule.png)

4. Make your first chat: "Show me 5 customers".

   ![alt text](images_skills/jskill_19_test_customers1.png) 

4. Test the search filter: "Show me customer ALFKI".

    ![alt text](images_skills/jskill_20_test_customers2.png) 

5. You see, Joule decided not to show the phone number. You can also tell Joule to show it. But it may drop other not "required" values.

   ![alt text](images_skills/jskill_21_test_customers3.png) 

6. You can determine the behavior of Joule, which outputs to generate. 

   You can add additional Output Parameters, which Joule should always generate and map them to the result set of the action service.

   Or you can switch off "Allow Joule to generate a response". You will then need to create a response message yourself in an additional "Send Response" step (creating a "Send Response" step is not covered in this tutorial).

   ![alt text](images_skills/jskill_22_switchoffautomaticresponse.png) 

Congrats. You just ran your first Joule Skill.


