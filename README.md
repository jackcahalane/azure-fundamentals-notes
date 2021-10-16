# azure-fundamentals-notes
Rough notes created while studying for the Azure Fundamentals (AZ-900) exam

## Describe Cloud Concepts
A **hybrid cloud** is based on an on-premises architecture and a public cloud or a private cloud and a public cloud.

**Regions** are *always* paired with other regions. Paired region is always in same geography, but is always farthest from original region, minimum 300 miles away. This allows for replication outages to have minimal impact on Azure services.

IaaS allows to rent hardware and have control over the OS.

A **free Azure subscription** is good for 30 days before you have to upgrade.

A **zone** is a geographic grouping of **Azure regions** used to determine billing based on data transfers.

**Azure management groups** provide a level of scope above subscriptions. You organise subscriptions into containers called "management groups" and apply your governance conditions. All subscriptions within a management group automatically inherit conditions applied to management group.

**Resource Groups** can contain resources from *any* **region**, not just the region in which the resource group is located.

Need to have a subscription, *then* resource groups to create a resource.

Can export **ARM Template** from a resource or from a resource group.

Increase default limits for how many of select resouces of each type can be provisioned per Azure Region. Can be accomplished via **ARM**. Lets you increase default limits but doesn't let you exceed hard limits.

What is unique about **Azure Government** is that it is only available in the United States.

## Describe Core Azure Services
**Windows Virtual Desktop (WVD)** supports Remote Desktop clients on Windows Desktop, Web, Android, MacOS, iOS, and Microsoft Store Client.

Can use **WVD** with your existing Microsoft 365 ir Wubdiws oer-user license. Only pay for VM where WVD runs.

**Spot VMs** don't use standard SLA for Azure VMs.

**Scale Set**:
* A group of load balanced VMs that can automatically increase/decrease in response to demand or a defined schedule.
* VMs are automatically distributed across fault domains (FD), update domains (UD) and AZs.
* Is fault tolerant if a specific DC fails.

**Availability Set**:
* A logical grouping of VMs within a datacenter
* VMs are automatically distributed across fault domains (FD) and update domains (UD).
* Not fault tolerant if a single DC fails.

**Azure Virtual Network (VNet)** is the fundamental building block for your private network in Azure. VNet enables Azure resources to securely communicate with each other, the Internet, and on-prem networks.

**Azure Virtual Network (VNet)** is a logical isolation of the Azure cloud dedicated to your subcription.
By default, virtual networks *cannot* communicate with each other.

Reccommended to have one VNet each for frontend and backend servers.

You should use **VNet peering** or **VPN gateways** to connect Azure Vnets to each other. With VNet peering, you can seamlessly connect two or more VNets in Azure, routing the traffic directly. You can also deploy VPN gateways in each VNet to connect them to each other over the public internet.

Azure **storage account** must have Geo-redundant storage or Geo-zone-redundant storage enabled first to achieve automatic replication to another region.

Azure Storage options:
* Locally-Redundant Storage (LRS): Only resilient to single node in DC failure.
* Zone-Redundant Storage (ZRS): Available if DC down. Not if region down.
* Geo-Redundant Storage (GRS): Available if region down.

**Azure Databricks** is an Apache Spark-based analytics platform designed to provide a collaborative analytics workflow.

**Azure Event Grid** provides a solution for building event-driven architectures that subscribe to Azure resources and route events to different endpoints. Events can be filtered before being forwarded to appropriate event handlers for processing.

## General Security and Network Security Features
With **Azure Security Center**, you can do the following:
* Evaluate your regulator compliance using the Regulatory compliance dashboard.
* Improve your compliance posture by taking action on recommendations.

**Azure Security Center** auto discovers and assesses security for new resources as they are deployed.

**Azure Security Center** allows you to use just-in-time (JIT) VM access.

Azure **DDoS Standard** can mitigate the following types of attacks:
* Volumetric attacks
* Protocol attacks
* Resource (application) layer attacks

**Azure Sentinel** is a SIEM and security orchestration automated response (SOAR) solution.

Azure **Traffic Manager** is a DNS-based traffic load balancer that enables you to distribute traffic optimally to services across global Azure regions while providing high availability and responsiveness.

**Network Security Groups** can be attached to subnets and/or network interfaces.

**Azure Network Security Group** filters network traffic to and from Azure resources in an Azure virtual network.

**Application Security Groups** enable you to configure network security as a natural extension of an application structure, allowing you to group VMs and define network security policies based on these groups.

**Azure Advanced Threat Protection (ATP)** to directly monitor the domain controller traffic and detect security threats using a sensor.

## Describe Core Solutions and Management Tools on Azure
**Azure IoT Central** can be managed as a SaaS.

**Azure Sphere** is a secured, high-level application platform with built-in communciation and security features for internet-connected devices. It comprises a secured, connected, crossover microcontroller unit (MCU), a custom high-level Linux-based OS, and a cloud based security service that provides continuous, reliable security. Enables creation of secured, internet-connected devices that can be updated, controlled, monitored, and maintained remotely.

ML models created in **Machine Learning Studio** can't be deployed or managed by Azure ML service. ML Studio solutions are managed in ML Studio and are only deployed as web services.

You can access **Cloud Shell** through the Azure portal or from shell.azure.com, but you cannot use the Azure portal inside Cloud Shell.

