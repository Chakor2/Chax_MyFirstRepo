# Customize user account lockout settings

By default, Hitachi Cloud Accelerator Platform users are locked out of their account for two hours after three unsuccessful sign-in attempts. If required, administrators can modify the number of failed sign-in attempts and the lockout duration.

> **Note:** To customize the lockout settings for user accounts, you must have administrative access to the computer from which Cloud Accelerator Platform was deployed.

**To customize lockout settings for user accounts, perform the following actions:**

1. Connect to the computer from which Cloud Accelerator Platform was deployed.

2. Navigate to the **platform-bootstrap-hcap** folder.

3. In the **config** sub-folder, open the **customer.yml** file and locate the **hcapcore** section.

4. To modify the number of failed login attempts, perform the following actions:

      1. If the **authnz_brute_failed_attempts** property is not available under the **hcapcore** section, add the property.

      2. Update the number of failed sign-in attempts, as shown in the example below:

         ```
         authnz_brute_failed_attempts: 5
         ```

5. To modify the lockout duration, perform the following actions:

      1. If the **authnz_brute_locked_duration_in_min** property is not available under the **hcapcore** section, add the property.

      2. Update the lockout duration (in minutes), as shown in the example below:

         ```
         authnz_brute_locked_duration_in_min: 60
         ```

6. Save the **customer.yml** file.

7. For your changes to take effect, ensure that you are in the **platform-bootstrap-hcap** folder and then run the following command to redeploy Cloud Accelerator Platform.<br>

      ```
      bundle exec rake app:deploy
      ```

