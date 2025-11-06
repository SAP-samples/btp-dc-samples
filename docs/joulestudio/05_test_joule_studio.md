# Get Started with a simple Joule Skill example

After you have now set up your Joule Studio environment, you may make your very first steps in Joule Studio with a simple example.

### Create an Environment for your Joule Skills

Enter your SAP Build Lobby, click on your SAP Build Process Automation Subscription in your Subaccount.

1. Enter the "Control Tower" in SAP Build and select "Environments".

    ![alt text](images_testjoule/testjoule_01_envs.png) 

2. Select "Create".

    ![alt text](images_testjoule/testjoule_02_envs.png) 

3. Enter the name "test_env_standalone", select a color, and provide some description. 

    ![alt text](images_testjoule/testjoule_03_envs_alone.png) 

4. Create a second environment, named "test_env_shared".

    ![alt text](images_testjoule/testjoule_04_envs_shared.png) 

5. Click on your environments and select the "Joule" view on your environment. It is empty for now.

    ![alt text](images_testjoule/testjoule_05_envs_.png) 


### Create your first Joule Skill

1. Enter the "Lobby". Select "Create" --> "Joule Skill"

    ![alt text](images_testjoule/testjoule_06_lobby_.png) 

2. Provide a name for the project. E.g., "testJoule_project".

    ![alt text](images_testjoule/testjoule_07_project_.png) 

3. In your project, select "Create" --> "Joule Skill"

    ![alt text](images_testjoule/testjoule_08_skill_.png) 

4. Provide a name, "SimpleSkill", and provide the description "Tell me something about your skills". The description is important. Based on it, Joule will select the skill in a shared environment.

    ![alt text](images_testjoule/testjoule_09_skill2_.png) 

5. Click on your skill and enter Joule Studio.

   Select the first step, "When a scenario is called," and check the configuration.

   ![alt text](images_testjoule/testjoule_10_edit_.png) 

6. Click on the "Plus" icon between the steps. A selection screen opens. Select "Send message".

    ![alt text](images_testjoule/testjoule_11_edit_.png) 

7. Click on your "Send Message" step and open the Message Editor.

    ![alt text](images_testjoule/testjoule_12_edit_.png) 

8. Keep "Illustrated Message", provide the "answer" (e.g., "Joule skills are magic!"), and change the picture, for example, to "Balloons" and save it.

    ![alt text](images_testjoule/testjoule_13_edit_.png) 


### Release Deploy your Joule Skill

1. Save and Release your Joule Skill.

    ![alt text](images_testjoule/testjoule_15_release_.png) 

2. Switch the version of your Project to the "Released" version.

    ![alt text](images_testjoule/testjoule_16_released_.png) 

3. A deploy button will appear; click "Deploy". 

    ![alt text](images_testjoule/testjoule_17_deploy_.png) 

4. Select "test_env_standalone" as the deployment environment. Confirm "Deploy".

    ![alt text](images_testjoule/testjoule_18_deployenv_.png) 

5. Switch back to your environments and select the Joule tab. A "Launch" button will appear. You can now test the skill in a standalone environment, which means only the Joule skills of your project are available in Joule.

    ![alt text](images_testjoule/testjoule_20_env_.png) 

6. Type "Tell me about your skills" in Joule

    ![alt text](images_testjoule/testjoule_22_env_alone.png) 

7. Receive the message you have created.

    ![alt text](images_testjoule/testjoule_23_env_alone.png) 

### Optional: Test your skill in a shared environment

1. Deploy your skill also in your second environment, which you have named "test_env_shared". Once deployed, open this environment. You can now enable the "Share Environment Capabilities" under "Settings".

    ![alt text](images_testjoule/testjoule_24_env_shared.png) 

2. Switch to your Joule-enabled SAP Build Work Zone application. Open a site and select the Joule icon.

    ![alt text](images_testjoule/testjoule_30_workzone.png) 

3. Repeat your test with "Tell me about your skills" in Joule

    ![alt text](images_testjoule/testjoule_31_workzone.png)

4. The results should be the same.

    ![alt text](images_testjoule/testjoule_32_workzone.png) 
