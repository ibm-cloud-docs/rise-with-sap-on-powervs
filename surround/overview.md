---

copyright:
  years: 2025
lastupdated: 2025-02-07

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Overview
{: #surround-overview}

When considering moving your on-premise IBM Power SAP systems to the RISE with SAP on IBM Power Virtual Server service, you also need to consider the surround workloads. The surround workloads communicate and interact with your SAP core systems. The diagram below shows a high-level view of a typical application landscape in an enterprise.

![Figure 1. Enterprise](../images/enterprise.svg "Enterprise"){: caption="Enterprise" caption-side="bottom"}

The SAP Core systems are the candidates for the RISE with SAP on IBM Power Virtual Server, while the surround workloads can be categorized as follows:

* non-RISE SAP - These SAP Surround workloads are not suitable to be migrated to RISE with SAP Power Virtual Server. Examples include the following:
    * SAP CRM - SAP CRM (Customer Relationship Management) is considered as legacy and replaced by the SaaS service Customer Experience.
    * SAP SRM - SAP SRM (Supplier Relationship Management) is considered as legacy and replaced by the SaaS service Ariba.
    * SAP ECC - SAP ECC (ERP Central Component) systems that are not being migrated to RISE with SAP Power Virtual Server.
    * SAP HR - SAP SRM (Supplier Relationship Management) is considered as legacy and replaced by the SaaS service SuccessFactors.
    * SAP PI - SAP PI (NetWeaver Process Integration) is SAP enterprise application integration (EAI) software, a component of the NetWeaver product group used to facilitate the exchange of information among a company's internal software and systems and those of external parties.
    * SAP PO - SAP PO (Process Orchestration) is a tool that makes it easy to synchronize data between different systems to automate and optimize business processes. PO has all the functionality of SAP PI in a single Java stack plus unified features such as Business Rule Management (BRM), Business Process Management (BPM), Enterprise Service Repository (ESR), B2B Collaboration and cloud integration, and for application integration.
    * SAP GTS - SAP GTS (Global Trade Services) is software that allows organizations to support and define import and export trade processes in SAP ERP. GTS reduces the time and costs of complying with global trade regulations and provides visibility into the supply chain while goods are in transit.
* non-RISE non-SAP - These workloads are not running SAP applications and provide services such as international tax codes, custom pricing rules, custom product, configuration engines, document storage etc.

## Non-RISE SAP surround workloads
{: #surround-overview-non-rise}

Non-RISE SAP® surround workloads are those workloads that currently reside alongside your on-premise SAP systems hosted on {{site.data.keyword.IBM}} Power that you intend to migrate to RISE with SAP on {{site.data.keyword.powerSysFull}}.

![Figure 1. Non-RISE SAP surround workloads](../images/non-rise.svg "Non-RISE SAP surround workloads"){: caption="Non-RISE SAP surround workloads" caption-side="bottom"}

## Non-RISE non-SAP surround workloads
{: #surround-overview-non-rise-non-sap-surround-workloads}

Surround non-RISE non-SAP® workloads are those workloads that currently reside alongside your on-premise SAP systems hosted on {{site.data.keyword.IBM}} Power that you intend to migrate to IBM Cloud because they are tightly coupled to your SAP systems hosted in RISE with SAP on IBM Power Virtual Server.

![Figure 2. Non-RISE non-SAP surround workloads](../images/non-sap.svg "Non-RISE non-SAP surround workloads"){: caption="Non-RISE non-SAP surround workloads" caption-side="bottom"}

## Surround workload coupling
{: #surround-overview-coupling}

Additionally, it is imperative to understand how the non-RISE SAP and non-RISE non-SAP surround workloads are coupled with the on-premise IBM Power SAP systems that you are considering to migrate to the RISE with SAP on IBM Power Virtual Server service and how they will integrate post migration/transition. In this document we will classify these surround workloads as:

* Tightly coupled - Tightly coupled workloads require low latency connections to your SAP systems or require high bandwidth connections.
* Loosely coupled - Loosely coupled workloads do not need high bandwidth connectivity or low latency between the surround workload and the SAP system.

![Figure 3. Coupled Surround Workloads](../images/coupled-surround.svg "Coupled Surround Workloads"){: caption="Coupled Surround workloads" caption-side="bottom"}

### Tightly coupled surround workloads
{: #surround-overview-tightly-coupled-surround-workloads}

As tightly coupled workloads require low latency connections to your SAP systems or require high bandwidth connections, then they are probably colocated in the same data center as your SAP workloads. Therefore, when considering moving your SAP systems to RISE with SAP on IBM Power Virtual Server service, you should consider moving these tightly coupled surround workloads to IBM Cloud. These tightly coupled surround workloads may be IBM Power, x86, virtualized or containerized workloads.

As these surround workloads cannot be hosted in the SAP owned RISE with SAP on IBM Power Virtual Server IBM Account, the diagram below, shows how they can be migrated to one of the following three infrastructure environments in your IBM Cloud account and peered with the SAP owned RISE with SAP on IBM Power Virtual Server IBM Account:

* Virtual Private Cloud (VPC) - IBM Cloud Virtual Private Cloud (VPC) is a highly resilient and highly secure software-defined network (SDN) on which you can build isolated private clouds for your business operations while maintaining essential public cloud benefits. See [IBM Cloud VPC Solutions](https://www.ibm.com/cloud/vpc) and [IBM Cloud® Virtual Private Cloud (VPC) Infrastructure environment introduction](/docs/sap?topic=sap-vpc-env-introduction).
* Power Virtual Server - IBM Power Virtual Server is a family of configurable, multi-tenant, virtual IBM Power servers with access to IBM Cloud services. See [IBM Power Virtual Server](https://www.ibm.com/products/power-virtual-server) and [IBM Power Systems Infrastructure environment introduction](/docs/sap?topic=sap-power-env-introduction).
* Classic Infrastructure - The classic infrastructure IaaS platform leverages a traditional network architecture, best suited for lift and shift workloads so you can move applications quickly and keep the same architecture. See [IBM Cloud Bare Metal Servers on Classic Infrastructure](https://www.ibm.com/products/bare-metal-servers/classic?mhsrc=ibmsearch_a&mhq=classic%20infrastructure%20-%20ibm%20cloud), [IBM Cloud Virtual Servers on IBM Cloud Classic Infrastructure](https://www.ibm.com/products/virtual-servers-classic) and [Classic Infrastructure environment introduction](/docs/sap?topic=sap-classic-env-introduction).

![Figure 3. Peering](../images/peering.svg "Peering"){: caption="peering" caption-side="bottom"}

### Loosely coupled surround workloads
{: #surround-overview-loosely-coupled-surround-workloads}

As loosely coupled workloads do not need high bandwidth connectivity or low latency between the surround workload and your SAP systems, then these workloads may already be delivered from a cloud provider using IaaS, PaaS or SaaS delivery models. These loosely coupled workloads may also continue to be hosted in your data centers, a colocation facility or in a service provider's data center. Alternatively, if feasible you may consider transitioning these workloads to IBM cloud as well. 
