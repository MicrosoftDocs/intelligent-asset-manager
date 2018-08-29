---
title: Tutorial UI ISVs
---
# Tutorial: Technical Integration Process for UI ISVs

## First Steps

After reviewing the [**Quickstart process for UI technical integration**](../../Quickstarts/ISV.md) for our [**ISVs partners**](../../Overview/key-users.md), please follow the initial steps below in order to start Universal Inventory integration of your tool:

1. Ensure your personnel has the required technical skills:
   - Microsoft SQL Server: connect to a SQL Server database, and query or fill the database using T-SQL, the query language used in SQL Server.
   - A solid technical background of your solution.
2. Read the [**UI Introduction**](../UI/introduction.md) to get familiarized with the Universal Inventory terms and main technical components.
3. Read the [**UI Data Model**](Data_Model.md)​ to understand how data in the inventory is organized.​

## ISV: Inventory Provider

If you are an ISV that will <ins>provide</ins> inventory data to UI with your scanning tool or service, you should build a connector that pushes data into the Universal Inventory application:

1. Make sure you understand the [**UI Input schema**](Input_Schema.md), and how the [**UI Push Connectors**](Push_Connectors.md)​ works.
2. Read about [**DataSourceId**](Input_Schema.md#markdown-header-dataSourceId), and send a proposed DataSourceId​ for your Connector to SAM-UI@microsoft.com for validation.
3. Download and install the latest version of [**Universal Inventory**](https://aka.ms/DownloadUI).
4. Create a test Project in UI. Look at the empty database created with SQL Management Studio. (The database name will be the name of your test project prefixed with "UI_")
5. Build a [**Push Connector**](Push_Connectors.md) and use it to fill the tables in the [in] schema of the test database with the data scanned through your inventory tool/service.
6. Send a backup of the filled database to SAM-UI@microsoft.com.
7. We will process the database against ​UI quality standards and provide feedback to fine-tune your Connector.
8. Once the fine tuning is finalized, we will confirm your tool's integration.

## ISV: Inventory Consumer

If you are an ISV that will <ins>consume</ins> inventory data from UI in your value/data analysis tool or service, please contact SAM-UI@microsoft.com outlining which of the options of the 4 topics below best suit your plan and solution. We will then proceed to give you more information about the integration.

1. What is the format and content you need to consume UI data:  

   **Option 1)** Microsoft Excel: UI creates an Excel file filled with the data you need. Which worksheets and columns do we need to create?

   **Option 2)** SQL backup: UI creates a database filled with the data you need, and creates a backup copy of that database to file. Which tables and fields do we need to create?.

   **Option 3)** Json: UI creates a (collection of) json objects filled with the data you need. Which objects and collections do we need to create?

   Other formats can be discussed, but building them will require more time as we have to include the implementation in our planning.

2. What export type you seek to implement when the user chooses within UI to share data with your solution:

   **Option 1)** UI can save the corresponding file (Excel, SQL backup, or json) to the user’s local disk:  

     You provide a web portal or mailbox where the user can manually upload    this file.  

    In this case, acquiring consent to see the user’s data is handled exclusively between you and the user, since UI does not export any data directly. We just prepare it for the user in the required format.  

    **Option 2)** UI can export the data directly to your web service:  
  
    You provide a web service where UI posts the data in json format, or uploads the prepared file (Excel, SQL backup, or json). We need to understand the requirements of the web service. E.g. whether the data can be uploaded in a single collection, in batches, or record by record, how we have to authenticate to use your service, and if/how the UI user can register for your service  

    In this case, the user needs to provide consent through UI, since we export the data directly to your service. We need to agree on the consent process.
3. Would you like to receive data?  

   **Option 1)** Anonymized - PII like device names, user names, mailbox addresses, and other will be anonymized before being exported.  

   **Option 2)** In clear text.
4. What is the schema and content you require to receive UI data?  

   You should tell us which subset of the data points available in UI you want to receive, and how it should be organized. We need to know which filters to apply to the available data. To know what data points are available on UI, please download and install the [latest version of UI](https://aka.ms/DownloadUI), create a new test project and look at the empty database created with SQL Management Studio. (The database name will be the name of your test project prefixed with "UI_")

  We will  work together to (as much as possible) make sure we can provide you a database in a format that your tool can support.

T​here might be regular updates to the Data Model and the data flow of Universal Inventory. We will keep you informed on the updates through the IAM Communication alias, but please check back here for the latest changes before working on the integration of your solution.