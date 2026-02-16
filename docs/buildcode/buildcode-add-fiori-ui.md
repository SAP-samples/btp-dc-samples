# Create a UI Application

The next step is to add a UI application to create and edit BTP notifications, and to list existing ones. 

SAP Build Code will use the **SAP Fiori Elements** UI applications. AP Fiori Elements offers a template-based app-creation approach and provides rich functionality out of the box while adhering to the latest SAP Fiori-based UX standards.

#### Procedure

1. On the Storyboard, go to the UI Applications section.
2. Click the + button to create a new UI application

   image

   
3. Provide the UI Application Details
  
   - Display and Application name: Enter "Notifications".
     
   - Description: Provide a Description of your choice.
     
   - Data Source: Select the Drop Down List Box and select your service maintenanceAppSrv

   image

4. Click next to go to the UI Application Template.

   Select Template-based, Responsive Application and click "Next".

   image

5. Select "List Report Page" and click "Next".

    This SAP Fiori app is intended mainly for desktop use, but it also works on mobile devices. If the main use case is on the mobile phone, consider creating a dedicated mobile project app with SAP Build.

   image

6. As Data Objects select:
   
   - Main Entity: MaintenanceNotifications
   - Generate Annotations: Yes
  
   Click "Finish".
  
   image


7. The UI generation takes a couple of seconds, and the UI application will be added to the storyboard.
   After creation, the Page Map opens. You  see two pages: A List Report and an Object Page, and their properties.

   image.


### Adjust the UI Application

The record number will be created by the backend and retrieved by the CAP Service. 

The user must add the number manually in an input field of the new UI application.

Therefore, a modification to make the Record Number field read-only is required.

1. Select the Object Page and click on the pencil icon to configure the page

    image
   
2. Expand "Sections" --> "General Information" --> "Form" --> "Fields".
   
   Click on "Record Number". In the side menu, search for the Annotation "Restrictions".

   Select **Read Only**.

   image.




