# Lab 14 - Manage access with RBAC

### Lab overview

Azure role-based access control (Azure RBAC) helps you manage who has access to Azure resources, what they can do with those resources, and what areas they have access to. Azure RBAC is an authorization system built on Azure Resource Manager that provides fine-grained access management to Azure resources.

In this walkthrough, we will assign roles and view activity logs.

## Lab objectives

In this lab, you will complete the following tasks:

+ Task 1: View and assign roles
+ Task 2: Monitor role assignments and remove a role

## Estimated timing: 15 minutes

## Architecture diagram

![](../images/az900lab14.png)

### Task 1: View and assign roles

In this task, we will assign the Virtual machine contributor role. 

1. On Azure Portal page, in Search resources, services and docs (G+/) box at the top of the portal, enter **Resource groups (1)**, and then select **Resource groups (2)** under services.

   ![image](../images/lab14-image1.png)

1. Then view and select the existing resource group **AZ-900-<inject key="DeploymentID" enableCopy="false"/>**.

1. You will be directed to the overview page of the resource group

1. Click on the **Access control (IAM) (1)** blade, and then switch to the **Roles (2)** tab. Scroll down and notice roles definitions that are available. Use the View link under details to get an idea of each role's permissions. Notice there is also information on the number of users and groups that are assigned to each role.

   ![image](../images/lab14-image3.png)

1. On the **AZ-900-<inject key="DeploymentID" enableCopy="false"/> | Access control (IAM)** blade select **+ Add (1)** then from drop-down select **Add Role assignments (2)**. 

   ![image](../images/lab14-image4.png)
   
1. In  **Add Role assignments** blade on the **Role** tab, Search for the **Virtual Machine Contributor (1)** role and select **Virtual Machine Contributor (2)** then click on **Next (3)**

    ![image](../images/lab14-image5.png)
   

1. On the **Members** tab, make sure to select **Assign access to: the user, group, or service principal (1)**. Next, click **+ Select members (2)** to open a popup window. In the search bar within the popup, enter your Azure account name (Username: **<inject key="AzureAdUserEmail"></inject>) (3)**, and then click **select (4)**.

    ![image](../images/lab14-image6.png)

1. Click **Review + Assign**.

   ![image](../images/lab14-image7.png)
   
     **Note:** The Virtual machine contributor role lets you manage virtual machines, but not access their operating system or manage the virtual network and storage account they are connected to. User name can be obtained from the Lab Environment output page

1. Back on **AZ-900-<inject key="DeploymentID" enableCopy="false"/> | Access control (IAM)** blade, select **Role assignments** tab.

    ![image](../images/lab14-image8.png)

1. **Refresh** the Role assignments page and ensure you are now listed as a Virtual machine contributor (you need to scroll down).

     ![image](../images/lab14-image9.png)

    **Note**: This assignment does not grant you any additional privileges, since your account has already the Owner role, which includes all privileges associated with the Contributor role.

### Task 2: Monitor role assignments and remove a role

In this task, we will view the activity log to verify the role assignment, and then remove the role. 

1. On the **AZ-900-<inject key="DeploymentID" enableCopy="false"/>** resource group blade, click **Activity log**.


1. In search bar search for **Create role assignment**.

1. Verify the Activity log shows your role assignment. (With your User Id). 

     ![image](../images/lab14-image13.png)
   
    **Note**: Can you figure out how to remove your role assignment?

<validation step="d5b66b53-22d2-4a55-bff0-7415cf18338d"/>

   > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
   > - Click Lab Validation tab located at the upper right corner of the lab guide section and navigate to the Lab Validation tab.
   > - Hit the Validate button for the corresponding task.
   > - If you receive a success message, you can proceed to the next task. If not, carefully read the error message and retry the step, following the instructions in the lab guide.
   > - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

### Review

In this lab, you have completed:
- View and assign roles
- Monitor role assignments and remove a role

## Reference link

- https://learn.microsoft.com/en-us/azure/role-based-access-control/overview
  
## You have successfully completed this lab. Proceed with the next lab.
