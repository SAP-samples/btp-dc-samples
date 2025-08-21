# Set Up SAP Start with Booster and include Joule

SAP Start is a predefined central entry point that enables accessing SAP cloud business solutions that are integrated with it and displays user-specific business content from these solutions.

SAP Start is based on SAP Build Work Zone, standard edition with the service plan "foundation" or "standard".

The initial setup of SAP Start can be done either by an automated setup that is based on running a SAP BTP Global Account Booster, or by a manual setup.

For manual setup and more information, see the SAP Start documentation at [SAP Help Portal](https://help.sap.com/docs/start/sap-start/setup).

### Set Up with Boosters

For automated set up you can either use the Booster "Set Up SAP Start" or the Booster "Set up an account for SAP Task Center with SAP Build Work Zone, standard edition"

The Booster "Set Up SAP Start" will use the SAP Build Work Zone service plan "foundation", which is restricted. It contains only one site in Build Work Zone, the  SAP Start site. 

**Note:** You cannot upgrade later from the foundation service plan to a "standard" service plan. You have to add SAP Task Center Service manually. You cannot use an existing Subaccount. In this case use manual setup. You can still use the booster for training.

The Booster "Set up an account for SAP Task Center with SAP Build Work Zone, standard edition", uses service plan "standard", which allow you to create addition Work Zone Sites. It also installs and integrates SAP Task Center with SAP Start.

In base cases you have to include your Joule system afterwards manually to use Joule in SAP Start.

### Prerequisites for Booster "Set Up SAP Start"

- You need an entitlement for SAP Build Work Zone, standard edition service plan foundation.

- You need a Cloud Identity Services tenant (Identity and Authentication service, IAS). If you don't have one, create one first. If you need help creating one, see the Discovery Center mission [Get Started with SAP BTP—Cloud Identity Service Provider](https://discovery-center.cloud.sap/missiondetail/4325/4605/).

- Optional: You need an entitlement for Joule with a service plan foundation (or standard for some license models)


### Start Booster "Set Up SAP Start"

Enter your Global Enterprise Account and navigate to "Boosters".

1. Search for the Booster "Set Up SAP Start" and click on the tile.

    ![alt text](images/foundation_booster_01.png)

2. Check the components of the booster.

    ![alt text](images/foundation_booster_03_components.png)

3. Check if you are entitled to use SAP Work Zone (in this picture you see additional entitlements which you need for the other booster).

    ![alt text](images/foundation_booster_02_entitle.png)

4. Start the Booster. 

    Step 1 checks the prerequisites. If anything is green you can continue. Otherwise solve the found issues. For example, if you dont have an Identity Authentication tenant, pause the mission and get one.

    ![alt text](images/foundation_booster_04_step1.png) 

5. Step 2: Set Up Subaccount

    Check the Services, which will be installed and provide a name for the Subaccount which will be created. Select a Provider and select a Region. You may keep the additional generated values or provide yours.

    ![alt text](images/foundation_booster_05_step2.png)

6. Step 3: Select Integrations

    In this basic tutorial, you do not yet provide integrations. 

    ![alt text](images/foundation_booster_06_step3.png) 

7. Step 4: Set Up Integrations

    You need to create a "Formation" "Integration with SAP Start" in order to add later aditional systems.

    You need to include your Identity and Authentication System.

    ![alt text](images/foundation_booster_07_step4.png) 

8. Start the Booster. When he has finished successfully, you see this Success message.

    ![alt text](images/foundation_booster_08_finished.png) 

9. Go to your Global Account and check the "Systems" which have been created.

    ![alt text](images/foundation_booster_09_systems.png) 

10. Go to "Formations". the SAP Start Booster created a formation with SAP Build Work Zone.

     ![alt text](images/foundation_booster_10_formation.png) 

11. Navigate to your Subaccount --> "Services" --> "Instances and Subscriptions" and click on the SAP Build Work Zone link.

     ![alt text](images/foundation_booster_11_subacc.png) 

12. Authenticate yourself with your Identity and Authentication tenant user and enter the Site Directory. You see one predefined Work Zone Site, "SAP Start".

     ![alt text](images/foundation_booster_12_saptstartsite.png) 

12. Click on the "Strat" icon. SAP Start will open. It is empty so far as you did not yet define integrations. Joule is not enabled.

     ![alt text](images/foundation_booster_13_saptstart.png) 


### Start Booster "Setting Up Joule" (optional)

In case you do not have yet a Joule Subscription in your Global Account, you can run the Booster "Setting Up Joule" to add an Joule Subscription to your account.

1. Open your Global Enterprise Account --> Boosters. Search for "Setting Up Joule"

    ![alt text](images/foundation_joule_booster_01.png) 

2. Check the components which will be set up and start the booster.

    ![alt text](images/foundation_joule_booster_02.png) 

3. Step 1: Check Prerequisites. If the results are green, you can continue. Otherwise mitigate the error messages.

    ![alt text](images/foundation_joule_booster_03_step1.png)

4. Step 2: Set up Subaccount

    Provide the service plan ("foundation" or "standard" for some license models) and Subaccount.

    ![alt text](images/foundation_joule_booster_04_step2.png) 

5. Step 3: Select integrations

    Select SAP Build Work Zone. If you do not use it in a productive environment, choose "Testing".

    ![alt text](images/foundation_joule_booster_05_step3.png) 

6. Select the capability "SAP Build Work Zone" and decide if you want to store conversation data.

    ![alt text](images/foundation_joule_booster_06_step4.png) 

7. Select your Build Work Zone System of your Global Account

    ![alt text](images/foundation_joule_booster_07_step5.png) 

8. Select "Next", Review and Start the Booster.

    ![alt text](images/foundation_joule_booster_08_step6.png) 

9. Once it has finished you will see the success message.
 
    ![alt text](images/foundation_joule_booster_09_finished.png) 


### Integrate Joule

Joule is a conversational user interface that can be integrated with SAP Start. Once you integrate Joule, you can open it from the header of SAP Start, to display the Joule panel.

Add the Joule system created by the booster to the SAP Start formation. 

1. In your global account, select System Landscape from the left panel, and select the Formations tab.   

    Search for your formation of type Integration with SAP Start and click Include Systems (in the top right corner of the formation).

    ![alt text](images/foundation_joule_include_01.png) 

2. Select the Joule System and click "Next"

    ![alt text](images/foundation_joule_include_02.png) 

3. Click "Include"

    ![alt text](images/foundation_joule_include_03.png) 

4. The Formation will be synchronized.

    ![alt text](images/foundation_joule_include_04.png) 

5. Joule has been subscribed. Click in the Joule service to get the service status.

    Click on the Work Zone service again.

    ![alt text](images/foundation_joule_include_05_workzone.png) 

6. You now have the little purple Joule icon in SAP Start. Click on it.

![alt text](images/foundation_joule_include_06_joule.png)

7. Ask Joule a question.

![alt text](images/foundation_joule_include_07_joule.png)


Congratulations!
