\# Project 3 - Monitoring and Alerting System



\## Scenario



BrightPath Solutions has implemented backup protection for critical workloads hosted in Azure. To improve operational visibility and reduce response times to service issues, the company requires a monitoring and alerting solution.



As a Junior Cloud Administrator, I was tasked with implementing Azure monitoring capabilities to track resource health, generate alerts, and support proactive incident management.



\## Project Objectives



\- Configure Azure Monitor

\- Create Action Groups

\- Configure Alert Rules

\- Monitor Virtual Machine health

\- Generate and test alerts

\- Document the monitoring solution



\## Technologies Used



\- Microsoft Azure

\- Azure Monitor

\- Azure Virtual Machines

\- Action Groups

\- Alert Rules

\- Activity Log



\## Skills Demonstrated



\- Azure Administration (AZ-104)

\- Monitoring and Alerting

\- Operational Support

\- Incident Response

\- Azure Resource Management



\### Project 3 - Monitoring and Alerting System



Status: In Progress



Skills:



\- Azure Monitor

\- Alert Rules

\- Action Groups

\- Virtual Machine Monitoring

\- Incident Response



\## Environment Preparation



A dedicated Resource Group was created to host monitoring and alerting resources for BrightPath Solutions.



This provides centralized management of monitoring-related components and supports lifecycle management of Azure resources.







\## Troubleshooting



\### Virtual Machine Deployment Challenges



During the implementation of the monitoring solution, several virtual machine deployment issues were encountered.



\#### Issue 1 - VM Size Unavailable



Initial attempts to deploy Azure virtual machines using B-series and D-series VM sizes resulted in deployment errors.



Example error:



```

NotAvailableForSubscription

```



**#### Issue 2 - Insufficient Quota**



During VM size selection, Azure reported:



```

Insufficient quota - family limit

Family vCPUs are insufficient to deploy these sizes.

```



Investigation of Azure Quotas revealed that the subscription had a quota allocation of:



```

0 of 0 vCPUs

```



for certain VM families, preventing deployment of those resources.



\#### Troubleshooting Actions



The following troubleshooting steps were performed:



\- Reviewed VM size availability within the selected Azure region.

\- Tested alternative VM families and deployment configurations.

\- Investigated Azure subscription quota limitations.

\- Reviewed Azure Quotas under Microsoft.Compute.

\- Identified VM family restrictions that impacted deployment options.



\#### Lessons Learned



This exercise highlighted the importance of validating:



\- Subscription quotas

\- Regional resource availability

\- VM family restrictions

\- Azure deployment prerequisites



before implementing production workloads.



The troubleshooting process provided valuable experience in diagnosing Azure infrastructure deployment issues and understanding subscription-level limitations.





**### Issue 3 - Unable to Create Azure Monitor Action Group**



While configuring Azure Monitor, an error occurred when attempting to create an Action Group.



\*\*Error encountered:\*\*



```text

Failed to create action group.

The subscription is not registered to use namespace 'microsoft.insights'.

```



\#### Investigation



The error suggested that the Azure subscription was not registered to use the Microsoft.Insights resource provider, which is required for Azure Monitor functionality, including:



\- Azure Monitor

\- Alert Rules

\- Action Groups

\- Monitoring Notifications



\#### Resolution



The issue was resolved by:



1\. Navigating to \*\*Resource Providers\*\* within the Azure subscription.

2\. Searching for:



```text

Microsoft.Insights

```



3\. Confirming the resource provider registration status.

4\. Registering the provider.

5\. Retrying the Action Group deployment.



\#### Outcome



After registering the Microsoft.Insights resource provider, the Action Group was created successfully and email notifications were configured for monitoring alerts.



\#### Key Learning



This exercise demonstrated the importance of verifying Azure Resource Provider registration when deploying Azure services in a new subscription.



It also reinforced the need to:



\- Review deployment error messages carefully.

\- Validate subscription configuration.

\- Understand service dependencies in Azure.

\- Troubleshoot Azure Monitor deployment issues systematically.


## CPU Alert Rule



An Azure Monitor metric alert was created to monitor CPU utilisation on the BrightPath Solutions virtual machine.



\### Alert Configuration



\- Alert rule: `alert-vm-high-cpu`

\- Monitored resource: `vm-brightpath-monitoring01`

\- Signal: Percentage CPU

\- Threshold: Greater than 10%

\- Severity: 3 - Informational

\- Notification method: Azure Monitor Action Group



The low CPU threshold was selected for testing so that the alert could be triggered and the notification process validated.

## Alert Testing and Validation



The Azure Monitor alert rule was successfully tested against the virtual machine.



The alert was configured to monitor the Percentage CPU metric. When the configured threshold was exceeded, Azure Monitor changed the alert condition to Fired and initiated the associated Action Group.



\### Validation Results



\- Alert rule successfully evaluated the VM metric

\- CPU threshold was exceeded

\- Alert condition changed to Fired

\- The affected virtual machine was identified

\- The Action Group was activated

\- The monitoring and alerting workflow was successfully validated



This demonstrated that BrightPath Solutions could proactively detect performance issues affecting its Azure workloads and notify administrators through an automated alerting process.

## Alert Resolution Validation



After the virtual machine's CPU usage returned below the configured threshold, Azure Monitor automatically changed the alert condition from Fired to Resolved.



The associated Action Group sent an email confirming that the alert had been resolved.



\### Resolution Results



\- CPU usage returned below the 10 percent threshold

\- Azure Monitor automatically resolved the alert

\- The affected virtual machine was identified correctly

\- An email resolution notification was received

\- The complete alert lifecycle was successfully validated



This demonstrated that the monitoring solution could detect a performance issue, notify administrators, and confirm when the affected resource returned to normal operating conditions.

``

``

