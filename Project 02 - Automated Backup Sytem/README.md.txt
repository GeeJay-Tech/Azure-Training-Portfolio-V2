# Project 2 - Automated Backup System

## Scenario

BrightPath Solutions is a growing IT consultancy that hosts critical business applications on Azure Virtual Machines.

To protect company data and ensure business continuity, BrightPath Solutions requires an automated backup solution that can recover systems from accidental deletion, data corruption, ransomware attacks, or infrastructure failures.

As a Junior Cloud Administrator, I was tasked with implementing and testing an Azure Backup solution that provides automated protection for business-critical workloads.

## Project Objectives

- Create a Recovery Services Vault
- Configure Azure VM backups
- Create a backup policy
- Schedule automatic daily backups
- Verify backup jobs complete successfully
- Perform a test restore
- Document the solution

## Technologies Used

- Microsoft Azure
- Azure Virtual Machines
- Recovery Services Vault
- Azure Backup
- Azure Monitor

## Skills Demonstrated

- Azure Administration (AZ-104)
- Backup and Recovery
- Business Continuity Planning
- Recovery Services Vault Management
- Documentation and Reporting

### Deployment Troubleshooting

Initial VM deployments using Windows Server 2022 and the Standard_B1s size failed with an InternalOperationError during provisioning.

After troubleshooting, the deployment was successfully completed using:

- Windows Server 2019 Datacenter
- Standard_B1ms VM size
- UK South region

This highlights the importance of validating deployment options and troubleshooting Azure provisioning issues during infrastructure deployments.

## Backup Solution Design

To meet BrightPath Solutions' business continuity requirements, a Recovery Services Vault was deployed to provide centralized backup management for Azure resources.

The vault will store recovery points and enable backup and restore operations for business-critical virtual machines.

## Backup Configuration

A Recovery Services Vault backup policy was created and assigned to the virtual machine.

Policy Details:

- Daily automated backups
- Centralized backup management
- Recovery point retention
- Support for restore and recovery operations

This configuration ensures that BrightPath Solutions can recover critical systems following operational incidents or data loss events.

## Backup Validation

A manual backup was initiated to validate the configuration.

Results:

- Backup policy successfully applied
- Backup job completed successfully
- Recovery point created
- VM protection verified

This confirmed that the backup solution was functioning as expected and capable of creating recovery points for business-critical workloads.
``

## Architecture

The solution was designed to provide automated protection for a business-critical Azure virtual machine.

Components:

- Azure Resource Group
- Azure Virtual Machine
- Recovery Services Vault
- Azure Backup Policy
- Recovery Points
- Restore Operations

Workflow:

1. Azure VM deployed
2. Recovery Services Vault created
3. Backup policy configured
4. Daily backups scheduled
5. Recovery points generated
6. Restore operation tested successfully

## Deployment Evidence

### Resource Group Created
!creenshots/01-resource-group-created.png

### Virtual Machine Deployed
screenshots/02-vm-created.png

### Recovery Services Vault
![Recovery Services Vaultervices-vault.png

### Backup Enabled
![Backupots/04-backup-enabled.png

### Successful Backup Job
![Backup Job](screenshots/05successful.png

### Restore Validation
screenshots/06-restore-test.png
``

## Key Outcomes

This project demonstrated:

- Azure Backup configuration
- Recovery Services Vault management
- Backup policy creation
- Recovery point management
- Disaster recovery testing
- Azure administration aligned to AZ-104 objectives

The solution successfully protected and restored a business-critical virtual machine for the fictional company BrightPath Solutions.