---
title: Tutorial Quality Inventory
---
# Tutorial: Best Practices for Quality Inventory Collection

Collecting complete and accurate inventory is the key to success to complete a SAM Engagement. In this section, we give some guidance on how to ensure this and meet the obligations defined in the [Value Engagements Statements Of Work (SOWs)](https://www.microsoft.com/en-us/sam/use-cases.aspx?CollectionId=9d33c0b2-7c54-4274-8b1c-d1dec3b8548d).  

> [!TIP]
> If you prefer a video guided training about the best practices for a quality inventory, you can also watch the [IAM 2018 Session 1: Best Practices for Quality Inventory Collection](https://aka.ms/IAMSession1).

Today, Customers are looking for ways to transform their business and embrace the digital era. Often, Customers have multiple data sources and use a set of individual point-solutions to manage them. Having a quality asset management discovery plan is key to the success of any Software Asset Management Engagement.  
Therefore, comprehensive data collection and an ability to create a complete and accurate Preliminary CIDC are critical for delivering the biggest value possible as the result of a SAM Engagement. A best practice suggested is that the first thing to do with the Customer is kick off meeting, which will be the most important one.  
During this meeting, partners should present the value of SAM and the process behind it. This meeting is also the time to establish an agreement on timelines and infrastructure needed to complete the Engagement. Partners should articulate which data will be extracted from Customers’ environment and why.  
Basic questions to ask during a kick-off meeting include:

- How many clients and servers are in the infrastructure?
- Do employees work remotely?
- Is there a dev environment?
- It is imperative that you learn how their infrastructure is architected, how many of their servers have been virtualized, whether they have workloads running on the cloud, and who manages it all.
- Where the Customer’s assets reside, and how you can access them.

During the data collection, if Customer is unable to provide access to certain devices, or datasets, you’ll need to investigate further. There’s a chance that these devices are compromised.  
It is a common scenario to run multiple types of data-scanning platforms, depending on what the Customer already uses and what is the Partner’s plan. It is best practice to bring in additional Customer data, like SCCM, Altiris, etc. The more datasets used, the better. However, for any option that you choose to run, we recommend running Active Directory and [MAP Toolkit](https://www.microsoft.com/en-us/download/details.aspx?id=7826) in tandem with your Customers’ asset management tools, reporting separately into Universal Inventory.  
If you opt to use [MAP Toolkit](https://www.microsoft.com/en-us/download/details.aspx?id=7826), ensure multiple runs in different moments in time multiple times a day, for a
few weeks at minimum. Focus on collecting both inventory data as well as additional performance data (this will facilitate value work). If value work will be done with the inventory data collected, we suggest having the performance counters run for 32 days for all Windows Servers. If MAP Toolkit is not run consistently, you will not get the quality data you need to execute a successful SAM Engagement.  
Finally, you will need to validate the data you collect. Some best practices are described below, they should become blocking factors that might stop you from creating a CIDC for your SAM Engagement.

- Uncover the number of physical core, processors, servers and workstations in your project scope.
- Uncover the number of virtual processors and virtual machines (VMs).
- All VMs must have an underlying physical server, so make sure all the tools you are using can provide the physical server information of virtual machines.
- Scan vCenter related data, even if this task is being executed in an outsourced environment and, after identifying this information, determine the CPU. This is critical to core-based licensing.
- For SQL server instances, it is required reference to a SQL installation.
- From physical machines and mobile devices, to hyper-visors and host-machines, make sure you have the manufacturers identified. Know that usually those should be names you can find on the internet. An indicator of incorrect and low-quality data is when a manufacturer is called “test” or a mobile “unknown”.

SAM Partners should cross check the quality points described above and review the Minimum EDP Quality Standard to see some ways Microsoft evaluates the quality of EDPs.

## Minimum EDP Quality Standard samples

| Data Standard:                                                                                         | More Detail/Examples:                                                                                                                                           |
|--------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| The EDP Data Tab should have a row for each product and version on each installed device.              | This standard leads to many data rows in the EDP. To get a basic sense of completeness, focus on Workstations - there should be 1 Workstation OS for each seat. |
| Cumulative Workstation volume should equal the approximate company workstation volume (PCs count)      | Check EDP Summary Tab for Workstation OS licenses or CIDC tab A                                                                                                 |
| Physical Core and Processor Count for physical servers and workstations must be ALWAYS greater than 0. |                                                                                                                                                                 |
| Virtual Processor Count for virtual Servers and workstations must be ALWAYS greater than 0.            |                                                                                                                                                                 |
| All Virtual hosts must have 1 underlying physical server                                               | Check the EDP 'Other Server' Worksheet for any product identified as 'unknown host' & correct as needed.                                                        |
| All devices (virtual, physical, hosted) must contain an actual Processor type                          | 'Unknown' or XXXXXXXX are not processor types. No generic character strings should be included.                                                                 |
| The data rows in SQL Instance Worksheet tab must equal the total in Summary tab.                       | CIDC tab F must contain SQL instance data.                                                                                                                      |
| All products with Royalty Free License Model must have a license count greater than 0.                 |                                                                                                                                                                 |
| Machine Manufacturer and Model must represent actual Manufacture & Model.                              | No generic character strings should be included - XXXXXXXX or 123123 are not actual mfr names.                                                                  |
## Next Step: Inventory

Now that you are familiar with the Microsoft's best practices on how to collect a quality raw inventory of the software deployed and its importance, read how to create a UI standardized inventory on the [**UI Inventory Tutorial section**](inventory.md).