---

copyright:
  years: 2025
lastupdated: 2025-02-07

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Overview
{: #overview}

This document provides an overview of the following:

* RISE with SAP - The SAP® managed cloud service that helps organizations to migrate to the SAP Cloud, securely and smoothly.
* RISE with SAP on {{site.data.keyword.powerSysFull}} - The SAP managed cloud service hosted on the cloud-based version of IBM Power server platform.
* Surround workloads - Workloads that communicate and interact with the SAP systems that will be migrated to RISE with SAP on IBM Power Virtual Server. These surround workloads can be migrated to your IBM Cloud Account and peered with the SAP Systems hosted in the RISE with SAP on IBM Power Virtual Server Cloud Account.
* Surround workload migration - High-level advice and guidance on the approach to migrating surround workloads.

## RISE with SAP
{: #overview-rise-with-sap}

The RISE with SAP offering is a SAP® managed cloud service that helps organizations using on-premise ERP software, that includes including SAP ERP, SAP ECC, and SAP S/4HANA, to migrate to the SAP Cloud, securely and smoothly. RISE with SAP is tailored to help larger enterprises migrate their existing ERP data, processes, and capabilities to SAP S/4HANA Cloud Private Edition.

RISE with SAP is a fully accredited cloud infrastructure with managed services that include technical system operations, software support, and security services based on best-practice cloud architecture, and includes management of the operating system, SAP HANA database, and SAP S/4HANA Cloud Private Edition application.

RISE with SAP:

* is a single contract with a unified service-level agreement (SLA) for the entire solution stack, helping ensure consistent service quality across all components, simplifying procurement and management.
* includes ongoing support and maintenance for the entire solution stack, including infrastructure, platform, and application layers using certified subject-matter experts who handle operating system management tasks, such as patches, monitoring, and maintenance.
* has the ability to scale up or down as needed with flexible pricing based on usage and consumption.
* has enhanced security and compliance features with built-in controls and monitoring to help protect data and meet regulatory requirements.
* enables integration with SAP Business Technology Platform, which provides advanced analytics, AI, and machine learning capabilities to help businesses make data-driven decisions and improve operational efficiency
* encompasses partners and developers that provide a wide range of complementary solutions and services that enhance the RISE with SAP offering.

See [RISE with SAP](https://www.sap.com/uk/products/erp/rise.html?gclsrc=aw.ds&gad_source=1&gbraid=0AAAAAoV5MAX5yS4NBq8up4zvuErMQIF-Z&gclid=Cj0KCQiA4-y8BhC3ARIsAHmjC_HSyZuyRqHhIBD6sHB0YK_splrNwnJxGbHB_82swpzRbvCCVq3pAxwaAmOtEALw_wcB){: external}.

## RISE with SAP on IBM Power Virtual Server
{: #overview-rise-with-sap-power-vs}

Using {{site.data.keyword.powerSysFull}}, the cloud-based version of the mission-critical IBM Power server platform used for on-premises Enterprise Resource Planning (ERP), you can rapidly transform on-premises SAP ERP systems, modernize business processes and become more agile. Known for its high security, scalability and reliability, IBM Power servers are engineered for fewer disruptions and faster migration, supported by the highly resilient and secured IBM Cloud platform.

SAP S/4HANA Cloud Private Edition is the software in the RISE with SAP on IBM Power Virtual Server service that holds the client’s mission critical data and business processes. SAP Enterprise Cloud Services (ECS) provides a managed private environment with multi-layer defense in depth architecture handling infrastructure and technical managed services in line with their Service Level Agreement (SLA).

SAP S/4HANA Cloud Private Edition is a single-tenant managed private environment for clients where SAP creates a separate account IBM Cloud Account in their IBM Cloud Enterprise Account for each customer. The application and database virtual server instances are solely dedicated to a single client.

It is the client's responsibility to ensure secure connectivity to RISE with SAP on IBM Power Virtual Server. There are essentially four different ways to connect to the service and the client can select the connections based on their specific requirements on security, compliance, bandwidth, and cost:

1. IPsec VPN - The client and SAP will configure the encryption parameters and authentication details for the VPN gateways to establish a secure IPsec tunnel.
2. Dedicated Private Connection - While many clients rely on Internet services, some clients may prefer a dedicated private connection to the RISE with SAP on IBM Power Virtual Server environment for added security and compliance when accessing their business processes and applications. IBM Cloud Direct Link and Direct Link Connect facilitate these dedicated private connections. Direct Link Connect in association with a Cloud Exchange Provider, provides access to other cloud providers, on-premise connections and SAP Cloud peering. SAP Cloud Peering is a reliable and secure connectivity option for client to SAP Cloud Services leveraging SAP’s global interconnection provider ecosystem. SAP Cloud Peering provides a secure connectivity option, because the traffic traverses the Cloud Exchange Provider's network, to connect to SAP SuccessFactors, SAP Ariba, SAP BTP, SAP Concur and more SAP solutions.
3. Peering - Many clients using RISE with SAP on IBM Power Virtual Server may have an existing IBM Cloud Account, where they are hosting their own applications. As a part of integration, a secure connection is needed between the client IBM Cloud Account and the RISE with SAP on IBM Power Virtual Server IBM Cloud Account managed by SAP ECS. In IBM Cloud peering is facilitated by Transit Gateway cross-account connections.
4. Internet - Some clients may want to access RISE with SAP on IBM Power Virtual Server via via the Internet directly. This can be allowed via traffic traversing via the IBM Cloud Internet Services (CIS) Web Application Firewall (WAF). For inbound Internet connection, only HTTPS/TLS1.2 is allowed. 

The high-level RISE with SAP on IBM Power Virtual Server is shown in the diagram below along with the connectivity options.

![Figure 1. RISE with SAP on IBM Power Virtual Server Overview](../images/overview.svg "RISE with SAP on IBM Power Virtual Server Overview"){: caption="RISE with SAP on IBM Power Virtual Server Overview" caption-side="bottom"}

## Surround workloads
{: #overview-surround-workloads}

When considering moving your on-premise IBM Power SAP systems to the RISE with SAP on IBM Power Virtual Server service, you also need to consider the surround workloads. The surround workloads communicate and interact with your SAP core systems. The diagram below shows a high-level view of an enterprise.

![Figure 2. Enterprise](../images/enterprise.svg "Enterprise"){: caption="Enterprise" caption-side="bottom"}

The SAP Core systems are the candidates for the RISE with SAP on IBM Power Virtual Server, and the surround workloads are  
These surround workloads can be categorized as follows:

* non-RISE SAP - These SAP Surround workloads are not suitable to be migrated to RISE with SAP Power Virtual Server. Examples include the following:
    * SAP CRM - SAP CRM (Customer Relationship Management) is considered as legacy and replaced by the SaaS service Customer Experience.
    * SAP SRM - SAP SRM (Supplier Relationship Management) is considered as legacy and replaced by the SaaS service Ariba.
    * SAP ECC - SAP ECC (ERP Central Component) systems that are not being migrated to RISE with SAP Power Virtual Server.
    * SAP HR - SAP SRM (Supplier Relationship Management) is considered as legacy and replaced by the SaaS service SuccessFactors.
    * SAP PI - SAP PI (NetWeaver Process Integration) is SAP enterprise application integration (EAI) software, a component of the NetWeaver product group used to facilitate the exchange of information among a company's internal software and systems and those of external parties.
    * SAP PO - SAP PO (Process Orchestration) is a tool that makes it easy to synchronize data between different systems to automate and optimize business processes. PO has all the functionality of SAP PI in a single Java stack plus unified features such as Business Rule Management (BRM), Business Process Management (BPM), Enterprise Service Repository (ESR), B2B Collaboration and cloud integration, and for application integration.
    * SAP GTS - SAP GTS (Global Trade Services) is software that allows organizations to support and define import and export trade processes in SAP ERP. GTS reduces the time and costs of complying with global trade regulations and provides visibility into the supply chain while goods are in transit.
* non-RISE non-SAP - These are workloads that are not SAP and provide services such as international tax codes, custom pricing rules, custom product, configuration engines, document storage etc. Examples include the following:
    * webMethods
    * Redwood Software
    * Salesforce
    * Workday
    * SAS Institute
    * Sage Group
    * Citrix
    * Dassault Systèmes
    * Tableau
    * Automattic
    * Atlassian
    * MicroStrategy
    * Actian/HCL
    * Teradata
    * Infor
    * TIBCO Software
    * Informatica
    * ADP Payroll and HR software
    * Ultimate Kronos Software Group
    * Ceridian software
    * Honeywell Productivity Solutions

Additionally, it is imperative to understand how the non-RISE SAP and non-RISE non-SAP surround workloads are coupled with the on-premise IBM Power SAP systems you are proposing to migrate to the RISE with SAP on IBM Power Virtual Server service. In this document we will classify these surround workloads as:

* Tightly coupled - Tightly coupled workloads require low latency connections to your SAP systems or require high bandwidth connections.
* Loosely coupled - Loosely coupled workloads do not need high bandwidth connectivity or low latency between the surround workload and the SAP system.

![Figure 3. Coupled Surround Workloads](../images/coupled-surround.svg "Coupled Surround Workloads"){: caption="Coupled Surround workloads" caption-side="bottom"}

### Tightly coupled surround workloads
{: #overview-tightly-coupled-surround-workloads}

As tightly coupled workloads require low latency connections to your SAP systems or require high bandwidth connections, then they are probably colocated in the same data center as your SAP workloads. Therefore, when considering moving your SAP systems to RISE with SAP on IBM Power Virtual Server service, you should consider moving these tightly coupled surround workloads to IBM Cloud. These tightly coupled surround workloads may be IBM Power, x86, virtualized or containerized workloads.

### Loosely coupled surround workloads
{: #overview-loosely-coupled-surround-workloads}

As loosely coupled workloads do not need high bandwidth connectivity or low latency between the surround workload and your SAP systems, then these workloads may already be delivered from a cloud provider using IaaS, PaaS or SaaS delivery models. These loosely coupled workloads may also be hosted in your data centers, a colocation facility or in a service provider's data center.

## Surround workload migration
{: #overview-surround-workload-migration}

When approaching the migration of your surrounding workloads, it is helpful to understand the migration timeline and classify each of the surround workloads as a tactical or strategic migration:

* Tactical - In the tactical approach, the surround workload needs to be migrated in the same time frame as your SAP systems in RISE with SAP on IBM Power Virtual Server.
* Strategic - In the strategic approach, the surround workload does not need to be migrated in the same time frame as your SAP systems in RISE with SAP on IBM Power Virtual Server. The timeline is then governed by you business needs and requirements rather than the migration of your SAP systems.

In addition, classify the workloads into:

* Non-RISE SAP - These workloads are SAP systems that cannot be migrated to RISE with SAP Power Virtual Server because the are not SAP ERP, SAP ECC, or SAP S/4HANA. Many of these workloads can move to IBM Cloud and be hosted in your IBM Cloud Account. See [IBM Cloud for SAP and IBM Power Virtual Servers for SAP](https://cloud.ibm.com/docs/sap).
* Non-RISE non-SAP - These workloads are not SAP systems and cannot move to RISE with SAP. Many of these workloads can move to IBM Cloud and be hosted in your IBM Cloud Account. See [IBM Cloud Solution Library](https://cloud.ibm.com/docs?tab=solutions).

### Migration strategy
{: #overview-surround-workload-migration-strategy}

If the surround workload has been classified as tactical then it important to consider the strategy of achieving the migration in the timeline. These cloud migration strategies include re-hosting, re-platforming, refactoring, repurchasing and retiring.

* Re-hosting - Re-hosting, also known as Lift and Shift, involves moving applications from your on-premises environment to the cloud without making significant changes. An example is moving from on-premise VMware to [IBM Cloud for VMWare Solutions](https://www.ibm.com/products/vmware)
* Re-platforming - With a re-platforming migration, some adjustments or optimizations are made to the applications before moving them to the cloud. An example of this strategy is moving a VMware VM to run on [IBM Cloud Virtual Server for VPC](https://www.ibm.com/products/virtual-servers).
* Refactoring - Refactoring involves modifying or redesigning applications to fully leverage cloud-native features. This migration type often involves breaking down monolithic applications into microservices, making them more scalable in the cloud environment. Migrating applications to run on [IBM Cloud Kubernetes Services](https://www.ibm.com/products/kubernetes-service) or [Red Hat OpenShift on IBM Cloud](https://www.ibm.com/products/openshift)
* Repurchasing - Repurchasing involves retiring an existing application and replacing it with a SaaS alternative. Instead of migrating the application to the cloud, businesses opt for a cloud-based SaaS solution that meets their needs. An example may be [IBM MQ SaaS](https://www.ibm.com/products/mq/saas)
* Retiring - Retiring involves decommissioning outdated or unused applications as part of the migration process. This helps in reducing maintenance costs and eliminating redundant resources.

For surround workloads that have been classified as strategic, the same strategies apply, however, the decision on the selection of the strategy can be taken at a later date inline with your timeline.

There is a lot of documented migration strategies available, for example see [What is cloud migration?](https://www.ibm.com/think/topics/cloud-migration) and [Lift and shift VMware on-premises to IBM Cloud](https://cloud.ibm.com/docs/pattern-migration-options-vmware-workloads?topic=pattern-migration-options-vmware-workloads-whitepaper). The short blog, [Cloud migration best practices: Optimizing your cloud migration strategy](https://www.ibm.com/think/insights/cloud-migration-strategy), describes how IBM Turbonomic can simulate the migration of on-premises virtual machines (VMs) to the cloud, or the migration of VMs from one cloud provider to another, focusing on performance and cost optimization. The blog provides some insight on the following topics:

* Why migrate to the cloud?
* Types of cloud migration.
* Cloud migration strategies.
* Common cloud migration challenges.

### Migration program
{: #overview-surround-workload-migration-program}

The move of the surround workload is supported by your migration program. An example of a migration program may include 5 phases: Discovery, Assessment, Minimum Viable Product (MVP), Migration, and Operate.

* Phase 1: Discovery - Data is collected across technical, sales, and business teams to understand the motivation and internal factors driving the move to cloud. Identify priorities such as scalability, solving functional issues, lack of in-house skills, reducing infrastructure, and IT expenses. Identify and document current infrastructure, applications, relationships, and dependencies including drift from the expected business required state.
* Phase 2: Assessment - Data that is collected in the discovery phase is used to assess the migration to cloud viability to and choosing the right target platform solution. Right-size the target environment and take advantage of cloud elasticity. The outcome of the assessment phase is a high-level architecture of the cloud environments with an associated bill of materials. See [IBM Turbonomic](https://www.ibm.com/products/turbonomic)
* Phase 3: Minimum Viable Product (MVP) - Provides the confidence in the viability of the proposed solution. It is important to clearly define and articulate upfront the success criteria of the MVP as well as to identify the approving stakeholders. The successful MVP builds trust and confidence in the solution and provides the go ahead for the migration of the surround workload. The MVP familiarizes your operations team with the cloud platform and guides towards a smooth adoption.
* Phase 4: Migration - The surround workloads are migrated to cloud. The duration of the migration phase depends on the complexity and criticality of the surround workload. [IBM Technology Expert Labs](https://www.ibm.com/products/expertlabs) includes accelerator services to migrate workloads to IBM Cloud.
* Phase 5: Operate: Refers to tooling and processes to maintain the surround workload operational after the migration to IBM Cloud and leveraging cloud services. IBM Cloud services arranged by key operational processes includes:
    * Backup - [IBM Cloud Backup](https://www.ibm.com/products/backup), [Veeam on IBM Cloud](https://www.ibm.com/products/veeam), [Backup-as-a-Service for AIX/Linux On Power Virtual Server With Cobalt Iron Compass](https://cloud.ibm.com/docs/pvs-baas-with-compass?topic=pvs-baas-with-compass-white-paper) 
    * Observability - [IBM Cloud Logs](https://www.ibm.com/products/cloud-logs), [IBM Cloud Monitoring](https://www.ibm.com/products/cloud-monitoring) 
    * Compliance. - [IBM Security and Compliance Center](https://www.ibm.com/products/security-and-compliance-center), [Getting started with IBM Cloud Security and Compliance Center Workload Protection](https://cloud.ibm.com/docs/workload-protection?topic=workload-protection-getting-started), [Caveonix RiskForesight on IBM Cloud overview](https://cloud.ibm.com/docs/workload-protection?topic=workload-protection-getting-started)

### Post migration
{: #overview-surround-workload-migration-strategy-post-migration}

The diagram below illustrates the post-migration state of your SAP systems and surround workloads after adopting the migration strategy and migration program described above.

![Figure 4. Post Migration Surround Workloads](../images/surround-post.svg "Post Migration Surround Workloads"){: caption="Post Migration Surround workloads" caption-side="bottom"}

* Your SAP systems have migrated to RISE for SAP on Power Virtual Server.
* Your non-RISE SAP surround workloads have migrated to IBM Cloud and hosted in your own IBM Cloud Account.
* Your non-RISE non-SAP surround workloads have also migrated to either IBM Cloud or to other clouds.
* Your designated strategic loosely coupled surround workloads remain in your data centers awaiting migration according to your timeline.
