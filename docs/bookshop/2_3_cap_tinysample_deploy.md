# Deploy your Tiny-Sample App to Cloud Foundry
        

### Deploy to Cloud Foundry

1. Right-click on file `mta.yaml` and select "*Build MTA Project*". 

    Alternatively use terminal:

    ```
    mbt build
    ```

2. Login to Cloud Foundry. Open Command Palette (`CTRL + Shift + P`) and search for "CF: Login to Cloud Foundry" and select it.


3. Important: Make sure you use the correct **API Endpoint** from your CF Subaccount. You find it in the Overview page of your Subaccount.

   ![Login Cloud Foundry](images/0_cf_login_1.png)

4. Enter username (email) and password or SSO Passcode.

5. Choose your Subaccount and CF Space (for example "dev"), where you have SAP HANA Cloud installed. 
  
    Tip: If you skip the CF login, just run "CF: Login" again.

6. Choose **Apply**. 

7. Right-click on file `mta_archives/tinybookshop_1.0.0.mtar` and select "*Deploy MTA Archive*". 

    Alternatively use terminal:

    ```
    cf deploy mta_archives/tinybookshop_1.0.0.mtar
    ```

    ![](images/tinysample/2_tiny_deploy_1.png)


8. Go to your Cloud Foundry Subaccount. Check that deployment was successful.

    Open your Subaccount and your Cloud Foundry **Space**, where you deployed your application to.

    Under Applications, you see 2 new entries. Don't start the bookshop-db-deployer. Its sole purpose is to deploy the bookshop schema with an HDI-Container.

    ![](images/tinysample/2_tiny_deploy_2_newapps.png)

    You can open the service `tinybookshop-srv`. But it requires now authentication, which you can't provide in a plain browser.

    
9.  In your Subaccount Space, navigate to "Services" --> "Instances". You see 4 new entries.

     ![](images/tinysample/2_tiny_deploy_3_instances.png)



10. In your Subaccount, navigate to "HTML5 Applications" in the left navigation pane.
  
     HTML5 Applications will only be available if you subscribed to SAP Build Work Zone. 

     Click on your app `mytinybooksui``:
 
     ![](images/tinysample/2_tiny_deploy_4_managedapp.png)

11. The app should look the same as in your dev environment. 

     Note: It now consumes 1 unit of your Cloud Foundry Quota.

     ![New Fiori app](images/tinysample/2_tiny_dev_11_newfiori_draft.png)


Congratulations! You have just deployed your first CAP app with an SAP Fiori UI!

