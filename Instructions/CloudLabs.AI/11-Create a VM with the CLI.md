# 11 - Create a VM with the CLI

In this walk-through, we will configure the Cloud Shell, use Azure CLI to create a virtual machine, and review Azure Advisor recommendations. 

# Task 1: Configure the Cloud Shell

In this task, we will configure Cloud Shell. 

1. Sign in to the [Azure portal](https://portal.azure.com).

2. From the Azure portal, open the **Azure Cloud Shell** by clicking on the icon in the top right of the Azure Portal.

    ![Screenshot of Azure Portal Azure Cloud Shell icon.](../images/AZ-900-1101.png)

3. If you have previously used the Cloud Shell, proceed to the next task. 

4. When prompted to select either **Bash** or **PowerShell**, select **Bash**. 

5. When prompted, select **Show advanced settings** and then select **Use existing** and choose existing resource group. Then select **Create new** against Storage account as well as File Share and provide a unique value in both of the fields and then click on **Create storage**, and wait for the Azure Cloud Shell to initialize. 

# Task 2: Use CLI to create a virtual machine

In this task, we will use Azure CLI to create a resource group and a virtual machine.  

1. Ensure **Bash** is selected in the upper-left drop-down menu of the Cloud Shell pane (and if not, select it).

    ![Screenshot of Azure Portal Azure Cloud Shell with the Bash dropdown highlighted.](../images/Az-900-1102.png)

2. In the Bash session, within the Cloud Shell pane, get existing resource group. 

    ```cli
    az group list
    ```

3. Format resource group listing output.

    ```cli
    az group list --output table
    ```

4. Create a new virtual machine. Make sure that each line except for the last one is followed by the backslash (`\`) character. If you type the whole command on the same line, do not use any backslash characters. 

    ```cli
    az vm create \
    --name myVMCLI \
    --resource-group myRGCLI-[deployId] \
    --image UbuntuLTS \
    --location EastUS \
    --admin-username azureuser \
    --admin-password Pa$$w0rd1234
    ```

    >**Note**: If you are using the command line on a Windows computer, replace the backslash (`\`) character with the caret (`^`) character.
    
    **Note**: Replace myRGCLI-[deployId] with  **myRGCLI-<inject key="DeploymentID" enableCopy="false" />**
    
    **Note**: The command will take 2 to 3 minutes to complete. The command will create a virtual machine and various resources associated with it such as storage, networking and security resources. Do not continue to the next step until the virtual machine deployment is complete. 

5. When the command finishes running, in the browser window, close the Cloud Shell pane.

6. In the Azure portal, search for **Virtual machines** and verify that **myVMCLI** is running.

    ![Screenshot of the virtual machines page with myVMPS in a running state.](../images/Az-900-11-03.png)


# Task 3: Execute commmands in the Cloud Shell

In this task, we will practice executing CLI commands from the Cloud Shell. 

1. From the Azure portal, open the **Azure Cloud Shell** by clicking on the icon in the top right of the Azure Portal.

2. Ensure **Bash** is selected in the upper-left drop-down menu of the Cloud Shell pane.

3. Retrieve information about the virtual machine you provisioned, including name, resource group, location, and status. Notice the PowerState is **running**.

    ```cli
    az vm show --resource-group myRGCLI-[deployId] --name myVMCLI --show-details --output table 
    ```

4. Stop the virtual machine. Notice the message that billing continues until the virtual machine is deallocated. 

    ```cli
    az vm stop --resource-group myRGCLI-[deployId] --name myVMCLI
    ```

5. Verify your virtual machine status. The PowerState should now be **stopped**.

    ```cli
    az vm show --resource-group myRGCLI-[deployId] --name myVMCLI --show-details --output table 
    ```

**Note**: Replace myRGCLI-[deployId] with  **myRGCLI-<inject key="DeploymentID" enableCopy="false" />**

# Task 4: Review Azure Advisor Recommendations

In this task, we will review Azure Advisor recommendations.

   **Note:** If you have completed the previous lab (Create a VM with PowerShell), then you have already performed this task. 

1. From the **All services** blade, search for and select **Advisor**. 

2. On the **Advisor** blade, select **Overview**. Notice recommendations are grouped by Reliability, Security, Performance, and Cost. 

    ![Screenshot of the Advisor Overview page. ](../images/Az-900-11-04.png)

3. Select **All recommendations** and take time to view each recommendation and suggested actions. 

    **Note:** Depending on your resources, your recommendations will be different. 

    ![Screenshot of the Advisor All recommendations page. ](../images/Az-900-1105.png)

4. Notice that you can download the recommendations as a CSV or PDF file. 

5. Notice that you can create alerts. 

6. If you have time, continue to experiment with Azure CLI. 

Congratulations! You have configured Cloud Shell, created a virtual machine using Azure CLI, practiced with Azure CLI commands, and viewed Advisor recommendations.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Click the (...) icon located at the upper right corner of the lab guide section and navigate to the Lab Validation Page.
> - Hit the Validate button for the corresponding task.If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

Select the **Resources** tab, then in actions select deallocate to deallocate the VM, it will be Cost effective

