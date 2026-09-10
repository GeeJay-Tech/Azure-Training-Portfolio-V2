# Azure Cost Visibility Dashboard

## Project Overview

This project was completed alongside my Microsoft Azure Administrator (AZ-104) training.

The goal was to create a simple cost-management solution that provides visibility into Azure spending, monitors costs against a monthly budget, and sends an alert when spending reaches a defined threshold.

## Scenario

BrightPath Solutions is beginning its Azure journey and needs a straightforward way to monitor cloud spending.

As the junior Azure administrator, I was asked to:

- Organise the project using a dedicated resource group
- Review subscription costs using Cost Analysis
- Create a reusable cost view
- Configure a monthly budget
- Configure a budget alert
- Display cost information on an Azure dashboard

## Azure Resources and Configuration

| Item | Configuration |
|---|---|
| Subscription | Azure Subscription 1 |
| Resource group | `rg-cost-dashboard-lab` |
| Region | UK South |
| Dashboard | Azure Cost Visibility Dashboard |
| Cost view | Cost by resource |
| Budget | `budget-cost-dashboard-lab` |
| Budget period | Monthly |
| Alert threshold | 80% of actual cost |

## Resource Tags

The following tags were applied to help organise and identify the project:

| Tag | Value |
|---|---|
| Project | CostVisibilityDashboard |
| Environment | Training |
| Owner | GavinJames |

## Implementation

### 1. Accessed Azure Cost Analysis

I opened Cost Analysis at the subscription scope to review spending and cost information.

![Azurehots/01-cost-analysis.png

### 2. Configured a Cost View

I used the Cost Analysis view to examine Azure costs by resource.

screenshots/02-saved-cost-view.png

### 3. Created the Cost Dashboard

I created a private Azure dashboard named **Azure Cost Visibility Dashboard** and pinned the **Cost by resource** view to it.

![Azure Cost Visibility Dashboard](screenshots/ed a Monthly Budget

I created a monthly budget named `budget-cost-dashboard-lab` to monitor subscription spending.

screenshots/04-monthly-budget.png

### 5. Configured a Budget Alert

I configured an actual-cost alert at 80% of the monthly budget.

screenshots/05-budget-alerts.png

## Project Folder Structure

```text
azure-cost-visibility-dashboard/
├── README.md
└── screenshots/
    ├── 01-cost-analysis.png
    ├── 02-saved-cost-view.png
    ├── 03-cost-dashboard.png
    ├── 04-monthly-budget.png
    └── 05-budget-alerts.png
```

## Skills Demonstrated

- Navigating the Azure portal
- Working with Azure subscriptions
- Creating and tagging resource groups
- Using Azure Cost Management
- Analysing costs by resource
- Creating monthly budgets
- Configuring budget alerts
- Creating an Azure dashboard
- Documenting an Azure project for GitHub

## Important Notes

- The subscription had no reported resource costs when the project was completed, so some views showed no cost data.
- Azure budgets provide notifications but do not automatically stop or remove resources.
- Sensitive information such as subscription IDs, tenant IDs and email addresses has been excluded from the documentation.

## Conclusion

This project demonstrates a basic Azure cost-governance solution. It provides a central dashboard for cost visibility and uses a monthly budget alert to help identify unexpected spending.
