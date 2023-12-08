# 12 - Implement Azure Key Vault

In this walkthrough, we will create an Azure Key vault and then create a password secret within that key vault, providing a securely stored, centrally managed password for use with applications.

# Task 1: Create an Azure Key Vault

1. Click on the Azure Portal icon on the VM desktop and log in with the Azure using the Username and Password provided in the Lab **Environment Details** Tab.

2. From the **All services** blade, search for and select **Key vaults**, then select **+ Create**.

3. Configure the key vault. Leave the defaults for everything else.

    | Setting | Value | 
    | --- | --- |
    | Subscription | **Use your subscription** |
    | Resource group | **myRGKV-<inject key="DeploymentID" enableCopy="false" />** (use existing) |
    | Key vault name | **keyvaulttest<inject key="DeploymentID" enableCopy="false" />** |
    | Location | **East US** |
    | Pricing tier | **Standard** |
    | | |

4. Click **Review + create**, and then click **Create**. 

5. Once the new key vault is provisioned, click **Go to resource**. Or you can locate your new key vault by searching for it. 

6. Click on the key vault **Overview** tab and take note of the **Vault URI**. Applications that use your vault through the REST API will need this URI.

7. Take a moment to browse through some of the other key vault options. Under **Settings** review **Keys**, **Secrets**, **Certificates**, **Access Policies**, **Firewalls and virtual networks**.

    **Note**: Your Azure account is the only one authorized to perform operations on this new vault. You can modify this if you wish in the **Settings** and then the **Access policies** section.

# Task 2: Add a secret to the Key Vault
        
In this task, we will add a password to the key vault. 

1. Under **Objects** click **Secrets**, then click **+ Generate/Import**.

2. Configure the secret. Leave the other values at their defaults. Notice you can set an activation and expiration date. Notice you can also disable the secret.

    | Setting | Value | 
    | --- | --- |
    | Upload options | **Manual** |
    | Name | **ExamplePassword** |
    | Value | **hVFkk96** |
    | | |

3. Click **Create**.

4. Once the secret has been successfully created, click on the **ExamplePassword**, and note it has a status of **Enabled**

5. Click the current version, and note the **Secret Identifier**. This is the URL value that you can now use with applications. It provides a centrally managed and securely stored password.

6. Click the button **Show Secret Value**, to display the password you specified earlier.

Congratulations! You have created an Azure Key Vault and then created a password secret in that key vault, providing a securely stored, centrally managed password for use with applications.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Click the (...) icon located at the upper right corner of the lab guide section and navigate to the Lab Validation Page.
> - Hit the Validate button for the corresponding task.If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

 Select the **Resources** tab, then in actions select deallocate to deallocate the VM, it will be Cost effective
