# Set up SAP Build Process Automation with a Booster

You can set up SAP Build in two different ways.

You can use the "Cloud Integration Automation" service, a free service in SAP BTP, which helps to onboard BTP scenarios through a guided approach. For more information, see [SAP Help Portal](https://help.sap.com/docs/build-service/build-service-guide/initial-setup-of-sap-build?locale=en-US).


This tutorial uses individual setup of SAP Build services using a specific set-up Booster for SAP Build Process Automation, Joule, and optional SAP Build Work Zone.



### Prerequisites

You need an entitlement for SAP Build Process Automation and the service plan **build_default**. You will also temporarily need the service "standard."

You need a Cloud Identity Services tenant (Identity and Authentication service, IAS). If you don't have one, create one first. If you need help creating one, see the Discovery Center mission [Get Started with SAP BTP—Cloud Identity Service Provider](https://discovery-center.cloud.sap/missiondetail/4325/4605/).

You need an entitlement and a free quota for SAP BTP, Cloud Foundry Runtime.


### Check your Entitlements

The Booster for SAP Build Process Automation does not support build-default service plan requires a standard service plan for set-up in addition.

1. Open your Global Account, navigate to Entitlements --> Service Assignments, and search for "Process Automation". Make sure you have the necessary entitlements.

    ![](images/processa_booster_00_entitlements_.png)


### Start Booster for SAP Build Process Automation

1. Navigate in your Global account to "Boosters". Search for "Process Automation".

    Select the booster "Set up account for SAP Build Process Automation".

    ![](images/processa_booster_00_select_.png)

    Click Start. You will only install the mandatory components.

2. Step 1: Check Prerequisites.

    This step must be at least "green" or "warning". A warning means you don't have the entitlements for the optional service plans.

    ![](images/processa_booster_01_.png)

3. Step 2: Either create a new Subaccount or use an existing one. In this example, you create a Subaccount with all entitlements.

    ![](images/processa_booster_02_.png)

    ...or with missing optional entitlements

    ![](images/processa_booster_02_2.png)

4. Step 3: Name your subaccount, choose Provider and Region (where Joule is also available)

    Choose "standard" as the service plan. The booster does not support "build_default". You will change the service plan later (if you use a booster with a "free" plan, you will have to change to the "standard" plan first).

    ![](images/processa_booster_03_.png)

5. Step 4: Add users

    Please provide your Customer Identity Provider for Applications here. Otherwise, Joule Studio will not work.

    ![](images/processa_booster_04_.png)

6. Step 5: Review and Start

    The installation of SAP Build Process Automation 

    ![](images/processa_booster_05_.png)

7. When the booster has finished, navigate to your (new) Subaccount --> Instances and Subscriptions.

    ![](images/processa_booster_06_.png)

8. Check your newly created Process Automation Service.

    If cannot update the service plan (as shown), the entitlement for "Build_default is missing.

    ![](images/processa_booster_07_0_check.png)
    
    Add the missing entitlement. Do not forget to save afterwards.

    ![](images/processa_booster_07_1_check.png)

    ![](images/processa_booster_07_2_check.png)

    Change your service plan to "build_default"

    ![](images/processa_booster_07_3_check.png)

    ![](images/processa_booster_07_4_check.png)
    
    

9. Check your Destinations and additional settings

    ![](images/processa_booster_08_dest.png)

    Trust Configuration

    ![](images/processa_booster_09_trust.png)

    Custom IAS User and assigned Role Collections

    ![](images/processa_booster_10_user.png)

9. Click on your Subscription "SAP Build Process Automation" in order to open it.

    ![](images/05_setupjoule_booster_08_runjoule.png)

    You probably have to authenticate yourself with your Custom IAS User (if you have older authentication in your browser cache, you need to log off first or refresh your cache, or restart your browser)

    The SAP Build Lobby should start.

    ![](images/processa_booster_11_buildlobby.png)
