# Microsoft SAM - Universal Inventory

Universal Inventory (UI) is Microsoft's next-generation tool for inventory collection in support of Software Asset Management. UI is a component of Microsoft Intelligent Asset Manager 2018 (IAM 2018), Microsoft's platform for managing and leveraging SAM engagements. IAM 2018 supports our Program goals of helping our Customers make good technology decisions by:

1. Ensuring a quality inventory of Microsoft products in use, is acquired during engagements, and
2. Ensuring this quality inventory can be used for technology decision modeling.

UI enables Partners to automate, standardize, and secure data collection by integrating with several well-known inventory collection tools in the market. UI also enables the standardized inventory to be reused in market-ready Value tools from ISVs for use in Value Engagements.

UI is the result of Microsoft's collaboration with service vendors in several fields (ISV). This site explains how Inventory Providers and Inventory Consumers can integrate theis solution with UI.

**ISV Partner, to be onboarded in the Universal Inventory tool, please:**

1. Ensure your personnel has the required technical skills:
   - Microsoft SQL Server: connect to a SQL Server database, and query or fill the database using T-SQL, the query language used in SQL Server.
   - A solid technical background of your solution.
2. Read [I-AM UI Overview](I-AM_UI_Overview.md) to get a helicopter-view of Universal Inventory (UI) and Intelligent Asset Manager (I-AM).
3. Read [UI Data Model](UI_Data_Model.md)​ to understand how data in the inventory is organized.​

​Next,

**If you are an ISV that will <ins>provide</ins> inventory data to UI (Inventory Provider), you should build a connector that pushes data into the Universal Inventory:**

1. Make sure you understand the [Input schema](The_Input_Schema.md), and how a [Push Connector](Push_Connectors.md)​ works.
2. Download and the latest version of the [UI database template](https://microsoft.sharepoint.com/:u:/r/teams/MS_SAM_UI/Shared%20Documents/UniversalInventory.bacpac?csf=1&e=fA9rVK). Select "Import Data-tier Application" from the Databases context menu in SQL Management Studio and follow the wizard.
3. Read about [DataSourceId](The_Input_Schema.md#DataSourceId), and send a proposed DataSourceId​ for your Connector to SAM-UI@microsoft.com.
4. Build a Push Connector and use it to fill the UI database with the data scanned through your inventory tool/service.
5. Send a backup of the filled database to SAM-UI@microsoft.com.
6. We will process the database against ​UI quality standards and provide feedback to fine-tune your Connector.

**If you are an ISV that will <ins>consume</ins> inventory data from UI in your value Tool (Inventory Consumer), please contact SAM-UI@microsoft.com outlining which of the options of the 4 topics below best suits your plan and solution. We will then proceed to give you more information about the integration.**

1. What is the format you need to consume UI data:  

   **Option 1)** Microsoft Excel: UI creates an Excel file filled with the data you need.  

   **Option 2)** SQL backup: UI creates a database filled with the data you need, and creates a backup copy of that database to file.  

   **Option 3)** Json: UI creates a (collection of) json objects filled with the data you need.  

   Other formats can be discussed, but building them will require more time as we have to include the implementation in our planning.
1. What export type you seek to implement when the user chooses within UI to share data with your solution:

   **Option 1)** UI can save the corresponding file (Excel, SQL backup, or json) to the user’s local disk:  

     You provide a web portal or mailbox where the user can manually upload    this file.  

    In this case, acquiring consent to see the user’s data is handled exclusively between you and the user, since UI does not export any data directly. We just prepare it for the user in the required format.  

    **Option 2)** UI can export the data directly to your web service:  
  
    You provide a web service where UI posts the data in json format, or uploads the prepared file (Excel, SQL backup, or json). We need to understand the requirements of the web service. E.g. whether the data can be uploaded in a single collection, in batches, or record by record, how we have to authenticate to use your service, and if/how the UI user can register for your service  

    In this case, the user needs to provide consent through UI, since we export the data directly to your service. We need to agree on the consent process.
1. Would you like to receive data?  

   **Option 1)** Anonymized - PII like device names, user names, mailbox addresses, and other will be anonymized before being exported.  

   **Option 2)** In clear text.
1. What is the schema and content you require to receive UI data?  

   In other words, you need to tell us which subset of the data points available in UI you want to receive, and how it should be organized. We need to know which filters to apply to the available data. To know what data points are available on UI, please download the [UI Database Template](https://microsoft.sharepoint.com/:u:/r/teams/MS_SAM_UI/Shared%20Documents/UniversalInventory.bacpac?csf=1&e=fA9rVK).

   In the case of an export in MS Excel format, we need to know which worksheets and columns to create.  
   In the case of an export to SQL backup, we need to know which tables and fields to create.  
   In the case of an export to json, we need to know which objects and collections to create.

   We will then work together to (as much as possible) make sure we can provide you a database in a format that your tool can support.

____

Universal Inventory is work in progress. T​here will be regular updates to the data model and the data flow. We will keep you informed on the updates through the SAM-UI Communication alias, but please check back here for the latest changes before working on the integration of your solution. You can also follow the instructions on the [UI ISV Onboarding Guide​](https://aka.ms/iamisvguide) ​to set up automatic e-mail notifications for when there are updates on our Wiki Pages.

We would like to thank all our partners for their generous contribution to this exciting initiative. Send all your inquiries, proposals and remarks to
SAM-UI@microsoft.com​​.

The Microsoft SAM Intelligent Asset Manager 2018 and Universal Inventory Team  
SAM-UI@microsoft.com

AKA&#46;MS/SAMIAM