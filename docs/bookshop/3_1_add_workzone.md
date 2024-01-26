# Add your Fiori App to SAP Build Work Zone



## Prerequisites

Make sure you have finished the previous tutorial.






### Add FLP Configuration to your Project

1. Open your Business Application Studio (BAS), your Dev Space and your project "tinybookshop".

2. Check if you have created an FLP configuration. 
   
    Open in project explorer the file tinybookshop --> app --> tinybooksui --> webapp --> manifest.json. Search for `crossNavigation``.

    ![](images/flp/3_flp_1_manifest.png)

3. If you have no FLP configuration, add one. Open View --> Command Palette (Ctrl + Shift + P) and type "Fiori: Add Fiori Launchpad Configuration".

    The Fiori Launchpad Configuration Generator opens. Provide the following parameters:

    - Semantic Object: semanticobjecttinybooks
    - Action: show
    - Title: showtinyBooks (for example)

4. Check the value of sap.cloud in your manifest.json. 

   In case you named your managed approuter for exmplae "tinysamplerouter", it should be:

    ```bash
    "sap.cloud": {
      "public": true,
      "service": "tinysamplerouter"
    }
    ```

5. Build and deploy your application if it has changed.


### Integrate your HelloWorld app into SAP Build Work Zone

1. Open your Subaccount in your SAP BTP Cockpit.

2. Navigate to Services --> Instances and Subscriptions in the left navigation pane.

3. Select in Subscriptions "SAP Build Work Zone, standard edition".

    ![](images/flp/3_flp_2_launchflp.png)

    The Launchpad Site Manager opens in a new window.

    Note: If you get the error message "Access Denied", your user has not been assigned the role collection Launchpad_Admin. Go to Security --> Users, click on your user and assign the Launchpad_Admin role collection to your user.

4. Create a new Site. Name it for example "Tiny Books"

    ![](images/flp/3_flp_3_createsite.png)


5. Open the Channel Manager. 

    Refresh the Content Channel. Otherwise it will stay empty.

    ![](images/flp/3_flp_4_channelrefresh.png)

6. Open Content Manager, and the Content Explorer.

    ![](images/flp/3_flp_5_content_1.png)

7. In Content Explorer, enter the Channel "HTML5 Apps".

    ![](images/flp/3_flp_5_content_2.png)


8. In Content Explorer, add your Fiori UI to the Site Content Manager.

    ![](images/flp/3_flp_5_content_3.png)


9. Go back to Content Manager and create a "Group".

    ![](images/flp/3_flp_6_group_1.png)

10. Name it for example "tinyGroup" and assign your Fiori app to the group.

     Click "Save".

     ![](images/flp/3_flp_6_group_2.png)

11. Go back to Content Manager and repeat the same for the Role "Everyone".

     ![](images/flp/3_flp_7_role.png)

12. This should be the result:

     ![](images/flp/3_flp_8_result.png)

13. Go Site Directory and enter your site "Tiny Books" by clicking on the small "Go To Site"-icon.

     ![](images/flp/3_flp_9_entersite_1.png)

14. Click on your "showtinyBooks" tile.

     ![](images/flp/3_flp_9_entersite_2.png)

15. You tiny Books app will open:

     ![](images/flp/3_flp_10_app.png)
