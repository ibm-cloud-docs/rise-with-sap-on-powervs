---

copyright:
  years: 2025
lastupdated: "2026-04-27"

keywords: SAP, RISE, PowerVS, RISE with SAP on PowerVS, {{site.data.keyword.ibm_cloud_sap}}, Architecture diagram of RISE with SAP on IBM Power Virtual Server, IBM {{site.data.keyword.powerSys_notm}}, SAP modernization

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Reference Architecture
{: #reference-architecture}

## Overview
{: #reference-architecture-overview}

Using {{site.data.keyword.powerSysFull}}, the cloud-based version of the mission-critical IBM Power server platform used for on-premises enterprise resource planning (ERP), you can rapidly transform on-premises SAP ERP systems, modernize business processes and become more agile. Known for its high security, scalability and reliability, IBM Power servers are engineered for fewer disruptions and facilitates faster migration, supported by the highly resilient and secured IBM Cloud platform.
{: shortdesc}

SAP Cloud ERP Private is the software in the RISE with SAP on IBM {{site.data.keyword.powerSys_notm}} service that holds the client’s mission critical data and business processes. SAP provides a managed private environment with multi-layer defense in depth architecture handling infrastructure and technical managed services in line with their service level agreement (SLA).

![Figure 1. RISE with SAP on IBM Power Virtual Server Overview](../images/architecture-overview.svg "RISE with SAP on IBM Power Virtual Server Overview"){: caption="RISE with SAP on IBM {{site.data.keyword.powerSys_notm}} Overview" caption-side="bottom"}

SAP Cloud ERP Private Edition is a single-tenant managed private environment for clients where SAP creates a separate IBM Cloud Account in their IBM Cloud Enterprise Account for each customer. The application and database virtual server instances are solely dedicated to a single client.

SAP creates and manages the entire RISE with SAP on IBM IBM {{site.data.keyword.powerSys_notm}} architecture running in an IBM Cloud Enterprise Account owned by SAP. SAP defines, validates and deploys all technical resources deployed in this IBM Cloud Enterprise Account.

Clients of RISE with SAP on IBM IBM {{site.data.keyword.powerSys_notm}} do not get access to the SAP IBM Cloud Enterprise Account. The SAP IBM Cloud Enterprise Account and all the resources within it are visible to and managed by SAP only.
