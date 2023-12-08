# 14 - Manage access with RBAC

In this walkthrough, we will assign roles and view activity logs. 

# Task 1: View and assign roles

In this task, we will assign the Virtual machine contributor role. 

1. Click on the Azure Portal icon on the VM desktop.

2. From the **Search resources, services, and docs** blade, search for and select **Resource groups**

3. Then view the existing resource group. 

    | Setting | Value |
    | -- | -- |
    | Resource group | **myRGRBAC-<inject key="DeploymentID" enableCopy="false"/>** |

     
4. Click on the existing resource group

5. You will be directed to the overview page of the resource group

6. Click on the **Access control (IAM)** blade, and then switch to the **Roles** tab. Scroll through the large number of roles definitions that are available. Use the Informational icons to get an idea of each role's permissions. Notice there is also information on the number of users and groups that are assigned to each role.

   ![image](../images/AZ-900-access.png)

 7. Switch to the **Role assignments** tab of the **myRGRBAC-<inject key="DeploymentID" enableCopy="false"/> Access control (IAM)** blade, click **+ Add** and then click **Add role assignment**. In  Assignment type keep things as default, then switch to Roles tab, Search for the Virtual Machine Contributor role and select. Switch to the "Members" tab and Assign access to: the user, group, or service principal. Then click + Select members and type your azure account name (Username: <inject key="AzureAdUserEmail"></inject>) to the popup search function and hit 'select.' Then hit 'Review + Assign'.

    ![image](../images/AZ-900-module-14-addrole.png)

     **Note:** The Virtual machine contributor role lets you manage virtual machines, but not access their operating system or manage the virtual network and storage account they are connected to. User name can be obtained from the Lab Environment output page


8. **Refresh** the Role assignments page and ensure you are now listed as a Virtual machine contributor. 

    **Note**: This assignment does not grant you any additional privileges, since your account has already the Owner role, which includes all privileges associated with the Contributor role.

# Task 2: Monitor role assignments and remove a role

In this task, we will view the activity log to verify the role assignment, and then remove the role. 

1. On the myRGRBAC-<inject key="DeploymentID" enableCopy="false"/> resource group blade, click **Activity log**.

2. Click **Add filter**, select **Operation**, and then **Create role assignment**.

    ![Screenshot of the Activity log page with configured filter.](../images/1503.png)

3. Verify the Activity log shows your role assignment. (With your User Id). 

    **Note**: Can you figure out how to remove your role assignment?

     > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
     > - Click the (...) icon located at the upper right corner of the lab guide section and navigate to the Lab Validation Page.
     > - Hit the Validate button for the corresponding task.If you receive a success message, you can proceed to the next task. 
     > - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
     > - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.
 
 4. Select the **Resources** tab, then in actions select deallocate for deallocated the VM, it will be Cost effective.



