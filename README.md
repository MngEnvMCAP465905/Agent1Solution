# Agent1Solution

## Introduction
This is simple agent to demonstrate deployment better practices using GitHub Actions.

## Secrets

| Secret Name   | Description                                                                 | Scope          |
|---------------|-----------------------------------------------------------------------------|----------------|
| CLIENT_ID     | The Application (Client) ID of the Microsoft Entra ID App Registration used for authentication. Identifies the service principal used by workflows. | Organization   |
| CLIENT_SECRET | The client secret (password) associated with the App Registration. Used to securely authenticate the service principal. **Sensitive credential.** | Organization   |
| TENANT_ID     | The Directory (Tenant) ID of the Microsoft Entra ID instance hosting the App Registration. Required for authentication context. | Organization   |

## Links

- https://learn.microsoft.com/en-us/power-platform/alm/devops-github-actions
- https://learn.microsoft.com/en-us/power-platform/alm/devops-github-available-actions
- https://learn.microsoft.com/en-us/power-platform/alm/devops-github-available-administrative-actions
- https://learn.microsoft.com/en-us/power-platform/alm/tutorials/github-actions-start
- https://learn.microsoft.com/en-us/power-platform/alm/tutorials/github-actions-build
- https://learn.microsoft.com/en-us/power-platform/alm/tutorials/github-actions-deploy
