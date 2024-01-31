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

### 1. Create Azure SQL Database 
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

#### Load data to **quickkart** database
1. In the pane on the left side, in the top section, select **Query editor (preview)**.
1. Login to database, use username and passwoord provided in the previous step.
1. In **Query editor (preview)**, Copy the following query and paste inside the **query1** then select **Run**.
![Run-Query](media/run-query-sql-db.png)

```
create table Product
(
ProductID int identity primary key,
ProductName varchar(50),
ProductPrice numeric(10),
Vendor varchar(50),
Discount int,
ProductImage varchar(1000)
)
GO

insert into Product values('Sony Camera',20000,'Sony India',10,'Point_and_shoot_cameras.jpg')
insert into Product values('Samsung TV',34000,'Samsung India',20,'TV.jpg')
insert into Product values('Apple watch',30000,'Apple India',12,'watch.jpg')
insert into Product values('TMC Protien',4000,'TMC India',15,'supplement.jpg')
insert into Product values('US Polo Shirt',2500,'US Polo India',17,'shirt.jpg')
insert into Product values('Aviator Eye glass',1000,'Aviator India',20,'eyewear.gif')
insert into Product values('Spyker Jeans',2000,'Spyker India',50,'jeans.jpg')
insert into Product values('Jumpsuit',500,'Rst India',20,'jumpsuits.gifs')
GO

create table Customers
(
customerID int identity(1000,1) primary key,
emailID   varchar(50) unique,
FirstName varchar(50),
LastName  varchar(50),
Pincode   numeric(6),
[password] varchar(50),
userType char(1)
)
GO

insert into Customers values('customer1@cloudthat.com','Aplha','User',231216,'cust@1234','c')
Go

create table Subscribers
(
subscriberID int identity primary key,
emailID varchar(100) unique
)
GO

create table Vendors
(
vendorID   int   identity primary key,
vendorName varchar(200),
vendorEmailID  varchar(200),
vendorPassword varchar(200),
customerType char(1) default 'v'
)
GO

insert into vendors(vendorName,vendorEmailID,vendorPassword) values('Reebok','Rebok@quickcart.com','Kmail@1234')
insert into vendors values('Adidas','Adidas@quickcart.com','Kmail@1234')
insert into vendors values('Apple','Apple@quickcart.com','Kmail@1234')
insert into vendors values('Oneplus','Oneplus@quickcart.com','Kmail@1234')
GO

create table orders
(
orderid int identity(1,1) primary key,
custEmail varchar(50) references Customers(emailID),
prodID int,
prodCost int,
orderdate dateTime default getDate()
)
GO

```

<hr>

### 2. Create Azure Blob Storage

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

#### Upload Bolb to Azure Storage Blob Container

1. Download the all file from [assets](../assets) folder and save it on your computer (you can save it in any folder - you'll upload it to blob storage later).
1. To allow anonymous access for a storage account in the Azure portal, follow these steps:
   - Navigate to your storage account in the Azure portal.
   - Locate the **Configuration** setting under **Settings**.
   - Set Allow Blob anonymous access to **Enabled** .
1. Select **Containers** in the **Data storage** section.
1. In the **Containers** page, select **&#65291; Container** and add a new container named **products** with a public access level of **Blob (anonymous read access for blobs only)**.
   ![Create container text](media/create-container.png)
1. When the **products** container has been created, verify that it's listed in the **Containers** page.
1. In the pane on the left side, in the top section, select **Storage browser**.
1. In the storage browser page, select **Blob containers** and then select the listed **products** container.

1. Use the **&#10514; Upload** button to open the **Upload blob** panel.
1. In the **Upload blob** panel, select the all files you saved on your local computer previously. 
1. Select the **Upload** button.
1. Close the **Upload blob** panel if it's still open, and verify that **products** container contains all the files you uploaded.
1. In **Security + networking** section, select **Acccess Keys**.
1. In the **Access Keys** page, for **key1** select **show** for **Connection string** and copy the connection string and paste it in the notepad.