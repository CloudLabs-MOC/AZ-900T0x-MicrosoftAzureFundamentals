# 09 - Create a VM with a Template

In this walkthrough, we will deploy a virtual machine with a QuickStart template and examine monitoring capabilities.

# Task 1: Explore the gallery and locate a template

In this task, we will browse the Azure QuickStart gallery and deploy a template that creates a virtual machine.

1. Double click on the **Microsoft Edge** icon on the VM desktop to open the browser

2. In a new tab, access the [Azure Quickstart Templates gallery](https://azure.microsoft.com/resources/templates?azure-portal=true). In the gallery, you will find many popular and recently updated templates. These templates automate the deployment of Azure resources, including the installation of popular software packages.

3. Browse through the many different types of templates that are available. Are there any templates that are of interest to you?

4. Search and Select the **Deploy a simple Windows VM**.

    **Note**: The **Deploy to Azure** button enables you to deploy the template via the Azure portal. During such deployment, you will be prompted only for a small set of configuration parameters. 

5. Click the **Deploy to Azure** button. Your browser session will be automatically redirected to the [Azure portal](http://portal.azure.com/).

6. If prompted, sign in to the Azure with the **Username** and **Password** provided in the **Environment Details** Tab.

7. Click **Edit template**. The Resource Manager template format uses the JSON format. Review the parameters and variables.  Then locate the parameter for the virtual machine name. Go to line no 146 and Change the name to **myVMTemplate**, and **Save** your changes. 

    ![Screenshot of the template with the VM name change highlighted.](../images/0901.png)

8. Now configure the parameters required by the template (replace ***XXXX*** in the DNS label prefix with DeploymentID). Leave the defaults for everything else. 

    | Setting| Value|
    |----|----|
    | Subscription | **Choose your subscription**|
    | Resource group | **myRGTemplate-[DeploymentID]** (use existing) |
    | Location | **Keep default** |
    | Admin username | **azureuser** |
    | Admin password | **Pa$$w0rd1234** |
    | DNS label prefix | **myvmtemplate*xxxx*** |
    | Windows OS version | **2019-datacenter-gensecond** |

   **Note**: DeploymentId can be obtained from the **Environment Details** Tab.
    
  9. Click **Review + Create**.
  10. Click the **Create** 
  11. Monitor your deployment. 

# Task 2: Verify and monitor your virtual machine deployment

In this task, we will verify the virtual machine is deployed correctly. 

1. From the **All services** blade, search for and select **Virtual machines**.

2. Ensure your new virtual machine was created. 

    ![Screenshot of the virtual machines page. The new VM is shown and running.](../images/0902.png)

3. Select your virtual machine and on the **Overview** pane scroll down to view monitoring data.

    **Note**: The monitoring timeframe can be adjusted from one hour to 30 days.

4. Review different charts that are provided including **CPU (average)**, **Network (total)**, and **Disk bytes (total)**. 

    ![Screenshot of the virtual machine monitoring charts.](../images/0903.png)

5. Click on any chart. Note that you can **Add metrics** and change the chart type.

6. Return to the **Overview** blade.

7. Click on the **Activity log** (left pane). Activity logs record such events as the creation or modification of resources. 

8. Click **Add filter**, and experiment with searching for different event types and operations. 

    ![Screenshot of the Add filters page with Event type selected.](../images/0904.png)


