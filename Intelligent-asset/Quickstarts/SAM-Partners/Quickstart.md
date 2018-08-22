# Introductory Information

This user guide explains the steps and process for using Intelligent Asset Manager 2018 (IAM 2018). It is a living document. As new features become available they will be added.

## 1.1  About Intelligent Asset Manager 2018

Intelligent Asset Manager is designed to help streamline the conversion of raw data from inventory tools into usable and required formats to complete an MS SAM Engagement, and deliver value to the customer from the rich data provided that will enable them to fully understand their IT environment and make key technology and business decisions as a result.  

As the partner working with the customer, you are ultimately responsible for reviewing and ensuring completeness and accuracy of engagements, including all data entered into and reported out from Intelligent Asset Manager before it is provided to a customer.

Intelligent Asset Manager 2018 is a combination of the Universal Inventory system and the IAM Platform. It will be used as a key component of several programs at Microsoft, including Software Asset Management (SAM).

**Universal Inventory (UI):** Windows Desktop Application will convert raw inventory data into a standardized inventory document, with information that can be used for assessment and planning.  
**IAM Encryption/Decryption tool:** This application is a separate component of installed along with Universal Inventory and ensures data that could potentially contain any Personally Identifiable Information (PII) is encrypted prior to transmission to Microsoft.  
**Intelligent Asset Manager Cloud (IAM Cloud):** Web application designed to refine and finalize EDPs, and create ELPs, and where Engagement administration activities occur.

## 1.2  How does this guide work?

This guide is intended to be workflow sequenced in a way that largely follows the end-to-end steps required of a SAM Partner to complete a SAM Engagement in partnership with the Microsoft SAM EM.  
In addition to this guide, there are videos available that contain detailed overviews and demos of IAM features:

| **IAM 2018 Steps** | **Topic**                                         | **Training Session Video Link**|
|----------------|-------------------------------------------------|-----------------------------|
| Step 1         | **Best Practices for Quality Inventory Collection** | [https://aka.ms/IAMSession1](https://aka.ms/IAMSession1)  |
| Step 1         | **Installing Universal Inventory**                  | [https://aka.ms/IAMSession2](https://aka.ms/IAMSession2)  |
| Step 1         | **Creating a CIDC Using Universal Inventory**       | [https://aka.ms/IAMSession3](https://aka.ms/IAMSession3)  |
| Steps 2 and 3  |**End-to-end Engagement using the IAM Platform**     | [https://aka.ms/IAMSession4](https://aka.ms/IAMSession4)  |

## 1.3 Intelligent Asset Manager 2018 Workflow Overview

Here are the high-level Partner steps that make up IAM 2018 end-to-end Engagement com.

1. Determine whether the Engagement will require an Effective Licensing Position (ELP) document. If yes, will it be created using Microsoft’s Centralized ELP Service or self-created.
1. Provide a copy of the signed Letter of Engagement to the Microsoft SAM Engagement Manager.
1. Collect Customer Engagement consent through the IAM Tool.
1. Start working with Customer on inventory data collection
1. Load inventory data and create a Clean Inventory Data Contract (CIDC).
1. Encrypt the CIDC.
1. Upload an encrypted CIDC into the IAM Cloud.
1. Complete an Established Deployment Position (EDP).
1. *(Optional step)* Complete an ELP.
1. *(Optional step)* Use CIDC to gain Value reporting from integrated offerings.

## 1.4 IAM Cloud Requirements

- Microsoft Excel 2007 or higher
- Connection to the internet
- Have a Microsoft Account with access to Intelligent Asset Manager

Note: For provisioning to IAM Cloud, please see the last “Administrative” section of this guide for more information.

## 1.5 Universal Inventory Requirements

- Have a service account available (instructions on how to create it is included on this Guide)
- Have a SQL Server 2014 or later, Express Edition or higher database server available.

## 1.6 IAM 2018 Support

All technical support issues should be directed to IAMSupport@microsoft.com  
The following overview summarizes IAMs support standards:

![IAM Support Standards](media/IAM_support_standards.jpg)

Microsoft requires written consent directly from the customer before any decrypted PII is accepted.  
The SAM Engagement Manager will work with the customer to ensure all Microsoft policies and procedures are met for sharing and sending PII.