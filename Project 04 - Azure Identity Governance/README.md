# Project 04 - Azure Identity Governance

## Project Overview

In this project, I implemented identity and governance controls for a fictional organisation, **BrightPath Solutions**, using Microsoft Azure.

The objective was to gain hands-on experience with Microsoft Entra ID, Azure Role-Based Access Control (RBAC), Azure Policy, and Resource Locks.

Rather than only configuring the controls, I also tested them to verify that they behaved as expected.

---

## Technologies and Azure Services Used

- Microsoft Entra ID
- Azure Role-Based Access Control (RBAC)
- Azure Resource Groups
- Azure Policy
- Azure Resource Locks
- Azure Storage deployment validation

---

## 1. Resource Group Creation

I created a dedicated resource group named:

`rg-brightpath-governance`

The resource group was deployed in **UK South** and used as the scope for the governance controls implemented during the project.

![Resource Group Overview](Screenshots/01%20-%20Resource%20Group%20overview.png)

---

## 2. Microsoft Entra ID Test User

I created a test identity named **BrightPath Test User** in Microsoft Entra ID.

This account was used to demonstrate how an identity in Microsoft Entra ID can be granted access to Azure resources through Azure RBAC.

![BrightPath Test User](Screenshots/02.%20BrightPath%20Test%20User%20in%20Entra%20ID.png)

---

## 3. Azure RBAC Configuration

I assigned the **Contributor** role to the BrightPath Test User at the `rg-brightpath-governance` resource group scope.

This demonstrated the Azure RBAC model:

**Who:** BrightPath Test User  
**Role:** Contributor  
**Scope:** rg-brightpath-governance

The Contributor role allows the user to create and manage resources within the assigned scope without granting permission to assign Azure RBAC roles to other users.

Resources created within the resource group also fall within this RBAC scope.

![Contributor RBAC Assignment](Screenshots/03%20-%20Contributor%20RBAC%20role%20assignment.png)

---

## 4. Resource Lock Configuration

To protect the environment against accidental deletion, I configured a **Delete resource lock** on the resource group.

The lock allows authorised administrators to continue modifying resources while preventing the protected resource group and applicable resources from being deleted.

![Delete Lock Configured](Screenshots/04%20-%20Deleting%20lock%20configured.png)

---

## 5. Resource Lock Validation

I tested the resource lock by attempting to delete `rg-brightpath-governance`.

Azure rejected the deletion and reported that the resource group was locked and could not be deleted.

This confirmed that the Delete lock was working as intended.

![Deletion Blocked](Screenshots/05%20-%20Deletion%20blocked%20by%20the%20resource%20lock.png)

---

## 6. Azure Policy Configuration

I assigned the built-in **Allowed locations** Azure Policy to `rg-brightpath-governance`.

The policy was configured to allow resources to be deployed only in:

**UK South**

This demonstrated how Azure Policy can enforce organisational governance requirements independently of a user's RBAC permissions.

![Allowed Locations Policy](Screenshots/06%20-%20Allowed%20locations%20Policy%20assignment.png)

---

## 7. Testing a Non-Compliant Deployment

To validate the policy, I attempted to configure an Azure Storage account in **North Europe**.

Because North Europe was not included in the permitted locations, Azure Policy prevented the deployment from passing validation.

This demonstrated that having permission through RBAC to create a resource does not allow a user to bypass an Azure Policy restriction.

![North Europe Blocked](Screenshots/07%20-%20North%20Europe%20deployment%20blocked%20by%20Policy.png)

---

## 8. Testing a Compliant Deployment

I changed the proposed Storage account location from North Europe to **UK South**.

The deployment then passed validation, confirming that resources complying with the Allowed locations policy could be deployed successfully.

The Storage account did not need to be created because the purpose of this test was to validate policy enforcement.

![UK South Validation Passed](Screenshots/08%20-%20UK%20south%20validation%20passed.png)

---

## Key Learning Outcomes

Through this project, I gained practical experience with:

- Creating identities in Microsoft Entra ID
- Assigning Azure RBAC roles
- Understanding RBAC scope and inheritance
- Applying the principle of least privilege
- Protecting Azure resources using Resource Locks
- Assigning built-in Azure Policies
- Configuring policy parameters
- Testing compliant and non-compliant deployments
- Understanding the difference between RBAC and Azure Policy

A key takeaway from the project was:

**Azure RBAC controls who can perform actions, while Azure Policy controls what configurations are allowed.**

I also validated the difference between Azure resource lock types:

**Delete:** Resources can be modified but deletion is prevented.  
**Read-only:** Resources can be viewed but modifications and deletions are prevented.

---

## AZ-104 Skills Demonstrated

This project provided hands-on experience relevant to the **Microsoft AZ-104: Microsoft Azure Administrator** certification, particularly:

- Manage Microsoft Entra users
- Manage access to Azure resources
- Configure Azure RBAC
- Manage Azure governance
- Configure Azure Policy
- Configure Resource Locks
- Understand Azure resource hierarchy and scope