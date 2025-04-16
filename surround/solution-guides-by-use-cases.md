---

copyright:
  years: 2025
lastupdated: 2025-04-14

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Surround workloads by use-case
{: #surround-workloads-by-use-case}

This section lists the available solution guides, reference architectures or deployable architectures by use-cases.

A deployable architecture is cloud automation for deploying a common architectural pattern that combines one or more cloud resources. It is designed to provide simplified deployment by users, scalability, and modularity. See [What is a deployable architecture?](/docs/secure-enterprise?topic=secure-enterprise-understand-module-da#what-is-da).

An IBM Cloud project is a management tool that is designed to organize and provide visibility into a real-world project that exists in your organization. A project manages all of the configured instances of a deployable architecture and the resources that are related to the real-world reasons that they are deployed. See [https://cloud.ibm.com/docs/secure-enterprise?topic=secure-enterprise-understand-module-da#what-are-projects](https://cloud.ibm.com/docs/secure-enterprise?topic=secure-enterprise-understand-module-da#what-are-projects).

## AI
{: #surround-workloads-by-use-case-ai}

The following solution guides are available for AI to enable you to leverage AI with your non-RISE workloads:

* [Gen AI Pattern for Watsonx on IBM Cloud](/docs/pattern-genai-rag?topic=pattern-genai-rag-genai-pattern) - This reference architecture summarizes the best practices for Watsonx Gen AI Pattern deployment on IBM Cloud. AI holds the promise to transform life and business but raises concerns around trust, security, and regulatory compliance. Understanding Gen AI and its infrastructure is vital for navigating its complex landscape. This reference architecture showcases how IBM Cloud and Watsonx provide a secure environment for deploying and governing Gen AI applications.
* [Watsonx.ai SaaS with Assistant and Governance](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-watsonx-ai-reference-architecture) - The Watsonx.ai SaaS with Assistant and Governance deployable architecture is designed to automate the deployment and configuration of the IBM watsonx platform in an IBM Cloud account. The IBM watsonx platform is made up of several services working together to offer AI capabilities to end users who can explore them using IBM watsonx projects. The automation also configures a IBM watsonx starter project for an existing IBM Cloud user. A typical use case is to establish a ready to use IBM watsonx platform in an Enterprise account by granting administrator access to an AI Researcher. It enables an administrator to automatically install all of the services that the IBM watsonx platform is comprised of, as well as the setup of a starter watsonx project, allowing an AI Researcher to login to the platform and begin working immediately.

IBM watsonx as a Service is where you work with, deploy, and govern foundation and machine learning models with watsonx.ai and watsonx.governance, see [Realize the promise of AI with watsonx](https://www.ibm.com/watsonx){: external}. For detailed information on wastonx, see [Documentation for IBM watsonx as a Service](https://dataplatform.cloud.ibm.com/docs/content/wsj/getting-started/welcome-main.html?context=wx&audience=wdp){: external}

## Data
{: #surround-workloads-by-use-case-data}

IBM watsonx.data is a hybrid, open data lakehouse to power AI and analytics with all your data anywhere. It combines the elements of the data warehouse and data lakes to bring the best-in-class features and optimizations.

It offers a single platform where you can store the data or attach your current data sources for managing and analyzing your enterprise data. Attaching your data sources helps to reduce data duplication and cost of storing data in multiple places.

It uses open data formats with APIs and machine learning libraries, making it easier for data scientists and data engineers to use the data. architecture enforces schema and data integrity, making it easier to implement robust data security and governance mechanisms.

You can use watsonx.data to store any type of data (structured, semi-structured, and unstructured) and make that data accessible directly for Artificial Intelligence (AI) and Business Intelligence (BI). 

At this time, there are no solution guides available to assist you with leveraging watson.data with your non-RISE workloads, however, watsonx.data can be deployed in IBM Cloud with one of the following deployment patterns:

* Software as a Service (SaaS) – The SaaS version of watsonx.data deployed on IBM Cloud see [IBM watsonx.data overview](/docs/watsonxdata?topic=watsonxdata-wxd_ov).
* Software – watsonx.data can be deployed on IBM Software Hub see [IBM watsonx.data on IBM Software Hub](https://www.ibm.com/docs/en/watsonx/watsonxdata/2.1.x?topic=software){: external}. IBM Software Hub runs on top of Red Hat OpenShift, which means that you can run IBM Software Hub on any on-premises, private cloud cluster or any public cloud infrastructure that supports Red Hat OpenShift. See [Red Hat OpenShift on IBM Cloud](https://www.ibm.com/products/openshift){: external} and [Getting started with Red Hat OpenShift on IBM Cloud](/docs/openshift?topic=openshift-getting-started).

## IBM Cloud Framework for Financial Services
{: #surround-workloads-by-use-case-fs}

IBM Cloud for Financial Services&reg; is designed to build trust and enable a transparent public cloud ecosystem with the features for security, compliance, and resiliency that financial institutions require. Financial institutions can confidently host their mission-critical applications in the cloud and transact quickly and efficiently. With a large partner ecosystem of independent software vendors (ISVs), Software as a Service (SaaS), and fintech partners, IBM Cloud for Financial Services offers a new generation of cloud for the enterprise.

Financial institutions can now deploy on public cloud to enable innovation and deliver new outstanding customer experiences, while managing stringent industry regulations for sensitive data and complex workloads. See the solution guide [Getting started with IBM Cloud for Financial Services](/docs/framework-financial-services?topic=framework-financial-services-about) which describes the following reference architectures: 

* [Single-region IBM Cloud for Financial Services reference architecture for VPC with Virtual Servers for VPC](/docs/framework-financial-services?topic=framework-financial-services-vpc-architecture-detailed-vsi) - This architecture shows a deployment of the VPC that uses Virtual Servers for VPC as the primary compute.
* [Virtual Servers for VPC and Power Virtual Server reference architecture for IBM Cloud for Financial Services](/docs/framework-financial-services?topic=framework-financial-services-vpc-architecture-detailed-vsi-w-powervs) - This solution pattern contains the design and architecture decisions for cloud native and Power Virtual Server workloads in IBM Cloud for Financial Services.
* [Single-region IBM Cloud for Financial Services reference architecture for VPC with Red Hat OpenShift on IBM Cloud](/docs/framework-financial-services?topic=framework-financial-services-vpc-architecture-detailed-openshift) - Red Hat OpenShift on IBM Cloud extends the Kubernetes platform with built-in software to enhance app lifecycle development, operations, and security. The master nodes are entirely IBM's responsibility, while there is shared responsibility for the worker nodes.

In addition to the solution guide above, [Landing zone](/docs/secure-infrastructure-vpc) describes a number of VPC landing zone deployable architectures. These are Infrastructure as Code (IaC_) assets based on the IBM Cloud for Financial Services reference architecture. You can use the deployable architectures to create a secure and customizable Virtual Private Cloud (VPC) environments:

* [VPC landing zone](/docs/secure-infrastructure-vpc?topic=secure-infrastructure-vpc-vpc-ra) - This deployable architecture deploys a VPC landing zone with two Virtual Private Clouds (VPC); a Management VPC to manage the environment, and a Workload VPC that hosts the workload. Each VPC is a multi-zoned, multi-subnet implementation that keeps your workloads secure. A transit gateway connects the VPCs to each other and Virtual Private Endpoints are used connect to IBM Cloud services. IBM Cloud Flow Logs for VPC enables the collection and storage of information about the internet protocol (IP) traffic that is going to and from network interfaces within your VPC. In addition, Activity Tracker logs events from enabled services. IBM Cloud Flow Logs for VPC and Activity Tracker are included in this deployable architecture. You can add more security services, such as Hyper Protect Crypto Services.
* [VSI on VPC landing zone](/docs/secure-infrastructure-vpc?topic=secure-infrastructure-vpc-vsi-ra) - This deployable architecture creates a customizable and secure infrastructure, with virtual servers, to run your workloads with a Virtual Private Cloud (VPC) in multi-zone regions.
* [VSI on existing VPC landing zone - Extension](/docs/secure-infrastructure-vpc?topic=secure-infrastructure-vpc-vsi-ext-ra) - This deployable architecture extends an existing VPC deployable architecture by creating virtual server instances (VSI) in some or all of the subnets of any existing landing zone VPC deployable architecture.
* [VSI on VPC landing zone - QuickStart variation](/docs/secure-infrastructure-vpc?topic=secure-infrastructure-vpc-vsi-ra-qs) - The QuickStart variation of the VSI on VPC landing zone deployable architecture creates a fully customizable Virtual Private Cloud (VPC) environment in a single region. The solution provides virtual servers in a secure VPC for your workloads. The QuickStart variation is designed to deploy quickly for demonstration and development.
* [Red Hat OpenShift Container Platform on VPC landing zone](/docs/secure-infrastructure-vpc?topic=secure-infrastructure-vpc-ocp-ra) - Red Hat OpenShift Container Platform on VPC landing zone is a deployable architecture solution that is based on the IBM Cloud for Financial Services reference architecture. It creates secure and compliant Red Hat OpenShift Container Platform workload clusters on a Virtual Private Cloud (VPC) network.
* [Red Hat OpenShift Container Platform on VPC landing zone - QuickStart variation](/docs/secure-infrastructure-vpc?topic=secure-infrastructure-vpc-roks-ra-qs) - The QuickStart variation of the Red Hat OpenShift Container Platform on VPC landing zone deployable architecture creates a fully customizable Virtual Private Cloud (VPC) environment in a single region. The solution provides a single Red Hat OpenShift cluster in a secure VPC for your workloads. The QuickStart variation is designed to deploy quickly for demonstration and development.

## Hybrid
{: #surround-workloads-by-use-case-hybrid}

These solution guides describe hybrid use cases, linking on-premise applications with IBM Cloud:

* [Hybrid HPC with persistent cloud resource pools](/docs/hybrid-hpc-cloud-pool?topic=hybrid-hpc-cloud-pool-hybrid-hpc-pers-cloud-pool) - This reference architecture summarizes the best practices for deploying a Hybrid High Performance Computing (HPC) environment connecting an on-premises HPC environment to a persistent pool of HPC compute on IBM Cloud&reg;. An organization with an existing HPC on-premises facility might decide to augment this with cloud-based resources.
* [Hybrid HPC with dynamic cloud resource pools](/docs/hybrid-hpc-cloud-pool?topic=hybrid-hpc-cloud-pool-hybrid-hpc-dyn-cloud-pool) - This reference architecture summarizes the best practices for deploying a Hybrid High Performance Computing (HPC) environment connecting an on-premises HPC environment to a dynamically provisioned pool of HPC compute resources on IBM Cloud&reg;. An organization with an existing HPC on-premises facility might decide to augment this with these dynamic cloud-based resources.
* [Deploy Satellite on-premises or in hyperscaler](/docs/pattern-base-ibm-cloud-satellite?topic=pattern-base-ibm-cloud-satellite-base-ibm-cloud-satellite) - Due to privacy, regulatory, or compliance reasons, customers might not send or store data in the public cloud. In such scenarios, the best option is to create one or more Satellite locations on-premises and hosts the data locally to satisfy the data residency requirement. The Satellite on-premises or in hyperscaler pattern includes two common solution patterns:

    * One or more IBM Cloud Satellite locations configured on-premises
    * One Satellite location is configured on-premises, and another Satellite location is configured in the cloud

* [IBM Cloud private connectivity offerings](/docs/private-connectivity?topic=private-connectivity-connect-privately-ibm-cloud) - This guide describes the various ways of connecting to IBM Cloud with a private connection using the following topologies:

    * Direct Link Dedicated - Single tenant connection to IBM Cloud Point of Presences (PoPs)
    * Direct Link Connect - Multi-tenant service provider connection to IBM Cloud PoPs
    * VPN (site-to-site) - VPN tunnel from on-premises firewall to IBM Cloud VPN
    * VPN (client-to-site) - VPN tunnel from laptop to IBM Cloud VPN
    * Satellite Connector - A layer-7, endpoint-oriented connection from IBM Cloud to access on-premises data source.

* [Extending your enterprise network to IBM Cloud](/docs/pattern-classic-edge-gateway?topic=pattern-classic-edge-gateway-extending-enterprise-network) - This guide describes on-premises data centers connectivity into IBM Cloud classic, with workloads in classic, Power Virtual Server, and Virtual Private Cloud (VPC). The diagram includes examples to show where workload compute instances, proxy servers, and jump servers are located.

## Observability
{: #surround-workloads-by-use-case-observability}

These solution guides describe [Observability](/docs/observability-hub) use cases. IBM Cloud offers Observability services that you can use to monitor, troubleshoot, and understand the activity in your account. You can also use them to keep records for auditing and compliance. This guide describes the following services:
  
* [IBM Cloud Logs](/docs/cloud-logs) - IBM Cloud Logs is a scalable logging service that persists logs and provides users with capabilities for querying, tailing, and visualizing logs.
* [IBM Cloud Monitoring](/docs/monitoring) - IBM Cloud Monitoring is a cloud-native, and container-intelligence management system that you can include as part of your IBM Cloud architecture. Use it to gain operational visibility into the performance and health of your applications, services, and platforms.
* [IBM Cloud Activity Tracker Event Routing](/docs/atracker) - Use IBM Cloud Activity Tracker Event Routing to configure how to route auditing events, both global and location-based event data, in your IBM Cloud. Auditing events are critical data for security operations and a key element for meeting compliance requirements. Control of the storage location is critical to building enterprise-grade solutions on the IBM Cloud.
* [IBM Cloud Logs Routing](/docs/logs-router) - You can use IBM Cloud Logs Routing to collect and route IBM Cloud logs from your account to a configured target.
* [IBM Cloud Metrics Routing](/docs/metrics-router) - Use IBM Cloud Metrics Routing to configure how to route platform metrics in your IBM Cloud account.

### IBM Cloud Essential Security and Observability Services deployable architecture
{: #surround-workloads-by-use-case-observability-da}

The [IBM Cloud Essential Security and Observability Services](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-core-security-services-pattern) deployable architecture summarizes the deployment and best practices on IBM Cloud for setting essential security services and their associated dependencies. IBM Cloud's essential security services are crucial for ensuring robust security and compliance for cloud-based applications and data. Their primary goal is to provide a framework for secure and compliant IBM Cloud workloads. These services include:

* Key Protect - This service provides a secure and scalable way to manage encryption keys for your cloud applications. It ensures that sensitive data is protected by managing and safeguarding cryptographic keys, facilitating compliance with industry standards and regulatory requirements. See [IBM Key Protect for IBM Cloud](https://www.ibm.com/products/key-protect).
* Secrets Manager - This service helps in securely storing and managing sensitive information such as API keys, credentials, and certificates. By centralizing secret management, it reduces the risk of exposure and simplifies the process of accessing and rotating secrets, thereby enhancing the security posture. See [IBM Cloud Secrets Manager](https://www.ibm.com/products/secrets-manager).
* Security and Compliance Center - This platform offers a comprehensive suite of tools to assess, monitor, and maintain the security and compliance of your cloud environment. It provides insights and controls to help organizations meet regulatory requirements, adhere to best practices, and protect against threats. See [IBM Security and Compliance Center](https://www.ibm.com/products/security-and-compliance-center).
* IBM Cloud Security and Compliance Center Workload Protection - This service offers features to protect workloads, get deep cloud and container visibility, posture management (compliance, benchmarks, CIEM), vulnerability scanning, forensics, and threat detection and blocking. See [Getting started with IBM Cloud Security and Compliance Center Workload Protection](/docs/workload-protection?topic=workload-protection-getting-started).

## Security and compliance
{: #surround-workloads-by-use-case-security-compliance}

The security and compliance use case focuses on the following IBM Cloud offerings:

* [Security and Compliance Center](https://cloud.ibm.com/catalog/services/security-and-compliance-center?catalog_query=aHR0cHM6Ly9jbG91ZC5pYm0uY29tL2NhdGFsb2c%2Fc2VhcmNoPXNlY3VyaXR5I3NlYXJjaF9yZXN1bHRz){: external} - Manage your continuous compliance monitoring needs.
* [Security and Compliance Center Workload Protection](https://cloud.ibm.com/workload-protection/catalog/security-and-compliance-center-workload-protection?catalog_query=aHR0cHM6Ly9jbG91ZC5pYm0uY29tL2NhdGFsb2c%2Fc2VhcmNoPXNlY3VyaXR5I3NlYXJjaF9yZXN1bHRz){: external} - Cloud-Native Application Protection Platform solution to manage your security and compliance posture, allowing you to monitor misconfigurations and detect and respond to vulnerabilities and threats in real-time.

### IBM Cloud Security and Compliance Center
{: #surround-workloads-by-use-case-security-compliance-scc}

With IBM Cloud Security and Compliance Center, you can evaluate for and view the current compliance posture of your deployed resources through a unified dashboard. Each resource is evaluated to determine its compliance to a specific control that you select. With Security and Compliance Center you can evaluate your resources in IBM Cloud. To start evaluating resources in other environments such as a Amazon Web Services and Microsoft Azure, you must connect an instance of Security and Compliance Center Workload Protection through the integrations panel. For a list of IBm Cloud resources that can be evaluated see [IBM Cloud components that can be evaluated](/docs/security-compliance?topic=security-compliance-scannable-components#evaluate-services).

You can configure Caveonix Cloud Platform to send results to Security and Compliance Center so that you can view all of your results in one place. Caveonix can transmit infrastructure findings that are found when a compliance scan is run that evaluates VMware environments. See [Connecting Caveonix Cloud Platform](/docs/security-compliance?topic=security-compliance-setup-caveonix&interface=ui)

When you integrate an instance of IBM Cloud Security and Compliance Center Workload Protection with Security and Compliance Center, you can run scans that validate your level of compliance to a specific predefined profile. Then, you can view all the results and a history of those results in a single location. See [Connecting Workload Protection](/docs/security-compliance?topic=security-compliance-setup-workload-protection&interface=ui)

As a security or compliance focal, you would choose a predefined profile that is most suitable for your organization and optionally customize the profile by creating custom rules, adding or removing rules, or building your own profile based on the catalog of controls. To scan your resources, you create an attachment of the profile to the scope of resources you want to scan. After the attachment is created, your resources are evaluated one time per day by Security and Compliance Center. As results are returned, they are forwarded to your Cloud Object Storage bucket while results are shown in the Security and Compliance Center dashboard. See [IBM Security and Compliance Center](https://www.ibm.com/products/security-and-compliance-center) and [Getting started with Security and Compliance Center](/docs/security-compliance?topic=security-compliance-getting-started).

### IBM Cloud Security and Compliance Center Workload Protection
{: #surround-workloads-by-use-case-security-compliance-scc-wp}

IBM Cloud Security and Compliance Center (SCC) Workload Protection is a cloud-native application protection platform (CNAPP) that allows customers to monitor and secure workloads across hybrid multi-cloud environments. With SCC Workload Protection, you can leverage advanced features including vulnerability management, cloud security posture management (CSPM), along with threat detection, helping you safeguard your most critical business applications. See [Getting started with SCC Workload Protection guidance](/docs/workload-protection?topic=workload-protection-getting-started).

SCC Workload Protection, automates compliance checks for IBM Cloud Framework for Financial Services, Digital Operational Resilience Act (DORA), CIS IBM Cloud Foundations Benchmark, PCI and many other industry related or best practices standards. With a detailed inventory of your IBM Cloud resources and prioritization based on full context it facilitates the resolution and management of collected violations. See [About IBM Cloud Security Posture Management (CSPM)](docs/workload-protection?topic=workload-protection-about). Key features of SCC Workload Protection include:

* [Cloud Security Posture Management (CSPM)](/docs/workload-protection?topic=workload-protection-key-features#feature_1) - Provides a unified and centralized platform to manage the security and compliance of applications, workloads and infrastructure that run on IBM Cloud, in other clouds, and on-prem, covering managed services, hosts or VMs and containers, OpenShift or Kubernetes.
* [Vulnerability Management](/docs/workload-protection?topic=workload-protection-key-features#feature_2) - Scanning for vulnerabilities on OS packages and 3rd-party libraries such as Java, Python, Golang, Javascript, or Ruby.
* [Server Endpoint Detection and Response (EDR)](/docs/workload-protection?topic=workload-protection-key-features#feature_3) - Instruments hosts, VMs and Kubernetes/OpenShift clusters to inspect all system activity through system calls with minimal performance footprint.
* [Kubernetes Workload Protection and Network Segmentation (CWPP)](/docs/workload-protection?topic=workload-protection-key-features#feature_4) - IBM Cloud Security and Compliance Center Workload Protection is a full Kubernetes Workload Protection Platform including vulnerability scanning, host and container detection/prevention, posture and compliance (KSPM), all built for Kubernetes and OpenShift.
* [Incident response and forensics](/docs/workload-protection?topic=workload-protection-key-features#feature_5) - Automates the collection and correlation of events, posture, and vulnerabilities to identities across hosts, VMs, containers and Cloud activity.

SCC Workload Protection is available in the IBM Cloud catalog, see [Security and Compliance Center Workload Protection](https://cloud.ibm.com/workload-protection/catalog/security-and-compliance-center-workload-protection).

## Resiliency
{: #surround-workloads-by-use-case-resiliency}

These solution guides describe [Resiliency](/docs/resiliency) - This guide discusses the following resiliency topics:

* [Understanding high availability](/docs/resiliency?topic=resiliency-understanding-ha) - A discussion on architecture patterns to design IBM Cloud services for high availability (HA), helping ensure resilience against different fault types that might impact the distributed IBM Cloud infrastructure. For HA in the cloud, it's important to understand the high-level concepts that you need to address if you're building or running a highly available cloud system. HA is achieved by using redundant system components and services, and by distributing these components across different environments. IBM Cloud delivers highly available cloud services by using redundant components and eliminating single points of failure. At the multizone regions (MZR) level, HA means having workloads running in multiple availability zones in the MZR, which provide the redundancy for local failures. 
* [Understanding disaster recovery](/docs/resiliency?topic=resiliency-understanding-dr) - Disaster recovery (DR) the process of recovering one or more workloads to a working state in a second IBM Cloud region after an unplanned outage. HA is not the same as DR. Disasters are different. Disasters cause a workload to go down despite attempts to make it highly available. The worst disasters have widespread consequences, which means that affected workloads might require recovery in a different region altogether.
* [Understanding cyber resiliency](/docs/resiliency?topic=resiliency-cyber-resiliency-overview) - Cyber resiliency is part of an organization's ability to prevent, withstand and recover from cybersecurity incidents, including ransomware attacks and other malicious actions.

## Backup
{: #surround-workloads-by-use-case-backup}

The following products or solution guides are available for backup of surround workloads in IBM Cloud:

* SAP HANA Backup using Backint and IBM Cloud Object Storage.
* Cobalt Iron Compass.
* IBM Cloud Backup for VPC.
* IBM Cloud Backup for Classic.
* Portworx PX-Backup.
* FalconStor StorSafe Virtual Tape Library.
* Veeam Kasten.
* TrilioVault for Kubernetes.
* IBM Storage Protect.
* Veeam Backup and Replication.

### SAP HANA Backup using Backint and IBM Cloud Object Storage
{: #surround-workloads-by-use-case-backup-backint}

SAP HANA Backup using Backint and IBM Cloud Object Storage is an automated solution designed for the implementation of an SAP HANA Backup solution using Backint and IBM Cloud Object Storage. The setup runs just onetime initial full data backup to COS for SYSTEM and TENANT databases. The regular backup policy for the databases must be configured by the client. All data backup, log backup and catalog backup files are saved in the same dedicated bucket, with versioning enabled and no enforced storage quota created in an IBM Cloud Object Storage instance by using an existing bastion host with secure remote SSH access in the same IBM Cloud VPC as the SAP HANA system. The storage class for the deployed bucket is a Smart Tier Storage Class with regional resiliency. See [SAP HANA Backup using Backint and IBM Cloud Object Storage](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-sap-vpc-automation-hana-backup-cos-a2a5c6fa-64e8-4907-a88d-f8d38214d218-global/readme/terraform/terraform/f2b8715e-1fd7-45ab-9624-20585d9af619-global) and [Deploying SAP HANA db backup to Cloud Object Storage on existing IBM Cloud VPC with automation](/docs/sap?topic=sap-sap-automate-hana-db-backup-cos-deploy&interface=ui).

### Cobalt Iron Compass
{: #surround-workloads-by-use-case-backup-cobalt}

Cobalt Iron Compass ia a single, unified, SaaS-based offering to backup and restore IBM PowerVS workloads. With IBM Storage Protect, Compass protects a variety of PowerVS platforms, applications, and data classes including AIX, Linux, Oracle on AIX, DB2 on AIX and SAP HANA on Linux. See [Cobalt Iron - Secure Automated Backup with Compass](https://cloud.ibm.com/catalog/services/cobalt-iron---secure-automated-backup-with-compass?catalog_query=aHR0cHM6Ly9jbG91ZC5pYm0uY29tL2NhdGFsb2c%2Fc2VhcmNoPWJhY2t1cCNzZWFyY2hfcmVzdWx0cw%3D%3D#about) and [Backup-as-a-Service for AIX/Linux On Power Virtual Server With Cobalt Iron Compass](/docs/pvs-baas-with-compass?topic=pvs-baas-with-compass-white-paper)

### IBM Cloud Backup for VPC
{: #surround-workloads-by-use-case-backup-vpc}

IBM Cloud Backup for VPC automatically creates backups and manually restores Block Storage for VPC volumes and File Storage for VPC shares from backup snapshots. By using this service, you can prevent data loss, manage risk, and improve data compliance. You can ensure that your data is backed up regularly, and you can retain the backups while you need them. You can create and manage backup policies and plans in the console, from the CLI, with the API, or Terraform. See [About Backup for VPC](/docs/vpc?topic=vpc-backup-service-about&interface=ui),

### IBM Cloud Backup for Classic
{: #surround-workloads-by-use-case-backup-classic}

IBM Cloud Backup for Classic is an automated agent-based multi-tenant backup system that provides users with a method to back up data between servers in one or more data centers on the IBM Cloud. IBM Cloud Backup is an enterprise-level backup storage and disaster recovery solution that is available for local access across globally dispersed data centers. With IBM Cloud Backup, you can add cloud-based backup to any physical, virtual, or hybrid server environment, leverage system image and granular recovery options and restore capabilities for dissimilar hardware, and schedule backups and retention schemes to follow custom timetables or employ the daily, or weekly pre-configured schedules as needed. See [Getting started with IBM Cloud Backup for Classic](/docs/Backup?topic=Backup-getting-started) and [Cloud Backup](https://cloud.ibm.com/cloud-storage/backup/order?catalog_query=aHR0cHM6Ly9jbG91ZC5pYm0uY29tL2NhdGFsb2c%2Fc2VhcmNoPWJhY2t1cCNzZWFyY2hfcmVzdWx0cw%3D%3D).

### Portworx PX-Backup
{: #surround-workloads-by-use-case-backup-portworx}

Portworx PX-Backup delivers enterprise-grade point-and-click backup and recovery protection for all applications running on IBM Kubernetes Service and Red Hat OpenShift on IBM Cloud, even if they are stateless. Built exclusively for containerized applications, Portworx PX-Backup protects your applications - data, application configuration, and Kubernetes objects - with a single click at the Kubernetes Pod, Namespace, or Cluster level. See [PX-Backup for Kubernetes](https://cloud.ibm.com/catalog/services/px-backup-for-kubernetes?catalog_query=aHR0cHM6Ly9jbG91ZC5pYm0uY29tL2NhdGFsb2c%2Fc2VhcmNoPWJhY2t1cCNzZWFyY2hfcmVzdWx0cw%3D%3D#about)

### FalconStor StorSafe Virtual Tape Library
{: #surround-workloads-by-use-case-backup-falconstor}

FalconStor StorSafe Virtual Tape Library (VTL) is a software solution that optimizes backup and restore, to improve performance and significantly reduce backup storage costs. With its integrated deduplication, the solution removes redundant copies of data, thereby reducing capacity requirements, decreasing storage costs, and minimizing replication and restore times. StorSafe VTL can be used with all leading backup solutions, and enables both hybrid and native-cloud backup, as well as both workload and tape migration to the cloud. StorSafe VTL also supports NFS and SMB interfaces in a NAS environment. AIX and Linux systems can use StorSafe as an NFS server for applications such as Oracle RMAN or SAP Hana Studio. You can also store backup files created with the Veeam Agent for IBM AIX on backup repositories managed by Veeam Backup & Replication (VBR). See [FalconStor StorSafe VTL for PowerVS Cloud](https://cloud.ibm.com/catalog/content/vtltile-tags-v10.03-01-f1e88e51-7e3d-4fbc-a7ed-3ab9adb2afea-global#about).

### Veeam Kasten
{: #surround-workloads-by-use-case-backup-kasten}

Veeam Kasten is a Kubernetes-native backup and disaster recovery solution designed to protect, move, and manage containerized applications. On IBM Cloud, Kasten provides robust capabilities to ensure the safety and recoverability of your Kubernetes workloads. IBM Cloud Kubernetes Service (IKS) is a managed Kubernetes service to create your own cluster of compute hosts where you can deploy and manage containerized apps on IBM Cloud. See [Veeam Kasten - Enterprise Data Protection for Kubernetes](https://cloud.ibm.com/catalog/content/k10-8bd412c9-55a6-4ed1-ac85-fef553d91807-global/readme/iks/helm/f2ac708a-6879-44cd-bdcc-ac405d407e8d-global).

### TrilioVault for Kubernetes
{: #surround-workloads-by-use-case-backup-triliovault}

TrilioVault for Kubernetes is a leading provider of cloud-native Data Protection software solutions, supporting private, public and hybrid-clouds, engineered from ground up for Kubernetes, KubeVirt and OpenStack environments. Trilio’s software dramatically reduces the amount of time spent on restoration and migration activities empowering customers from diverse sectors, such as telecommunications, financial services, defense, automotive and healthcare with the ability to easily deploy, manage and scale applications with confidence. See [TrilioVault for Kubernetes](https://cloud.ibm.com/catalog/content/k8s-triliovault-operator-7dbb5777-6b68-4efb-9a93-ec5ade46e293-global#about).


### IBM Storage Protect
{: #surround-workloads-by-use-case-backup-storage-protect}

IBM Storage Protect provides data resilience for physical file servers, virtual environments, and a wide range of applications. Organizations can scale up to manage billions of objects per backup server. Clients can reduce backup infrastructure costs with built-in data efficiency capabilities and the ability to migrate or copy data to tape, public cloud services, and on-premises object storage. IBM Storage Protect can also store IBM Storage Protect Plus data, allowing companies to take advantage of their existing investment for long-term data retention and disaster recovery. See [IBM Storage Protect](https://cloud.ibm.com/catalog/content/SPonIBMCloud-20c54034-d319-48c0-beb6-0b4adc54265c-global#about).

### Veeam Backup and Replication
{: #surround-workloads-by-use-case-backup-veeam-vbr}

Veeam Backup and Replication provides data protection and disaster recovery for virtual, physical, and cloud environments, offering efficient and reliable backup and recovery capabilities. Veeam Backup and Replication lets you deploy and manage the following Veeam Agents on computers in your infrastructure:

* Veeam Agent for Microsoft Windows.
* Veeam Agent for Linux.
* Veeam Agent for IBM AIX.
* Veeam Agent for Oracle Solaris.
* Veeam Agent for Mac.

Additionally Veeam supports the following plug-ins:

* Veeam Plug-in for SAP HANA for x86.
* Veeam Plug-in for SAP HANA for Linux on Power.
* Veeam Plug-in for Oracle RMAN.
* Veeam Plug-in for SAP on Oracle.
* Veeam Plug-in for Microsoft SQL Server.
* Veeam Plug-in for IBM Db2.

Veeam Backup and Replication is available in IBM Cloud in the following environments:

* IBM Cloud for VMware Cloud Foundation Classic Automated - Veeam seamlessly integrates directly with your VMware hypervisors to help your enterprise achieve high availability. This service provides recovery points and time objectives for your applications and data. The recovery points and time objectives can be provided in less than 15 minutes after configuration is completed. By using this service, you control both the backup and restore of all virtual machines (VMs) for your infrastructure directly from the Veeam console. See [Veeam on IBM Cloud overview](/docs/vmwaresolutions?topic=vmwaresolutions-veeamvm_overview).
* IBM Cloud for VMware Cloud Foundation as a Service - The Veeam Backup service is available and ready to use in your IBM Cloud&reg; for VMware Cloud Foundation as a Service instance. This service seamlessly integrates as a managed solution to help your enterprise achieve high availability and provides recovery points for your applications and data. By using this service, you control the backup of all virtual machines (VMs) for your infrastructure directly from the Veeam console. See [Managing Veeam for VCF as a Service](https://cloud.ibm.com/docs/vmware-service?topic=vmware-service-tenant-veeam)
* IBM Cloud VPC - You can use Veeam software to back up your storage data on a virtual server instance for IBM Cloud Virtual Private Cloud. You can use Veeam software backups to protect the following resources individual volumes, folders and files. With the Veeam Agent for Linux&reg; and the Veeam Agent for Microsoft&trade; Windows&trade; you can create backups and perform restores for storage that is attached to an individual virtual server instance. Additionally, with the Veeam Backup and Replication tool for Microsoft Windows, you can manage backup for multiple Linux&reg; and Microsoft Windows virtual server instances through a single interface. See [About Veeam](https://cloud.ibm.com/docs/vpc?topic=vpc-about-veeam).