A **stoage account** is required to use **Azure Cloud Shell**.

You should use **Cloud Shell** when you need to run the cmdlet New-AzVm in a scripting environment inside the browser.

**Azure CLI** and **PowerShell** run on Windows, Linux or MacOS. Commands work the same on Mac, Linux and Windows with both Azure CLI and PowerShell.

Both **Azure CLI** and **PowerShell** execute commands in an interactive command-line based environment. Neither supports a GUI interface.

You can use the **Azure mobile app** to run PowerShell commands. The app provides you with access to Azure Cloud Shell, where you can choose between launching Bash and PowerShell and run ad hoc Azure CLI or PowerShell commands.

You should use **Azure CLI** when you need to log in to Azure with az login without opening a browser.

**Azure Advisor** integrates with **Azure Security Center** to help prevent, detect and respond to threates to Azure resources. Based on data collected and analysis performed by Azure Advisor, Security Center identifies potential security vulnerabilities and creates recommendations.

**Azure Monitor** can use autoscale to add/remove resources as appropriate to minimize costs and ensure performance.

You can use **Service Health** to send an email whenever VM usage exceeds its quota or want to be notified if your App Service exceeds the usage quota.

**Service Health** allows you to implement a webhook on your website to display health incidents.

You should use **Azure Locks** to prevent any users from deleting resources from a subscription with content spanning mutliple resource groups.

Management locks:
* CanNotDelete
* Read-only

Use a **lock** when you want to prevent VMs from being deployed in a subscription or resource group. Can create a **Read-Only** resource lock at he scription level to prevent VMs and other resources to be created.

If a resource group has a **CanNotDelete** lock, then the adminsitrator must remove the lock before it can be deleted.

When a **lock** is applied to a scope or resource, it applies to all users and roles.

## Describe Identity, Governance, Privacy and Compliance Features
The **Microsoft Trust Center** is a central locaiton for the latest info, news, and best practices in security, privacy and compliance.

**Authentication** can use certs to identify a person or service. A certificate have an embedded key that identifies a person or service.

An MFA is required for **authentication** when supporting users located in an on-prem **Active Directory** only. Azure MFA Service (Cloud) doesn't support this configuration and requires Azure AD as a security component.

Azure guarantees at least 99.9% availability of **Azure AD Basic and Premium** services. Azure does *not* provide SLA for free tier Azure AD.

**Azure AD Free** edition support self-service password change for cloud users.

**Azure Advisor** can only provide limited recommendations for **Azure AD**. It's not capable of calculating user risk levels or providing cutom AD recommendations. These functions can only be povided by Azure AD **Identity Protection**.

Authentication types supported by both SSPR and MFA are:
* Password
* SMS
* Voice call

Role Based Access Control (RBAC): 
* **User Access Administrator**: From the contexy of the management group, this role grants permissions to assign access and policies only.

**Policies** can be assigned to a resource group.

An **initiative** is a collection of Azure policy definitions, usually grouped with the aim of achieving a single goal. Initiatives are used to siplify managing and assigning policies. The same initiative can be assigned to multiple scopes to include resources, resource groups, subsctiptions or management groups. Policies have to be in same subscription.

When an **initiative assignment** is evaluated, all policies in that initiative are evaluated. If you want to evaluate a policy by itself, you should either not assign the policy to an initiative or create an initiative that contains that policy only.

**Initiatives** can be assigned to management groups.

**Azure Policy** for ongoing evaluation of compliance and identification of non-compliant resources.

Not all Azure resources support **tags**.

When you assign a **tag** to a resource group, the resource within that group do *not* inherit the tag.

When a **blueprint** is updated and the updated version is published, any assignments of the blueprint are not updated automatically. You must update the blueprint assignment with the new updated version of the assignment.

**Blueprint Operator** role can assign existing published blueprints, but can't create new blueprint definitions.

**Compliance Manager** helps you track and manage your company's compliance to standard and regulations that are applicable to your organisation sich as ISO 27001, NIST 800-53 and GDPR.

**Audit reports** allow you to determine how comliant Azure is with regards to GDPR, as well as allow you to view a list of independent assessments on Microsoft cloud services. Reports provide info about compliance related to NIST, GDPR and ISO.

**Health Alerts** when you want you and your team to receive a text when Azure maintenance is planned.

Monitor **Health Advisories** to view the Azure features that are planned to be deprecated.

## Describe Azure Cost Management and SLAs
A **reserved capacity** is different from a reserved instance, which is mainly used for Azure database services such as Azure SQL Database, Azure Cosmos DB, Azure Synapse Analytics, and Azure Cache for Redis.

All bandwidth inbound to Azure is always free.

Bandwidth going *out* of Azure will be charged at standard data transfer rates other than those explicitly covered by the CDN or ExpressRoute pricing.

Any **Azure Disks** that are attached to a VM will not be deleted if its VM is deleted. 

You still continue to accruse charges for the Azure storage needed for the VM's OS disk and any attached data disks even if your VMs ar ealready stopped.

Azure does *not* provide an SLA for services in public preview.

Public preview is covered Microsoft Customer Support Services. Private preview is not.

Public previews are a way to obtain customer feedback on new features.

Access to preview features can be configured at the organisation or user level.

**Azure Cost Management + Billing** identifies idle and underutilized resources.
