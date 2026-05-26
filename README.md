# Agent1Solution

## 📘 Introduction
This repository demonstrates a **simple Power Platform agent solution** with an implementation of **Application Lifecycle Management (ALM)** using GitHub Actions.

The goal is to showcase a **repeatable and secure deployment pattern** for:
- Exporting solutions from a development environment
- Storing solutions in source control
- Building managed artifacts
- Deploying to production environments

This aligns with recommended ALM patterns for Power Platform using GitHub Actions.  

---

## 🧭 Solution Overview

This repository implements a simplified ALM pipeline:

1. **Export from Dev**
   - Export unmanaged solution
   - Unpack into source control
   - Commit to a feature branch

2. **Build**
   - Pack solution from source
   - Import into a build environment
   - Export as managed solution

3. **Deploy**
   - Deploy managed solution to production

These steps align with common Power Platform ALM practices such as exporting from development, generating build artifacts, and releasing to downstream environments. 【1-3d5651】  

---

## ⚙️ Workflows

The repository includes the following GitHub Actions workflows:

| Workflow | Purpose |
|----------|--------|
| `export-from-dev-and-branch-solution.yml` | Exports solution from Dev and commits to repository |
| `build-and-deploy-to-prod.yml` | Reusable workflow to build and deploy solution |
| `on-workflow-dispatch-build-and-deploy-to-prod.yml` | Manual deployment trigger |
| `on-merge-create-release.yml` | Creates release on merge |
| `on-release-build-and-deploy-to-prod.yml` | Deploys solution on release |

---

## 🔐 Configuration

This repository uses **GitHub Actions** and requires configuration of **Secrets** and **Variables** to securely authenticate and interact with Power Platform environments.

---

## 🔐 Secrets

Secrets are encrypted values used to securely store sensitive information such as credentials, tokens, and keys. These values are not exposed in logs and are required for secure authentication during workflow execution.

### Required Secrets

| Name | Scope | Description |
|------|------|------------|
| `CLIENT_ID` | 🏢 Organization | Application (Client) ID of the Microsoft Entra ID App Registration |
| `CLIENT_SECRET` | 🏢 Organization | Client secret associated with the App Registration |
| `TENANT_ID` | 🏢 Organization | Directory (Tenant) ID of the Microsoft Entra ID |

These values are used for **service principal authentication**, which is the recommended approach for automation scenarios. 【2-bd2005】  

> 🔒 Organizational secrets can be overridden at the repository level when repository-specific values are required.

---

## ⚙️ Variables

Variables are non-sensitive configuration values used by workflows. These values are visible in logs and are typically used to define environment-specific settings.

### Required Variables

| Name | Scope | Description |
|------|------|------------|
| `DEV_ENVIRONMENT_URL` | 🏢 Organization | Development environment (source of truth) |
| `BUILD_ENVIRONMENT_URL` | 🏢 Organization | Build environment for managed solution creation |
| `PROD_ENVIRONMENT_URL` | 🏢 Organization | Production environment for deployment |

> ⚙️ Organizational variables can be overridden at the repository level when repository-specific values are required.

---

## 🔧 Power Platform Actions

This repository uses **GitHub Actions for Microsoft Power Platform**, which provide capabilities such as:
- Exporting and importing solutions  
- Packaging and unpackaging solutions  
- Deploying to downstream environments  
- Automating the application lifecycle  

These actions enable full CI/CD automation directly from GitHub workflows. 【1-3d5651】  

---

## 🚀 Getting Started

To use this repository:

1. Configure required **Secrets** and **Variables**
2. Run the export workflow:
   - `export-from-dev-and-branch-solution.yml`
3. Validate changes via Pull Request
4. Trigger deployment via:
   - Manual workflow dispatch, or
   - Release workflow

---

## 🔗 References

- [GitHub Actions for Power Platform](https://learn.microsoft.com/en-us/power-platform/alm/devops-github-actions) 【1-3d5651】  
- [Available Power Platform Actions](https://learn.microsoft.com/en-us/power-platform/alm/devops-github-available-actions) 【3-ee1041】  
- [Administrative Actions](https://learn.microsoft.com/en-us/power-platform/alm/devops-github-available-administrative-actions) 【4-d42b9a】  
- [Getting Started Tutorial](https://learn.microsoft.com/en-us/power-platform/alm/tutorials/github-actions-start) 【2-bd2005】  
- [Build Tutorial](https://learn.microsoft.com/en-us/power-platform/alm/tutorials/github-actions-build) 【5-210b83】  
- [Deploy Tutorial](https://learn.microsoft.com/en-us/power-platform/alm/tutorials/github-actions-deploy) 【6-c3a587】  

---

## 🧠 Notes

- This repository is intended for **demonstration and learning purposes**
- For enterprise implementations, consider:
  - Adding solution validation (`check-solution`)
  - Implementing environment approvals
  - Separating build and deploy workflows for stricter CI/CD controls

``
