
# 03 - Deploy Azure Container Instances

In this walkthrough we create, configure, and deploy a Docker container by using Azure Container Instances (ACI) in the Azure Portal. The container is a Welcome to ACI web application that displays a static HTML page. 

## Task 1: Create a container instance

In this task, we will create a new container instance for the web application. 

1. Click on the Azure Portal icon on the VM desktop and login with the Azure credentials from the Lab Environment output page.

2. From the **Search resources, Services, and docs(G+/)** blade, search for and select **Container instances** and then click **+ Create**. 

3. Provide the following Basic details for the new container instance  (leave the defaults for everything else)): 

	| Setting| Value|
	|----|----|
	| Subscription | **Choose your subscription** |
	| Resource group | **myRGContainer-<inject key="DeploymentID" enableCopy="false" />** (Use Existing) |
	| Container name| **mycontainer**|
	| Region | **(US) East US** |
	| Image source| **Other registry**|
	| Image type| **Public**|
	| Image| **mcr.microsoft.com/azuredocs/aci-helloworld**|
	| OS type| **Linux** |
	| Size| ***Leave at the default***|

	
4. Configure the Networking tab . Leave all other settings at their default values .

	| Setting| Value|
	|--|--|
	| DNS name label| **mycontainerdns<inject key="DeploymentID" enableCopy="false" />** |

	**Note**: Your container will be publicly reachable at dns-name-label.region.azurecontainer.io. If you receive a **DNS name label not available** error message following the deployment.

    ![Screenshot of the configuration pane of the create container instances blade, in Azure portal, with the DNS name label entered. ](../images/AZ900-01.png)

5. Click **Review and Create** to start the automatic validation process.

6. Click **Create** to create the container instance. 

7. Monitor the deployment page and the **Notifications** page. 

8. While you wait you may be interested in viewing the [sample code behind this simple application](https://github.com/Azure-Samples/aci-helloworld). Browse the \app folder. 

## Task 2: Verify deployment of the container instance

In this task, we verify that the container instance is running by ensuring that the welcome page displays.

1. After the deployment is complete, click the **Go to resource** link the deployment blade or the link to the resource in the Notification area.

2. On the **Overview** blade of **mycontainer**, ensure your container **Status** is **Running**. 

3. Locate the Fully Qualified Domain Name (FQDN).

   ![Screenshot of the overview pane for the newly created container in Azure portal, with the FQDN highlighted. ](../images/AZ-900-02.png)

2. Copy the container's FQDN into the new browser tab and press **Enter**. The Welcome page should display.

   **Note**: It might take 10-15 minutes to load the page.
 
   ![Screenshot of the ACI welcome message shown in a web browser.](../images/AZ-900-0300.png)
	

   **Note**: You could also use the container IP address in your browser. 

Congratulations! You have used Azure Portal to successfully deploy an application to a container in Azure Container Instance.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Click the (...) icon located at the upper right corner of the lab guide section and navigate to the Lab Validation Page.
> - Hit the Validate button for the corresponding task.If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

  Select the **Resources** tab, then in actions select deallocate to deallocate the VM, it will be Cost effective

