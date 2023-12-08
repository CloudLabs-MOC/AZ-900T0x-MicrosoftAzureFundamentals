# 02 - Create a Web App

In this walkthrough, we will create a new web app that runs a Docker container. The container displays a Welcome message.

# Task 1: Create a Web App

Azure App Service is actually a collection of four services, all of which are built to help you host and run web applications. The four services (Web Apps, Mobile Apps, API Apps, and Logic Apps) look different, but in the end they all operate in very similar ways. Web Apps are the most commonly used of the four services, and this is the service that we will be using in this lab.

In this task, you will create an Azure App Service Web App.

1. Click on the Azure Portal icon on the VM desktop and login with the Azure credentials from the Lab Environment output page.

2. From the **Search resources, Services, and docs(G+/)** blade, search for and select **App Services**, and click **+ Create**

3. On the **Basics** tab of the **Create Web App** blade.

    **Note:**  **DeploymentId** can be obtained from the Lab Environment output page.

    | Setting | Value |
    | -- | -- |
    | Subscription | **Choose your subscription** |
    | Resource Group | **myRGWebApp1-<inject key="DeploymentID" enableCopy="false"/>** (use existing) |
    | Name | **myDockerWebApp<inject key="DeploymentID" enableCopy="false"/>** |
    | Publish | **Docker Container** |
    | Operating System | **Linux** |
    | Region | **East US** (ignore any service plan availability warnings) |
    | | |
    

4. Click **Next > Docker** and configure the container information. The startup command is optional and not needed in this exercise.

    **Note:** This is same container that was used in the Container Instances walkthrough to display a hello world message.

    | Setting | Value |
    | -- | -- |
    | Options | **Single container** |
    | Image Source | **Docker Hub** |
    | Access Type | **Public** |
    | Image and tag | **mcr.microsoft.com/azuredocs/aci-helloworld** |
    | | |

5. Click **Review + create**, and then click **Create**.

# Task 2: Test the Web App

In this task, we will test the web app.

1. Wait for the Web App to deploy.

2. From **Notifications** click **Go to resource**.

3. On the **Overview** blade, locate the **Default Domain** entry.

    ![Screenshot of the web app properties blade. The URL is highlighted.](../images/AZ-900-module-02-app-service.png)

4. Click on the **URL** to open the new browser tab and display the Welcome to Azure Container Instances page.

    ![Screenshot of the Welcome to Azure Container Instance page.](../images/0802.png)

5. Switch back to the **Overview** blade of your web app and note that it includes several charts. If you repeat step 4 a few times, you should be able to see correspoding telemetry being displayed in the charts. This includes number of requests and average response time.


  > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
  > - Click the (...) icon located at the upper right corner of the lab guide section and navigate to the Lab Validation Page.
  > - Hit the Validate button for the corresponding task.If you receive a success message, you can proceed to the next task. 
  > - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
  > - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

6. Select the **Resources** tab, then in actions select deallocate for deallocated the VM, it will be Cost effective.
