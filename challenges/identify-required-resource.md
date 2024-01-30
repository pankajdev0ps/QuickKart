# Challenge 2: Identify and provisioned the required Azure Resources.


> Note: Identify all the required Azure Resource but provisioned only needed one.

## Required Azure Service and Resources
- Azure SQL Database
- Azure Blob Storage
- Azure Key Valut
- Azure Web App
- Azure Static Web App
- Azure Service Bus Queue
- Azure API Management
- Azure Application Insight
- Azure Logic App


## Tasks

### Create Azure SQL Database 
1. In the Azure portal, select **＋ Create a resource** from the upper left-hand corner and search for Azure SQL. Then in the resulting **Azure SQL** page, select **Create**.

2. Review the Azure SQL options that are available, and then in the SQL databases tile, ensure **Single database** is selected and select Create.
    - **Subscription:** Select your Azure subscription.
    - **Resource group:** Create a new resource group `Quickkart-RG`
    - **Database name:** `quickkart`
    - **Server:** 
        - Select Create new and create a new server with a **unique
        name** in any available location. 
        - Use **SQL authentication** and specify `sqladmin` as the server admin login and a suitably `Pa55w.rd` password. (**remember the password** - you'll need it later!)
    - **Want to use SQL elastic pool?**: No
    - **Workload environment:** Development
    - **Compute + storage:** Select change configuration
        - **Service Tier:** Basic
        - click **Apply**
    - **Backup storage redundancy:** Locally-redundant backup storage

3. On the Create SQL Database page, select **Next :Networking >**, and on the Networking page, in the Network connectivity section, **select Public endpoint**. 

   Then **select Yes for both options** in the Firewall rules section to allow access to your database server from **Azure services** and **your current client IP address.**

4. Select **Review + Create**, and then select **Create** to create Azure SQL database.<br>

> Wait for deployment to complete. Then go to the resource that was deployed.

### Create Azure Blob Storage

1. On the Azure portal home page, select **+ Create a resource** from the upper left-hand corner and search for *Storage account*. Then in the resulting **Storage account** page, select **Create**.
1. Enter the following values on the **Create a storage account** page:
    - **Subscription**: Select your Azure subscription.
    - **Resource group**:  Select exisiting resource group `Quickkart-RG`.
    - **Storage account name**: Enter a unique name for your storage account using lower-case letters and numbers.
    - **Region**:  Select same location as Azure SQL DB `quickkart`.
    - **Performance**: *Standard*
    - **Redundancy**: *Locally-redundant storage (LRS)*

1. Select **Review**, and then select **Create** to create Azure Storage.<br>
1. Wait for deployment to complete. Then go to the resource that was deployed.