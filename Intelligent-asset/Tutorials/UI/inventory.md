---
title: Creating Universal Inventory
---
# Tutorial: Creating an inventory with Universal Inventory

After Universal Inventory is [**installed**](installation.md) and you learnt about the [**Best Practices for Quality Inventory**](quality.md), follow these steps to create an inventory of the infrastructure:

> [!TIP]
> If you prefer a video guided training for learning how to create the standard inventory document (CIDC) using UI, you can also watch the [IAM 2018 Session 3: Creating a CIDC Using Universal Inventory](https://aka.ms/IAMSession3).

## Creating a Universal Inventory

The Clean Inventory Data Contract (CIDC) is an Excel report used as the required template to pull in and consolidate raw inventory data from the various inventory and discovery tools, de-duplicated, and formatted to work with the main IAM site. Some manual usage and license allocation inputs will also be required to complete the CIDC. Once uploaded, the CIDC is validated against business rules to ensure proper data collection. If the CIDC fails validation a CIDC Error report detailing what needs to be fixed will be created.

![CIDC Error Report on IAM Cloud](media/CIDC-Error-Report-screenshot.jpg)

## Creating a New Project

1.. On the Customer’s machine, open the Universal Inventory client application that was just created. It will launch with a standard blank screen because no Projects are defined yet. With this solution the Customer can create multiple projects for themselves, UI can be a component to be used without any specific Microsoft Engagement running.

   ![UI Client App Universal Inventory](media/UI-Client-App-screenshot.jpg)

1. Click on “New Project”, type in the Project name (a valid project name consists of alphanumeric characters and spaces only, and is between 3 and 64 characters long) and click on “Save” button. The system will create the Project database, taking into account the data stored in UI database as a starting point. You know the Project was created successfully when you see a *project card* displayingd the status of the project and last update time.  

   ![UI Client App New Project Universal Inventory](media/UI-Client-App-New-Project.jpg)

>[!TIP]
>Many projects can be created in Universal Inventory. Every Project corresponds with an *inventory*, and can have many *data sources*. An organization with a complex infrastructure may consider creating a test project to validate correctness and verify data source availability, before creating a production project to be shared with value providers. SAM Partners may create a project for each customer, provided customers consent to their data being stored on the consultant's machine.  

1. Click on “Open Project” and you will see standard interface with the Actions and Reports that can be performed through UI.

   ![UI Client App Open Project Universal Inventory](media/UI-Client-App-Open-Project.jpg)

## Gathering Inventory Data Sources

1. Click on “Gather” to configure the data sources that need to be configured for this Engagement. *Data source not found* will be displayed the first time the Gather screen is opened for a project. To add new data sources for an Engagement you currently have to options:
    - Use a “Pull Connector” to reach out to the data sources maintained by Microsoft (Active Directory, MAP Toolkit, SCCM 2012 and/or vMWare vCenter (Office 365 will be added shortly); OR
    - Use to “Push Connectors” to automatically push the data scanned through the Inventory Tools/Services from the UI-integrated Vendors (ISVs).

1. For the first option of a “Pull Connector”, click on “Add” button and choose which data source is preferred from the available list of UI connectors on the right.

   ![UI Client App Pull Connector Universal Inventory](media/UI-Client-App-Pull-Connector.jpg)

3. Scroll through the list of available connectors and click **Add** on the appropriate connector. Depending on the type of connector selected, an **Add data source** dialog will show up allowing you to enter the parameters required to connect to the data source.  
  
4. Click **Add** in the Add data source dialog. The data source configuration is saved and a *data source card* displays the status of the data source and last update time.

5. To import data from the data source into the inventory, click the cog wheel on the data source card and select **Run** from the dropdown-menu. The status of the data source will change to *Running*. After the import is completed, the status changes to *Complete*.  

>[!TIP]
> If the data source status is *Failed* or *Partial*, open the log file to troubleshoot. The log file is in the Work Folder you specified during installation. If the information in the log file does not allow you to solve the issue, turn to [IAM Support](../../Sup_Comm.md) for help.

## Pull Connector: MAP Toolkit example

1. In this guide we will showcase in more detail the process for adding a MAP Toolkit integration as a data source, so click on “Add” under the MAP Toolkit option. Type the Sever name that contains the MAP data base instance and select the type of Authentication. Then, click on the blue Refresh button and the system will update with all Database names contained in this server under the “Database” drop-down menu. Select the preferred one. As an option, you can also define the “Tenant/Site” name. Click on “Add”.

   ![UI Client App MAP Toolkit Universal Inventory](media/UI-Client-App-MAP-Toolkit.jpg)

>[!TIP]
> The **Tenant/Site** field is optional but  useful when more than one MAP database is included, so that later reports can be run for a specific Tenant from a MAP database. At a later stage this field allows you to limit data in reports. E.g. geographically dispersed organizations might specify a site name to be able to only report on data from a specific site. Internet providers might specify a tenant name to be able to only report on data from a specific tenant. Multiple data sources can have the same Tenant/Site value.  

> [!IMPORTANT]
> Remember that Universal Inventory runs as Windows service. When you select 'Windows Integrated' authentication, it will not be the current user that connects to the data source to import data, but the [Service Account](preparation.md#prepare-a-local-user-account-as-service-account) of the Universal Inventory service.

2. A “Pull” connection will be created. Click on “Run” to pull the database from this source, you will see the status change to “Complete” in green, which means this selected environment was scanned and pulled into UI.

   ![UI Client App Pull Connection Created](media/UI-Client-App-Pull-Connection-Created.jpg)
   ![UI Client App Pull Connection Run](media/UI-Client-App-Pull-Connection-Run.jpg)

## Push Connectors: LanSweeper example

1. In case you wish to add a “Push Connector”, within this guide we will show you an example of how that can work through the LanSweeper UI-integrated application since they were one of our first Tool Partner to integrate with UI. When the LanSweeper application is ran, the start screen shows an option to Export the inventory to Universal Inventory.

   ![Export to UI Universal Inventory](media/Export-to-UI-screenshot.jpg)

1. Fill out the information related to your Universal Inventory server created and follow the steps within their application. The correct “Connect to Universal Inventory” Database name to be used is displayed on the Project Dashboard (see example below). Also, the Datasource ID should be provided by Lansweeper. Click on “Connect” and then on “Start” and the Push connector will start working to push your Lansweeper scanned data into your Project created within UI.

   ![UI Server Information Universal Inventory](media/UI-Server-Information.jpg)
   ![Push Connector Start Universal Inventory](media/Push-Connector-Start.jpg)

1. Once the export is completed it will be communicated through a pop-up window and you can finalize this process by clicking on “Ok”.

## Verifying Devices Scanned

1. Go back to the Project dashboard and this time select “Verify” to check a list of information about the devices scanned through the added data source.

   ![UI Client App Project Verify Universal Inventory](media/UI-Client-App-Project-Verify.jpg)

1. At the Verify tab, you will notice some options available for checking the database imported. On the “Column” filter, you can select which columns you would like to see on the report. To exclude certain parameters on both Devices and/or Users from your final CIDC file, select the row by clicking on the blue “Checkmark” on the left portion of the and then click on “Exclude” under the “Action” drop-down.

   ![UI Client App Exclude DB Row Universal Inventory](media/UI-Client-App-Exclude-DB-Row.jpg)

1. To verify Push Connectors data available on your UI Project, go back to “Gather” option on the initial Project dashboard and verify that the “Push” inventory is available.

   ![Verify Push Inventory Universal Inventory](media/Verify-Push-Inventory.jpg)

   >[!IMPORTANT]
    >If you see that any of the data sources included on your Project contain “Import Warnings” in yellow, it means that your data is missing important data points that will ensure a minimum quality standard on your CIDC. Click on the yellow message to read more information about which data is missing. Make sure that data is corrected before creating your CIDC so that you comply to these minimum standards recommended by Microsoft.

## Refinement and Data Normalization

1. Once you have finalized pushing and pulling from all the data sources you used to scan your Customer’s environment, you can verify all the data included in UI through the 3 different Reports available on the Project dashboard. Once you are certain that the data from the Push and Pull connectors are correct and all the right Devices and Users are available, you should proceed to the Refinement step, accessed through the “Refine” button on the Project dashboard.

   ![Refinement Step Universal Inventory UI](media/Refinement-Step-screenshot.jpg)

 >[!IMPORTANT]
>Refinement step, also known as “normalization”, de-duplicates and normalizes product naming from the various disparate inventory data collection solutions. Inventory collection tools contain their own product naming standards, and in order to have one single inventory format standard, refinement merges these into a single, standardized universal dataset that is easily to understand. 
For IAM , Microsoft is partnering with leading SAM Tools providers who have demonstrated best practices within their refinement/normalization solutions to offer no cost services for Engagements being processed through IAM. Refinement service offerings will expand over time. Refinement service providers may have their own set of Terms and Conditions for users.

   The IAM launch partner for Refinement is Snow Software. To learn more about Snow’s normalization solution, [click here](https://www.snowsoftware.com/int/solutions/data-normalization-cleansing-0).

   During refinement, a very limited amount of data collecting during inventory gathering is shared. Data fields that could contain Personally Identifiable Information (PII) are not transmitted. This table contains the data sent during refinement:

   | Data send for refinement | Example of data                  |
   |:--------------------------:|:----------------------------------:|
   | Software vendor          | Microsoft Corporation            |
   | Application path         | c:\program files\test\office.exe |
   | Application name         | Office 2013 Professional         |
   | File size                | 12000 mbs                        |

2. Click on “Refine” under the Snow service that is shown as available.

    ![Snow Service Normalization Universal Inventory UI](media/Snow-Service-screenshot.jpg)

1. Because it’s a no-cost service, you will need only at the first time do a short registration at Snow’s application. Click on “Sign up with Microsoft” and you will be requested to sign up with your Microsoft Work or School Account (Office 365 or Azure). You will then be redirected to a screen to type your Account and Password and then click on “Sign in”.

   ![Snow Service Registration normalization](media/Snow-Service-Registration.jpg)

1. The next screen will request your consent to forward your UI identity to Snow Software on the normalization App that you will be using. Read the terms on the window and click on “Accept”. You will then see that the UI application has been granted the necessary rights within the Snow’s normalization application and click on the green big “checkmark”.

   ![Snow Service Request Consent normalization](media/Snow-Service-Request-Consent.jpg)
   ![Snow Service Authorize App normalization](media/Snow-Service-Authorize-App.jpg)

1. Fill out a quick registration regarding your Customer and click on “Submit”. Read the Snow’s End-User License Agreement and click on “Accept” to finalize the set-up for the normalization service from Snow.

    ![Snow Service Customer Registration](media/Snow-Service-Customer-Registration.jpg)

    ![Snow Service License Agreement](media/Snow-Service-Agreement.jpg)

1. When the refinement is finalized by Snow’s application, a data timestamp will show on the box, as well as the green “Completed” note. 

>[!NOTE]
 > When you have products that are not recognized immediately by Snow, those are processed by Snow’s normalization team and made available on the UI app within the next 24 hours.

20. To check on the normalization work that has been completed, go back to the main Project dashboard and click on “Summary”. On the report, you will see the “Distinct software titles and versions” as the total count within the raw data and “Normalized software titles” with the total count after the normalization process.  

> [!TIP]
> You can also see the reports “Devices” and “Users” for more detailed information about them.

   ![Summary Report Universal Inventory UI](media/Summary-Report-screenshot.jpg)

## Exporting the Standardized Universal Inventory document
From this point on, you should perform the action of exporting your Universal Inventory standardized document based on what this inventory will be used for. 
If it will be used as an input into one of our Value Providers (ISVs with a SAM/value/analysis tool integrated with UI), you will find the icon of their solution on the "Export" tab and will be able to export the file in the right format for that specific solution by clicking on "Export".

If you are running UI to be used in a Microsoft SAM Engagement with a SAM Partner, you should follow the steps below on how to created a UI Clean Inventory Data Contract (CIDC), which will contain Microsoft licensing deployment data only, since it is the only data provided to Microsoft during a SAM Engagement.  

## Creating UI Clean Inventory Data Contract (CIDC) for a SAM Engagement
1. To finalize your inventory collection for a Microsoft SAM Engagement, you need to create the Universal Inventory CIDC. Click on the “Export” button on the Project dashboard and you will see the option to create a Microsoft CIDC. The system will then build the CIDC file and prompt you to select a location for it to be stored. 

> [!IMPORTANT]
> Only Microsoft-related licenses will be exported to this CIDC file. It is the same file that will later be encrypted and uploaded into the IAM platform to finalize your Microsoft SAM Engagement.

   ![Microsoft CIDC Create Universal Inventory UI](media/Microsoft-CIDC-Create.jpg)
   ![Microsoft CIDC File Location Universal Inventory UI](media/Microsoft-CIDC-File-Location.jpg)

2. If any of your data sources are missing important data, on this screen you will find an error messages with some information about the missing data. If you click on the “Description” for each item, you will see a list of the Devices that contain that specific error. These are important indicators that your inventory is not following the minimum data quality requirements that Microsoft recommends, so it is especially important that you fix them before moving forward with your CIDC creation.

   ![Error Messages Universal Inventory UI](media/Error-Messages-screenshot.jpg)
   ![List Devices With Error Universal Inventory UI](media/List-Devices-With-Error.jpg)

## CIDC Encryption/Decryption - for Microsoft SAM Engagements only

1. Once you find that your CIDC has sufficient data quality and is ready to be included by your SAM Partner on [IAM Cloud](../../Overview/IAMCloud.md) fore[ Efffective Deployment Position (EDP)](../SAM-Partners/EDP.md) and/or e[Effective Licensing Position (ELP)](../SAM-Partners/ELP.md) creation, you should open the IAM Encryption/Decryption tool that was installed along with UI_Setup to encrypt your CIDC data. Launch the tool and fill in the “Source CIDC File” by browsing your document on the location it was saved. Then you will have to determine a Password for your CIDC, so the data will only be available for the ones that have this password. Click on “Encrypt” and the CIDC encrypted file will be created in the same folder as the source file, with the same name suffixed with “-Encrypted”.
   - Guideline for CIDC password:
        - At least 8 characters long;
        - Include 3 of the following four below:
           - Uppercase
           - Lowercase
           - Numbers
           - Symbols or Unicode characters

           ![Guideline CIDC Password for Encryption](media/Guideline-CIDC-Password.jpg)

1. If you need to decrypt your CIDC, EDP or ELP to visualize the data, on the box “Decryption”, select the Source File and type the same Password used for encryption. Select the file type in the drop-down menu and click on “Decrypt”.

   ![Decrypt CIDC Universal Inventory UI](media/Decrypt-CIDC-screenshot.jpg)

1. Additionally, going back to the Universal Inventory app, on the “Export” option in the main dashboard,you will also find other options to export, which are the UI-integrated Value tools that are provided by our Tool Vendors. Our launch partner in providing this integration is UnifyCloud with their CloudRecon Analytics service, that generated Value Engagements reports. When you click “Export”, you will download a backup of your UI database in the standardized UI format that can be uploaded into CloudRecon.  
  >[!NOTE]
  > CloudRecon licenses might be required for using this service.  
  
  > [!TIP]
  > To be able to create a Value Engagement report, CloudRecon will require a full picture of the Customer’s IT environment, not only Microsoft-related licensing information. Therefore, this CIDC downloaded will contain all manufacturers data information.

   ![CloudRecon Analytics Export Universal Inventory UI](media/CloudRecon-Analytics-Export.jpg)

 Once the CIDC is encrypted, it should be sent to your SAM Partner since it will be ready to be uploaded into the [IAM Cloud](../../Overview/IAMCloud.md) platform to run through creation of the [Established Deployment Position (EDP)](../SAM-Partners/EDP.md) and, if required, the e[Established Licensing Position (ELP)](../SAM-Partners/ELP.md).

Additionally, we suggest having a look at the UI [Release Notes](Release-notes.md) section to get familiar with the latest changes on newest versions of Universal Inventory.
