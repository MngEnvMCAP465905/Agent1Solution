# Agent1Solution

## Introduction
This is simple agent to demonstrate deployment better practices using GitHub Actions.

## Configuration

This repository uses GitHub Actions and requires configuration of **Secrets** and **Variables** to securely authenticate and interact with Power Platform environments.

### 🔐 Secrets

Secrets are encrypted values used to securely store sensitive information such as credentials, tokens, and keys. These values are not exposed in logs and are required for secure authentication during workflow execution.

- **CLIENT_ID** (Organization)  
  The Application (Client) ID of the Microsoft Entra ID App Registration used for authentication. Identifies the service principal used by workflows.

- **CLIENT_SECRET** (Organization)  
  The client secret (password) associated with the App Registration. Used to securely authenticate the service principal.

- **TENANT_ID** (Organization)  
  The Directory (Tenant) ID of the Microsoft Entra ID instance hosting the App Registration. Required for authentication context.

| Name   | Description                                                                 | Scope        |
|---------------|-----------------------------------------------------------------------------|--------------|
| CLIENT_ID     | The Application (Client) ID of the Microsoft Entra ID App Registration used for authentication. Identifies the service principal used by workflows. | Organization   |
| CLIENT_SECRET | The client secret (password) associated with the App Registration. Used to securely authenticate the service principal. | Organization   |
| TENANT_ID     | The Directory (Tenant) ID of the Microsoft Entra ID instance hosting the App Registration. Required for authentication context. | Organization   |

> 🔒 Organizational secrets can be overridden at the repository level when repository-specific values are required.

### ⚙️ Variables

Variables are non-sensitive configuration values used by workflows. These values are visible in logs and are typically used to define environment-specific settings.


| Name                     | Description                                                                 | Scope        |
|----------------------------------|-----------------------------------------------------------------------------|--------------|
| DEV_ENVIRONMENT_URL              | URL of the development Power Platform environment used for exporting solutions. | Organization   |
| BUILD_ENVIRONMENT_URL            | URL of the build Power Platform environment used for managed solution conversion. | Organization   |
| PROD_ENVIRONMENT_URL       | URL of the production Power Platform environment used for deployment.        | Organization   |

> ⚙️ Organizational variables can be overridden at the repository level when repository-specific values are required.

## Links

- https://learn.microsoft.com/en-us/power-platform/alm/devops-github-actions
- https://learn.microsoft.com/en-us/power-platform/alm/devops-github-available-actions
- https://learn.microsoft.com/en-us/power-platform/alm/devops-github-available-administrative-actions
- https://learn.microsoft.com/en-us/power-platform/alm/tutorials/github-actions-start
- https://learn.microsoft.com/en-us/power-platform/alm/tutorials/github-actions-build
- https://learn.microsoft.com/en-us/power-platform/alm/tutorials/github-actions-deploy
