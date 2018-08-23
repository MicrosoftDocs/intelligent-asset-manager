# Intelligent Asset Manager

Intelligent Asset Manager (IAM) is Microsoft's next-generation platform for Software Asset Management. IAM helps organizations make good technology decisions by maintaining a quality inventory of software products in use, and ensuring this inventory can be used for technology decision modeling.

IAM consists of the following components:

- **[Universal Inventory](universal-inventory/what-is-universal-inventory.md)** (UI) is a free application you can install on-premise to gather and process data about the entire IT infrastructure. UI does not scan the IT infrastructure, but integrates with existing solutions to import data from sources such as the Active Directory, well-known discovery tools, asset management solutions, virtualization systems, and cloud subscriptions, and stores the consolidated inventory in a database on-premise.  

  [Download Universal Inventory](https://aka.ms/downloadui)

- **IAM Cloud** is a cloud service hosted by Microsoft. Data stored in UI can -but does not have to- be uploaded to IAM Cloud to produce the Microsoft-certified Effective Deployment Position (EDP) and Effective License Position (ELP).  
  
  At this moment only Microsoft SAM Partners have access to IAM Cloud.

# Introduction: IAM Data Flow

The data flow within IAM by SAM workflow is displayed in the picture below. It is critical to understand:

1. Only Microsoft software inventory data is sent to the IAM Cloud, therefore, to Microsoft. While solely using UI no customer data is shared with Microsoft.
1. IAM includes security measures to help protect the data and privacy of Customers and their employees. Details of this can be found in the [IAM Data Usage and Privacy Information](https://aka.ms/iamdatausage)  document.

![IAM Data Flow](media/IAM_Data_Flow.jpg)

## Getting Started with IAM

- Learn more about what is the  [**Universal Inventory**](Overview/UI.md) and how it works.  
- Learn more about what is the [**IAM Cloud**](Overview/IAMCloud.md) and how it works.
- Get to know all about the Key IAM Users and Stakeholders.
- Identify which User category you are a part of and follow the correspondent Quickstart and Tutorial guides to learn how to use all IAM apps and features.