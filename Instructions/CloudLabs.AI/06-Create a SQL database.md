
# 06 - Create a SQL database

In this walkthrough, we will create a SQL database in Azure and then query the data in that database.

# Task 1: Create the database

In this task, we will create a SQL database based on the AdventureWorksLT sample database. 

1. Click on the Azure Portal icon on the VM desktop and login with the Azure credentials from the Lab Environment output page.

2. From the **Search resources, services, and docs** blade, search for and select **SQL databases**, and then click **+ Create**. 

3. On the **Basics** tab, fill in this information.  

    | Setting | Value | 
    | --- | --- |
    | Subscription | **Choose your subscription** |
    | Resource group | **myRGDb-<inject key="DeploymentID" enableCopy="false"/>** (use existing) |
    | Database name| **db1** | 
    | | |


4. Next to the **Server** drop down list, click **Create new**. Click **OK** when finished.          

    | Setting | Value | 
    | --- | --- |
    | Server name | **sqlserver<inject key="DeploymentID" enableCopy="false"/>** (must be unique) |
    | Location | **(US) East US** |
    | Authentication method | **Use SQL authentication** | 
    | Server admin login | **sqluser** |
    | Password | **Pa$$w0rd1234** |
    | | |

   ![Screenshot of the Server pane and the New Server pane with fields filled in as per the table and the Review + create and OK buttons highlighted.](../images/0501.png)

5. Move to the **Networking** tab and configure the following settings (leave others with their defaults) 

    | Setting | Value | 
    | --- | --- |
    | Connectivity method | **Public endpoint** |    
    | Allow Azure services and resources to access this server | **Yes** |
    | Add current client IP address | **No** |
    | | |
    
   ![Screenshot of the Networking tab of the Create SQL Database blade with settings selected as per the table and the Review + create button highlighted.](../images/0501b.png)

5. On the **Security** tab. 
 
    | Setting | Value | 
    | --- | --- |
    | Enable Microsoft Defender for SQL| **Not now** |

6. Move to the **Additional settings** tab. We will be using the AdventureWorksLT sample database, if pop-up comes, click on **OK**.

    | Setting | Value | 
    | --- | --- |
    | Use existing data | **Sample** |
    | | |

    ![Screenshot of the Additional settings tab of the Create SQL Database blade with settings selected as per the table and the Review + create button highlighted.](../images/0501c.png)

7. Click **Review + create** and then click **Create** to deploy and provision the resource group, server, and database. It can take approx. 2 to 5 minutes to deploy.

8. Go to the resource tab to locate the SQL database you created. You may need to refresh.

# Task 2: Test the database.

In this task, we will configure the SQL server and run a SQL query. 

1. From the **Search resources, services, and docs** blade, search and select **SQL databases** and ensure your new database was created. You may need to **Refresh** the page.

    ![Screenshot of the SQL database and server that have just been deployed.](../images/0502.png)

2. Click the **db1** entry representing the SQL database you created, and then click **Query editor (preview)**.

3. Login as **sqluser** with the password **Pa$$w0rd1234**.

4.  If you are not able to login. 

    ![Screenshot of the Query Editor login page with IP address error.](../images/0503.png)
    
    **Note:** If you are able to login proceed with step 9.

5. From the **db1** blade, click **Overview**. 

    ![Screenshot of the SQL server page.](../images/0504.png)

6. From the SQL server **Overview** blade, click **Set server firewall**.

7. Scroll down to the Firewall rules section and click on **+ Add your client IPv4 address**. Be sure to **Save** your changes. 

    ![Screenshot of the SQL server firewall settings page with the new IP rule highlighted.](../images/az-900mod-6img-2.png)

8. Return to your SQL database and the **Query Editor (Preview)** login page. Try to login again as **sqluser** with the password **Pa$$w0rd1234**. This time you should succeed. Note that it may take a couple of minutes for the new firewall rule to be deployed. 

9. Once you log in successfully the query pane appears, enter the following query into the editor pane.

    ```
    SELECT TOP 20 pc.Name as CategoryName, p.name as ProductName
    FROM SalesLT.ProductCategory pc
    JOIN SalesLT.Product p
    ON pc.productcategoryid = p.productcategoryid;
    ```

    ![Screenshot of the Query editor with the query pane and the commands executing successfully.](../images/0507.png)

10. Click **Run**, and then review the query results in the **Results** pane. The query should run successfully.

    ![Screenshot of the database Query Editor pane with the SQL code having been run successfully and the output visible in the results pane.](../images/0508.png)

   > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
   > - Click the (...) icon located at the upper right corner of the lab guide section and navigate to the Lab Validation Page.
   > - Hit the Validate button for the corresponding task.If you receive a success message, you can proceed to the next task. 
   > - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
   > - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

11. Select the **Resources** tab, then in actions select deallocate for deallocated the VM, it will be Cost effective.
