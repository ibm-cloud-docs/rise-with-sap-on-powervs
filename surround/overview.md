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

When considering moving your on-premise IBM Power SAP systems to the RISE with SAP on IBM Power Virtual Server service, you also need to consider the surround workloads. The surround workloads communicate and interact with your SAP core systems. The diagram below shows a high-level view of an enterprise.

![Figure 1. Enterprise](../images/enterprise.svg "Enterprise"){: caption="Enterprise" caption-side="bottom"}

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
* non-RISE non-SAP - These are workloads that are not SAP and provide services such as international tax codes, custom pricing rules, custom product, configuration engines, document storage etc.

## Non-RISE SAP surround workloads
{: #surround-overview-non-rise}

Non-RISE SAP® surround workloads are those workloads that currently reside alongside your on-premise SAP systems hosted on {{site.data.keyword.IBM}} Power that you intend to migrate to RISE with SAP on {{site.data.keyword.powerSysFull}}.

![Figure 1. Non-RISE SAP surround workloads](../images/non-rise.svg "Non-RISE SAP surround workloads"){: caption="Non-RISE SAP surround workloads" caption-side="bottom"}

## Non-RISE non-SAP surround workloads
{: #surround-overview-non-rise-non-sap-surround-workloads}

Surround non-RISE non-SAP® workloads are those workloads that currently reside alongside your on-premise SAP systems hosted on {{site.data.keyword.IBM}} Power that you intend to migrate to IBM Cloud because they are tightly coupled to your SAP systems hosted in RISE with SAP on IBM Power Virtual Server.

![Figure 1. Non-RISE non-SAP surround workloads](../images/non-sap.svg "Non-RISE non-SAP surround workloads"){: caption="Non-RISE non-SAP surround workloads" caption-side="bottom"}

## Surround workload coupling
{: #surround-overview-coupling}

Additionally, it is imperative to understand how the non-RISE SAP and non-RISE non-SAP surround workloads are coupled with the on-premise IBM Power SAP systems you are proposing to migrate to the RISE with SAP on IBM Power Virtual Server service. In this document we will classify these surround workloads as:

* Tightly coupled - Tightly coupled workloads require low latency connections to your SAP systems or require high bandwidth connections.
* Loosely coupled - Loosely coupled workloads do not need high bandwidth connectivity or low latency between the surround workload and the SAP system.

![Figure 3. Coupled Surround Workloads](../images/coupled-surround.svg "Coupled Surround Workloads"){: caption="Coupled Surround workloads" caption-side="bottom"}

### Tightly coupled surround workloads
{: #surround-overview-tightly-coupled-surround-workloads}

As tightly coupled workloads require low latency connections to your SAP systems or require high bandwidth connections, then they are probably colocated in the same data center as your SAP workloads. Therefore, when considering moving your SAP systems to RISE with SAP on IBM Power Virtual Server service, you should consider moving these tightly coupled surround workloads to IBM Cloud. These tightly coupled surround workloads may be IBM Power, x86, virtualized or containerized workloads.

These surround workloads cannot be hosted in the SAP owned RISE with SAP on IBM Power Virtual Server IBM Account, however, they can be migrated to your IBM Cloud account and peered with the SAP owned RISE with SAP on IBM Power Virtual Server IBM Account.

![Figure 2. Peering](../images/peering.svg "Peering"){: caption="peering" caption-side="bottom"}

### Loosely coupled surround workloads
{: #surround-overview-loosely-coupled-surround-workloads}

As loosely coupled workloads do not need high bandwidth connectivity or low latency between the surround workload and your SAP systems, then these workloads may already be delivered from a cloud provider using IaaS, PaaS or SaaS delivery models. These loosely coupled workloads may also be hosted in your data centers, a colocation facility or in a service provider's data center.
