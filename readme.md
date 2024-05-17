# Azure Component Overview

In Azure the various components are designed to provide a structured and manageable way to organize, secure, and utilize cloud resources. It's sometimes rather baffling to know what each part is and what it's responsible for. Tenant? Subscription? Resource Group? What are they all?

## 1. Azure Tenant
An Azure tenant is a dedicated instance of Azure Active Directory (Azure AD, now *Entra*) that an organization receives when it signs up for a Microsoft cloud service such as Azure. It is the fundamental unit of organization in Azure, managing users, groups, and permissions.

> - **Primary Function** Identity and access management.
> - **Key Components** Users, groups, applications, and domains.

## 2. Azure Subscription
An Azure subscription is a *logical unit of Azure services* that is linked to an Azure account, which is an identity in Azure AD. It is used to manage and bill Azure resources.

> - **Primary Function**  Billing and access management.
> - **Key Components** Resource groups, policies, and permissions.

## 3. Resource Group
A resource group is a *container* that holds related resources for an Azure solution. These resources can be anything that you create and manage within Azure, such as virtual machines, databases, and storage accounts.

> - **Primary Function**  Organization and management of related resources.
> - **Key Components** Resources like VMs, databases, and more, grouped logically.

## 4. Azure Resources
Azure resources are *individual services or instances* you can create and manage, such as virtual machines, web apps, databases, and storage accounts.

> - **Primary Function**  Provisioning and managing specific cloud services.
> - **Key Components** Compute, storage, network, databases, and more.

## 5. Service Connector
An Azure service connector, often implemented as a feature or component within certain Azure services, facilitates the *integration and connectivity *between different Azure services or between Azure and external services.

> - **Primary Function** Seamless integration between different services.
> - **Key Components** APIs, connectors, and integration tools.

---

## Relationships Between the Components

### Tenant to Subscription
Each Azure tenant can contain multiple subscriptions. Subscriptions are used to logically separate resources for different purposes, such as development, testing, and production, or by different teams within an organization.

#### Example
A single organization (tenant) might have separate subscriptions for different departments or projects.

### Subscription to Resource Groups

Each subscription can contain *multiple resource groups*. Resource groups help in organizing and managing resources that share the same lifecycle, permissions, and policies.

#### Example
A subscription might have resource groups for different applications, environments (e.g., dev, test, prod), or services.

### Resource Groups to Resources

Each resource group contains one or more resources. Resources within a resource group can be managed together, and access controls can be applied at the resource group level.

#### Example
A resource group might contain a web app, a database, and a storage account, all related to a specific project.

### Resources to Service Connectors

Service connectors allow resources to interact with each other or with external services. They enable seamless integration and data flow between different services within Azure or with external services.

#### Example
A service connector might link a web app to a database or integrate an Azure function with an external API.

## Visual Representation

```mathematica
Azure Tenant
├── Subscription 1
│   ├── Resource Group 1
│   │   ├── Resource A
│   │   ├── Resource B
│   ├── Resource Group 2
│   │   ├── Resource C
│   │   ├── Resource D
├── Subscription 2
│   ├── Resource Group 3
│   │   ├── Resource E
│   │   ├── Resource F
```
---

## Resource Groups

We are going to be using resource groups a lot. They are a useful wat to not only keep all of our associated resources together, but also means that when we delete our resource group, then all resources within it are deleted. This is *good news* as it means we don't have expensive resources we are not using hanging around!