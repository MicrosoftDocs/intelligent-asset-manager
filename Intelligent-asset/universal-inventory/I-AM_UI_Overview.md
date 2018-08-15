# Intelligent Asset Manager (I-AM) - Universal Inventory (UI) Overview

## Components

The Universal Inventory consists of 3 components:

- A **Windows Service** that does the work of collecting data and maintaining the data store.

- A **Client** application to manage the Windows Service and produce output.

- The **Data Store** holding the inventory data.

Unlike its predecessor, UI maintains the inventory in a database controlled by the Customer that can be used to provide value services. Every time the user creates a *Project* in UI, a new inventory database is created.

All components can be installed on a single device. SAM consultants might want to install all components on their laptop, creating new projects for each customer engagement. Enterprises with large infrastructures may want to install the UI Service in their datacenter, the Client on an administrator's desktop, and the Data Store on a dedicated database server.

![UI Overview ](media/I-AM_UI_Overview.PNG)

UI does not scan or collect any data from devices. Instead it connects to existing sources of data such using *Connectors*.

## Connectors

A *Connector* imports data from a specific source into the inventory. Connectors are implemented as scripts so they can easily be reviewed by the customer, or customized for a specific infrastructure.

Two types of connectors exist:

- **Pull** connectors pull information from a data source. They are managed and executed by UI.  
  Pull connectors currently exist for Active Directory, MapToolkit, Office 365, SCCM, and vSphere.

- **Push** connectors are built by 3rd party providers. They are executed through the tool of the vendor, and push data directly into the Universal Inventory data store.

[Read here how to create a Push Connector](Push_Connectors.md)

## Output

The Universal Inventory can be consulted in the following ways:

- Through the **Dashboard**, a set of customizable reports.

- By the **ELP Service** provided by Microsoft to generate a validated License Position based on your inventory.

- By providers of **Value Services**