# Set up Joule Studio

Joule Studio is a capability in SAP Build that allows organizations to create and deploy custom Joule agents and skills that automate workflows and improve efficiency across SAP and non-SAP systems.

### Prerequisites

You have subscribed to SAP Build Process Automation using the build_default service plan.

You are entitled to Joule with the service plan "foundation" (or, in some cases, "standard").

You have established trust between Joule and the SAP Cloud Identity Services identity authentication tenant.


### Check your Global Account System Landscape

In order to run the Joule Booster successfully, your SAP Cloud Identity Services must be known to your System Landscape.

1. Open Global Account and navigate to "System Landscape" --> "Systems".

    In this case, the Booster for SAP Build Process Automation has already created a System entry.

    ![](images/05_setupjoule_system_01_systems.png)

2. Your Cloud Identity Services are also part of a formation.

    ![](images/05_setupjoule_system_02_formations.png)

3. Optional: If missing, add your Cloud Identity Services tenant manually.

    Switch to "Service Owner View" and click "Add System". 

    You need to know your CLD Tenant ID from your installation. It typically has around 9 digits.

    ![](images/05_setupjoule_system_03_addmanually.png)


### Setup Joule with Booster 

1. Check your entitlement for Joule

2. Open your Global Account, navigate to Boosters. Search for "Joule". Start the Booster "Setting up Joule".

    ![](images/05_setupjoule_booster_00_.png)

3. Step 1: The Prerequisites check must be green. If not solve the error messages of the prerequisites check.

    ![](images/05_setupjoule_booster_01_prer.png)

4. Step 2: Set up Subaccount

    Select the Service Plan "foundation" (or standard, depending on your license model)

    ![](images/05_setupjoule_booster_02_plan.png)

5. Step 3: Integrations

    Select Products from your System Landscape that you want to integrate into SAP Joule. In your case, SAP Build Work Zone (this is for this mission, optional).

    Choose "Testing" for this mission.

    ![](images/05_setupjoule_booster_03_select.png)

6. Step 4: Capabilities

    Select both. 

    ![](images/05_setupjoule_booster_04_capa.png)

7. Step 5: Set up Integrations

    ![](images/05_setupjoule_booster_05_setupi.png)

8. Review and Start Booster.

    This will take some minutes.

    ![](images/05_setupjoule_booster_06_review.png)

    Your booster should end successfully.

    ![](images/05_setupjoule_booster_07_success.png)

9. Go to your Subaccount --> "Instances and Subscription".

    Open your new Subscription "Joule" by clicking on it.
  
    ![](images/05_setupjoule_booster_08_runjoule.png)

    You probably need to authenticate with your Custom IAS user.

    You should see the message: "The service is up and running".


### Important: Assign required Roles and Role Collections

The Joule Booster does not create a Role Collection for your user. You have to do this manually.

1. Open your Subaccount, navigate to "Security" --> "Role Collections"

2. Choose "Create" Role Collection. Name it, for example, "Joule_Role_Collection".

3. Click on Joule Role Collection and click "Edit".

    Add the two following Roles: "extensibility_developer" and "end_user".

    ![](images/05_setupjoule_booster_09_addrc.png)

4. Go to your user and assign the new Role Collection "Joule_Role_Collection" to your user. You are ready to deploy  and execute Joule skills.


### Optional: Integrate your standalone SAP Build Environment in SAP Build Work Zone

After you have created your first Joule Studio app, you can later optionally integrate your standalone SAP Build environment with your Joule project as a "Dynamic URL" app into your SAP Build Work Zone (e.g., for testing). When you create a new app in the Content Manager, choose:

- System: SWZ_Joule
- APP UI Technology: Dynamic URL
- Relative Path to APP (example): /webclient/standalone/da_myjouleskillsenv

  (example for a "standalone environment" and the name "myjouleskillsenv")

![](images/2_setup_workzone_16_appintegration.png)
  
Provide a "Semantic Object" and an "Action" of choice.

![](images/2_setup_workzone_17_appintegration.png)

For more information about setting up SAP Build Workzone, see the tutorial [Deliver Your First SAP Fiori Launchpad Site](https://developers.sap.com/mission.cp-starter-digitalexp-portal.html)



Congratulations!


