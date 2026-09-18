# Project 06 - Azure Storage

## Project Overview

In this project, I worked as a Junior Cloud Administrator for BrightPath Solutions to deploy, configure and test Azure Storage services.

The project focused on selecting appropriate storage services, securing access to storage data, protecting data from accidental deletion and modification, and managing storage efficiently.

## Scenario

BrightPath Solutions requires secure and cost-effective cloud storage for different types of business data.

As the Junior Cloud Administrator, I was responsible for configuring an Azure Storage environment that provided secure Blob storage, shared file storage, data protection, controlled access and automated lifecycle management.

## What I Implemented

- Created an Azure Storage account using Standard performance and LRS redundancy
- Configured Hot as the default Blob access tier
- Reviewed Azure Storage redundancy options including LRS, ZRS, GRS and GZRS
- Configured Blob and Container soft delete with a 7-day retention period
- Enabled Blob Versioning
- Required secure transfer and TLS 1.2
- Configured Microsoft Entra authorization as the preferred authorization method in the Azure portal
- Used Microsoft-managed keys for encryption at rest
- Created a private Blob container named `marketing-files`
- Uploaded and managed a Block Blob
- Assigned the Storage Blob Data Contributor RBAC role for data-plane access
- Tested Blob Versioning by overwriting and recovering a previous version
- Tested recovery after deleting a blob
- Generated and tested a read-only Shared Access Signature (SAS) with an expiry time
- Created an Azure Files share named `finance-share`
- Created a Lifecycle Management rule to move blobs to the Cool tier after 30 days

## Implementation Evidence

### 1. Storage Account Configuration

I created an Azure Storage account for BrightPath Solutions using **Standard performance** and **Locally Redundant Storage (LRS)**.

The storage account was configured with secure transfer, TLS 1.2, Microsoft-managed encryption keys and Hot as the default Blob access tier.

![Storage Account Overview](01-storage-account-overview.png)

### 2. Blob Container and File Upload

I created a private Blob container named `marketing-files` and configured access to the stored data using Azure RBAC.

After assigning the **Storage Blob Data Contributor** role for data-plane access, I uploaded a Block Blob to the container and verified that the file was successfully stored.

![Blob Container Upload](02-blob-container-upload.png)

### 3. Blob Versioning and Data Protection

I enabled Blob Versioning and tested the protection by overwriting an existing blob to create multiple versions.

I then tested recovery using an earlier version, demonstrating how versioning can help recover data following accidental modification or deletion.

![Blob Versioning](03-blob-versioning.png)

### 4. Lifecycle Management

I created a Lifecycle Management rule named `MoveMarketingFilesToCool` for the Blob data.

The rule was configured to automatically move base blobs to the **Cool** access tier after more than **30 days** without modification, demonstrating how storage costs can be managed automatically as data becomes less frequently accessed.

![Lifecycle Management Rule](04-lifecycle-management-rule.png)

## Key Skills Demonstrated

- Azure Storage account configuration
- Blob Storage
- Azure Files
- Storage redundancy
- Access tiers
- Microsoft Entra ID and Azure RBAC
- Management plane vs data plane permissions
- Shared Access Signatures (SAS)
- Blob soft delete and versioning
- Storage encryption
- Secure transfer and TLS
- Lifecycle Management
- Least-privilege access

## Key Learning Outcomes

This project provided hands-on experience with:

- Selecting appropriate Azure Storage services for different business requirements
- Understanding LRS, ZRS, GRS and GZRS redundancy options
- Securing Blob data using Microsoft Entra ID and Azure RBAC
- Understanding the difference between management-plane and data-plane permissions
- Using SAS for temporary delegated access
- Protecting Blob data using soft delete and versioning
- Recovering previous versions of modified data
- Configuring Azure Files for shared file storage
- Using Lifecycle Management to automatically move older data between access tiers
- Applying least-privilege principles to Azure Storage

## AZ-104 Alignment

This project supports AZ-104 skills relating to:

- Configure Azure Storage accounts
- Configure Azure Blob Storage
- Configure Azure Files
- Configure storage security and access
- Configure Azure Storage redundancy
- Manage Blob access tiers
- Configure Blob lifecycle management
- Configure data protection
- Manage access using Microsoft Entra ID, Azure RBAC and SAS

## Project Outcome

Successfully deployed and configured an Azure Storage environment for BrightPath Solutions.

The project demonstrated how Azure Storage can be configured to provide secure data access, protect against accidental deletion and modification, provide temporary delegated access using SAS, support traditional file shares using Azure Files, and automatically manage Blob access tiers using Lifecycle Management.
