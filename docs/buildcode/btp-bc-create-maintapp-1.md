# Create a Maintenance Notifications App with SAP Build Code

Part 1, create the initial application.

### Create a Full-Stack Application Project from the Lobby

1. From your Subaccount open Services --> Instances and Subscription and start "SAP Build Code" (in this picture you see a trial account, which uses a "free" SAP Build Code Service Plan).

   ![](images_lobby/030_lobby_start_build_code.png)

2. You enter the SAP Build Lobby. Choose "Create" in your Project overview list.

    ![](images_lobby/031_lobby_Build_lobby_create.png)

3. Choose "Application".

    ![](images_lobby/032_lobby_1_project_create_app.png)

4. Choose "Full-Stack".

    ![](images_lobby/033_lobby_2_app.png)

5. Choose "Full-Stack Node.JS".

    ![](images_lobby/034_lobby_3_fullstack.png)

6. Provide Name, e.g. "MaintenanceApp". Keep the Full_Stack Dev Space.

    Choose "Review" and create the project.

    ![](images_lobby/035_lobby_4_name.png)

7. The Project MaintenanceApp will be created, this takes a minute.

    ![](images_lobby/036_lobby_pending_creation.png)

8. Once the project has been created, click on it and enter the Business Application Studio (BAS).

    ![](images_lobby/037_lobby_enter_project.png)

### Create the Mainatenance Notification App

1. In the Studio, click the Joule icon and open the Joule Code Assistant.

    ![](images_lobby/038_bas_open_joule.png)

2. Check available syntax and commands in Joule Code Assistant.

    ![](images_lobby/039_bas_joule.png)

3. Enter this command in Joule using natural language and run it:

    ```/cap-gen-app Create a maintenance notification app which contains a problem description and a number of the record, both should be strings.```

    
    ![](images_lobby/040_bas_command.png)

4. Joule Code Assistand will generate an inital app.

    Review the code and "accept" it.

    ![](images_lobby/041_bas_joule_accept.png)

5. Once accepted, the generated code block will be applied to the project.

    ![](images_lobby/042_bas_joule_result.png)


### Optional: Test your new basic application

Also the project does not yet has a data source and a UI, you can already test it.

1. Start the project either from "Run Configurations" on the left panel or from the small icon on the top right. It will take some seconds to start it.

    ![](images_lobby/044_bas_run_test.png)

2. Once started, a new browser window opens. You can check service details and metadata. Click the "view in table" icon in "Services".

    ![](images_lobby/045_bas_test_view_as_table.png)

3. A test UI opens. Click "Go" to load data. You will not have any so far. 

    Choose "Create" to create a new maintenance notification.

    ![](images_lobby/046_bas_test_go.png)

4. Give the notification a problem description. You can leave the record number empty for now. Choose "Create"

    ![](images_lobby/047_bas_test_create.png)

5. Go back to the List View and see the new data set.

   You have now an idea how the application works.

    ![](images_lobby/048_bas_test_result.png)

6. Once done, stop and disconnect the application by clicking on the red square button.

    ![](images_lobby/049_bas_test_stop_disconnect.png)



