# 10 - Create a VM with PowerShell

In this walk-through, we will configure the Cloud Shell, use Azure PowerShell module to create a resource group and virtual machine, and review Azure Advisor recommendations.

## Task 1: Configure the Cloud Shell

In this task, we will configure Cloud Shell.

1. Click on the Azure Portal icon on the VM desktop and login with the Azure credentials from the Lab Environment output page.

2. From the Azure portal, open the **Azure Cloud Shell** by clicking on the icon in the top right of the Azure Portal.

    ![Screenshot of Azure Portal Azure Cloud Shell icon.](../images/AZ-900-1001.png)

3. If you have previously used the Cloud Shell, proceed to the next task.

4. When prompted to select either **Bash** or **PowerShell**, select **PowerShell**.

5. When prompted, select **Show advanced settings** and then select **Use existing** and choose existing resource group. Then select **Create new** against Storage account as well as File Share and provide a unique value in both of the fields and then click on **Create storage**, and wait for the Azure Cloud Shell to initialize.


## Task 2: Create a virtual machine

In this task, we will use PowerShell to create a resource group and a virtual machine.

1. Ensure **PowerShell** is selected in the upper-left drop-down menu of the Cloud Shell pane.

2. In the PowerShell session, within the Cloud Shell pane, get existing resource group.

    ```
    Get-AZResourceGroup
    ```

3. Verify your resource group.

    ```
    Get-AzResourceGroup | Format-Table
    ```

4. Create a virtual machine. When prompted provide the username (**azureuser**) and the password (**Pa$$w0rd1234**) that will be configured as the local Administrator account on that virtual machines. Ensure that you include the tick (`) characters at the end of each line except for the last one (there should not be any tick characters if you type entire command on a single line). Replace myRGPS-[DeploymentId] in the below command with the Resource Group Name from the output of the previous command

    ```
    New-AzVm `
    -ResourceGroupName "myRGPS-[DeploymentId]" `
    -Name "myVMPS" `
    -Location "East US" `
    -VirtualNetworkName "myVnetPS" `
    -SubnetName "mySubnetPS" `
    -SecurityGroupName "myNSGPS" `
    -PublicIpAddressName "myPublicIpPS"
    ```

    **Note**: Wait for VM to deploy before closing PowerShell

5. Close the PowerShell session Cloud Shell pane.

6. In the Azure portal, search for **Virtual machines** and verify the **myVMPS** is running. This may take a few minutes.

    ![Screenshot of the virtual machines page with myVMPS in a running state.](../images/AZ-900-10-02.png)

7. Access the new virtual machine and review the Overview and Networking settings to verify your information was correctly deployed.


## Task 3: Execute commands in the Cloud Shell

In this task, we will practice executing PowerShell commands from the Cloud Shell.

1. From the Azure portal, open the **Azure Cloud Shell** by clicking on the icon in the top right of the Azure Portal.

2. Ensure **PowerShell** is selected in the upper-left drop-down menu of the Cloud Shell pane.

3. Retrieve information about your virtual machine including name, resource group, location, and status. Notice the PowerState is **running**.

    ```
    Get-AzVM -name myVMPS -status | Format-Table -autosize
    ```

4. Stop the virtual machine. When prompted confirm (Yes) to the action.

    ```
    Stop-AzVM -ResourceGroupName myRGPS-[deployId] -Name myVMPS
    ```
    **Note**: Replace myRGPS-[deployId] with **myRGPS-<inject key="DeploymentID" enableCopy="false" />**

5. Verify your virtual machine state. The PowerState should now be **deallocated**. You can also verify the virtual machine status in the portal.

    ```
    Get-AzVM -name myVMPS -status | Format-Table -autosize
    ```

## Task 4: Review Azure Advisor Recommendations


**Note:** This same task is in the Create a VM with Azure CLI lab.

In this task, we will review Azure Advisor recommendations for our virtual machine.

1. From the **All services** blade, search for and select **Advisor**.

2. On the **Advisor** blade, select **Overview**. Notice recommendations are grouped by Reliability, Security, Performance, and Cost.

    ![Screenshot of the Advisor Overview page. ](../images/AZ-900-10-03.png)

3. Select **All recommendations** and take time to view each recommendation and suggested actions.

    **Note:** Depending on your resources, your recommendations will be different.

    ![Screenshot of the Advisor All recommendations page. ](../images/AZ-900-10-04.png)

4. Notice that you can download the recommendations as a CSV or PDF file.

5. Notice that you can create alerts.

6. If you have time, continue to experiment with Azure PowerShell.

Congratulations! You have configured Cloud Shell, created a virtual machine using PowerShell, practiced with PowerShell commands, and viewed Advisor recommendations.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Click the (...) icon located at the upper right corner of the lab guide section and navigate to the Lab Validation Page.
> - Hit the Validate button for the corresponding task.If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

Select the **Resources** tab, then in actions select deallocate to deallocate the VM, it will be Cost effective
