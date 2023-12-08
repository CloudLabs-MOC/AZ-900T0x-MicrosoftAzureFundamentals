# 17 - Create an Azure Policy

In this walkthrough, we will create an Azure Policy to restrict the deployment of Azure resources to a specific location.

# Task 1: Create a Policy assignment

In this task, we will configure the allowed location policy and assign it to our subscription. 

1.  If not before login to Azure portal, Click on the **Azure Portal** icon on the VM desktop and log in with the **Username** <inject key="AzureAdUserEmail"></inject> and **Password** <inject key="AzureAdUserPassword"></inject> .

2. From the **Search resources, Services, and docs(G+/)** blade, search for and select **Policy**, under the **Authoring** section click **Definitions**.  Take a moment to review the list of built-in policy definitions. For example, in the **Category** drop-down select only **Compute**. Notice the **Allowed virtual machine size SKUs** definition enables you to specify a set of virtual machine SKUs that your organization can deploy.

3. Return to the **Policy** page, under the **Authoring** section click **Assignments**. An assignment is a policy that has been assigned to take place within a specific scope. For example, a definition could be assigned to the subscription scope. 

4. Click **Assign Policy** at the top of the **Policy - Assignments** page.

5. On the **Assign Policy** page, select the Scope selector by clicking the ellipsis.

    ![Screenshot of the scope selector ellipses.](../images/scope.png)

6. Ensure your subscription is selected. Your subscription name might be different. Notice you can optionally scope the policy to a resource group. Leave the defaults and click **Select**. 

    **Note**: A scope determines what resources or grouping of resources the policy assignment applies to. In our case we could assign this policy to a specific resource group, however, we chose to assign the policy at the subscription level. Be aware that resources can be excluded based on the scope configuration. Exclusions are optional.

    ![Screenshot of the Scope pane with field values filled in and the Select button highlighted. ](../images/scope2.png)

7. Select the **Policy definition** ellipsis button. In the **Search** box type **location** and click on the **Allowed locations** definition, then click **Add**.

    **Note**: This **Allowed Locations** policy definition will specify a location into which all resources must be deployed. If a different location is chosen, deployment will not be allowed. For more information view the [Azure Policy Samples](https://docs.microsoft.com/en-us/azure/governance/policy/samples/index) page.

   ![Screenshot of Available Definitions pane with various fields highlighted and the Audit VMs that do not use managed disks option selected.](../images/location.png)

8.  In the **Assign policy** pane, switch to the **Parameters** tab, click on the arrow at the end of the **Allowed locations** box, and from the subsequent list choose **Japan West**. Leave all other values as they are and click **Review + create**, and then **Create**.

    ![Screenshot of Assign policy pane with various fields filled in along with the location Japan West populated and the assign button highlighted.](../images/allowedloc.png)

9. The **Allowed locations** policy assignment is now listed on the **Policy - Assignments** pane and it is now in place, enforcing the policy at the scope level we specified (subscription level).

# Task 2: Test Allowed location policy

In this task, we will test the Allowed location policy. 

1. In the Azure Portal, from the **Search resources, Services, and docs(G+/)** blade, search for and select **Storage accounts**, and then click **+ Create**.

2. Configure the storage account. Leave the defaults for everything else. 

    | Setting | Value | 
    | --- | --- |
    | Subscription | **Use your subscription** |
    | Resource group | **myRGPolicy** (use existing) |
    | Storage account name | **storageaccount<inject key="DeploymentID" enableCopy="false"/>** |
    | Location | **(US) East US** |
    | | |

    Click on **Review** and once validation gets success, click on **Create**.
    
     You will receive the error message under the Region setting stating that Policy enforcement and Value does not meet requirements on resource, including the **Allowed locations** policy name.
     
   
   > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
   > - Click the (...) icon located at the upper right corner of the lab guide section and navigate to the Lab Validation Page.
   > - Hit the Validate button for the corresponding task.If you receive a success message, you can proceed to the next task. 
   > - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
   > - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

# Task 3: Delete the policy assignment

In this task, we will remove the Allowed location policy assignment and test. 

We will delete the policy assignment to ensure we are not blocked on any future work we wish to do.

1. From the **Search resources, Services, and docs(G+/)** blade, search for and select **Policy** and then click your **Allowed locations** policy.

    **Note**: On the **Policy** blade, you can view the compliance state of the various policies you have assigned.

    **Note**: The Allowed location policy may show non-compliant resources. If so, these are resources created before the policy assignment.

2. Click **Delete Assignment** in the top menu.

   ![Screenshot of the Delete Assignment menu item.](../images/delete.png)

3. Confirm you wish to delete the policy assignment in the **Delete assignment** dialogue by clicking **Yes**

4. Try to create another storage account to ensure the policy is no longer in effect.

    **Note**: Common scenarios where the **Allowed locations** policy can be useful include: 
    - *Cost Tracking*: You could have different subscriptions for different regional locations. The policy will ensure that all resources are deployed in the intended region to help with cost tracking. 
    - *Data Residency and Security compliance*: You could also have data residency requirements, create subscriptions per customer or specific workloads, and define that all resources must be deployed in a particular data center to ensure data and security compliance requirements.

Congratulations! You have created an Azure Policy to restrict the deployment of Azure resources to a particular data center.


