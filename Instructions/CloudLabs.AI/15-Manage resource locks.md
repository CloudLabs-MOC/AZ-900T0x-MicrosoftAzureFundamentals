# 15 - Manage resource locks

In this walkthrough, we will verify the existing resource group, add a lock to the resource group and test deletion, test deleting a resource in the resource group, and remove the resource lock. 

# Task 1: Verify the existing resource group

In this task, we will verify the existing resource group for this exercise. 

1. Click on the **Azure Portal** icon on the VM desktop and log in with the **Username** and **Password** provided in the Lab Environment Tab.

2. From the **All services** blade, search for and select **Resource groups**, then view the existing resource group.

# Task 2:  Add a Lock to the resource group and test deletion

In this task, we will add a resource lock to the resource group and test deleting the resource group. 

1. In the Azure portal, navigate to the existing resource group **myRGLocks-<inject key="DeploymentID" enableCopy="false" />**.

2. You can apply a lock to a subscription, resource group, or individual resource to prevent accidental deletion or modification of critical resources. 

3. In the **Settings** section, click **Locks**, and then click **+ Add**. 

    ![Screenshot of the myRGLocks-[deployId] resource group with the Locks pane displaying.](../images/AZ900-1501.png)

4. Configure the new lock. When you are done click **OK**. 

    | Setting | Value | 
    | --- | --- |
    | Lock name | **RGLock** |
    | Lock Type | **Delete** |
    | | |

5. Click **Overview** and click **Delete resource group**. Type the name of the resource group and click **Delete**. You receive an error message stating the resource group is locked and can't be deleted.

    ![Screenshot of the delete locks failed.](../images/1602.png)

# Task 3: Test deleting a member of the resource group

In this task, we will test if the resource lock protects a storage account in the resource group. 

1. From the **All services** blade, search for and select **Storage accounts**, and then click **+ Create**. 

2. On the **Basics** tab of the **Create storage account** blade, fill in the following information. Leave the defaults for everything else.

    | Setting | Value |
    | --- | --- |
    | Subscription | **Select your subscription** |
    | Resource group | **myRGLocks-<inject key="DeploymentID" enableCopy="false" />** |
    | Storage account name | **storageaccount<inject key="DeploymentID" enableCopy="false" />** |
    | Location | **(US) East US**  |
    | Performance | **Standard** |
    | Replication | **Locally redundant storage (LRS)** |


3. Click **Review + Create** to review your storage account settings and allow Azure to validate the configuration. 

4. Once validated, click **Create**. Wait for the notification that the account was successfully created. 

5.  Wait for the notification that the storage account was successfully created. 

6. Access your new storage account and from the **Overview** pane, click **Delete**. You receive an error message stating the resource or its parent has a delete lock. 

    ![Screenshot of the error deleting the storage account.](../images/1603.png)

    **Note**: Although we did not create a lock specifically for the storage account, we did create a lock at the resource group level, which contains the storage account. As such, this *parent* level lock prevents us from deleting the resource and the storage account inherits the lock from the parent.

# Task 4: Remove the resource lock

In this task, we will remove the resource lock and test. 

1. Return to the **myRGLocks-<inject key="DeploymentID" enableCopy="false" />** resource group blade and, in the **Settings** section, click **Locks**.
    
2. Click the **Delete** link to the right of the **RGLock** entry.

    ![Screenshot of the Lock with the Delete link highlighted.](../images/AZ-900-1502.png)

3. Return to the storage account blade and confirm you can now delete the resource.

Congratulations! You created a resource group, added a lock to the resource group and tested deletion, tested deleting a resource in the resource group and removed the resource lock. 

 **Note** : **Wait for 10 minutes before heading to the Validation Step**
 
 > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Click the (...) icon located at the upper right corner of the lab guide section and navigate to the Lab Validation Page.
> - Hit the Validate button for the corresponding task.If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

Select the **Resources** tab, then in actions select deallocate to deallocate the VM, it will be Cost effective
