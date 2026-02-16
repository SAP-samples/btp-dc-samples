# Add Logic For Error Handling


Your app still lacks error handling. If creating the new maintenance notification in the backend fails, the user will not actually receive a notification. 

You could have a new notification instance on the BTP, but no corresponding maintenance notification in your SAP S/4HANA cloud destination. The next step will be to enhance the code with error handling using Joule.

1. In Joule, enter this prompt:

    ```
    /cap-app-logic #srv/code/maintenancenotifications-logic.js add error handling. If the creation of the maintenance notification fails, the notification should also not be created, and an error should be issued.
    ```

2. After Joule has created a proposal, review the generated code and accept the code by clicking Accept
The result should look like this:


    ![image]()

3. Let’s check the new code:

    - The upper part of the code is largely unchanged, apart from the new line 17, where a try statement makes sure any error from the backend call in line 19 can be caught and handled.

    - As of line 26, the new error handling that Joule added starts. If no new maintenance notification is created after the API call, the user receives a message, and an error is thrown.

    - If an error is thrown, then it is handled in line 32, and in line 34, the request is rejected. This means that the creation of the notification on the BTP is terminated, and so, if the creation of an SAP S/4HANA maintenance notification fails, the BTP notification is also not created.

Return to the storyboard.

The CAP backend service in the tutorial scenario is now complete.
