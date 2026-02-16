# Create a UI Application

The next step is to add a UI application to create and edit BTP notifications, and to list existing ones. 

For this, a new SAP Fiori Elements application with a List Report and Object Page floor plan will be created. This template-based app-creation approach fits well with this requirement and provides rich, standard functionality out of the box while adhering to the latest SAP Fiori-based UX.

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
