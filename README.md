# Agent1Solution

## Introduction
This is simple agent to demonstrate deployment better practices using GitHub Actions.

## Secrets

Secrets are securely stored, encrypted values used by workflows to authenticate with external services and protect sensitive information. 

These values are not exposed in logs and should be used for credentials such as client secrets, tokens, and other confidential data required during pipeline execution.

| Name   | Description                                                                 |
|---------------|-----------------------------------------------------------------------------|
| CLIENT_ID     | The Application (Client) ID of the Microsoft Entra ID App Registration used for authentication. Identifies the service principal used by workflows. |
| CLIENT_SECRET | The client secret (password) associated with the App Registration. Used to securely authenticate the service principal. |
| TENANT_ID     | The Directory (Tenant) ID of the Microsoft Entra ID instance hosting the App Registration. Required for authentication context. |

🔐 These secrets are managed at the organization level and should be scoped to only the repositories that require them.

## Links

- https://learn.microsoft.com/en-us/power-platform/alm/devops-github-actions
- https://learn.microsoft.com/en-us/power-platform/alm/devops-github-available-actions
- https://learn.microsoft.com/en-us/power-platform/alm/devops-github-available-administrative-actions
- https://learn.microsoft.com/en-us/power-platform/alm/tutorials/github-actions-start
- https://learn.microsoft.com/en-us/power-platform/alm/tutorials/github-actions-build
- https://learn.microsoft.com/en-us/power-platform/alm/tutorials/github-actions-deploy
