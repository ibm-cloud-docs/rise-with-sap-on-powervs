---

copyright:
  years: 2025
lastupdated: "2026-04-02"

keywords: SAP, RISE, PowerVS, RISE with SAP on PowerVS, SAP on IBM Cloud, Benefits of RISE with SAP on IBM Cloud, IBM Power Virtual Server, SAP modernization

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Overview
{: #integration-overview}

With RISE with SAP on {{site.data.keyword.powerSysFull}}, the SAP&reg; Enterprise Cloud Services (ECS) team manages the SAP systems, however, it is your responsibility to establish network connectivity and domain name server (DNS) resolution to RISE with SAP on {{site.data.keyword.powerSysFull}}. IBM recommends that you consult with your SAP representative to understand the available options on how to connect your on-premises networks and your IBM Cloud Account networks to the RISE with SAP on {{site.data.keyword.powerSysFull}} networks.
{: shortdesc}

This document explains the concepts and best practices to follow for a performant and secure solution to connect your networks with the RISE with SAP on IBM {{site.data.keyword.powerSysFull}} networks.

The term **surround workloads** is used to define a workload that integrates with your SAP system hosted in RISE with SAP on {{site.data.keyword.powerSysFull}}. These surround workloads can be non-RISE SAP or non-RISE non-SAP workloads. These surround workloads can be hosted:

* **Internet** - These are typically SaaS based services, such as SAP Business Technology Platform (BTP) to which connections can be established only through Internet.
* **On-premises** - These surround workloads are typically loosely coupled workloads that do not require high bandwidth or low latency connections.
* **IBM Cloud** - These surround workloads are located in IBM Cloud, they can be hosted in one of the three IBM Cloud infrastructure environments; IBM Cloud Classic, IBM Cloud VPC or IBM {{site.data.keyword.powerSysFull}} in IBM data center.
* **On another cloud** - These surround workloads are located and hosted in other clouds and accessed through private networks.

While your RISE with SAP on IBM {{site.data.keyword.powerSysFull}} workloads are running in the SAP IBM Cloud Account, your IBM Cloud surround workloads run in your own IBM Cloud Account and connectivity must be established between these two.
{: note}


## RISE with SAP on IBM {{site.data.keyword.powerSysFull}} inter-connectivity options
{: #integration-overview-arch-connectivity}

The diagram below shows the inter-connectivity options provided by RISE with SAP on IBM {{site.data.keyword.powerSysFull}}.

![Figure 1. Inter-connectivity](../images/interconnectivity.svg "Inter-connectivity"){: caption="Inter-connectivity" caption-side="bottom"}

The connections to RISE with SAP on IBM {{site.data.keyword.powerSysFull}} are defined as follows:

* **Internet to RISE with SAP on IBM {{site.data.keyword.powerSysFull}}** - This connectivity provides application access to and from the Internet. The Internet connection allows the use SAP Cloud Connector, for example.
* **On-premises to RISE with SAP on IBM {{site.data.keyword.powerSysFull}}** - This connection connects your user/workloads on-premises or other non-IBM Cloud locations to the RISE with SAP on IBM {{site.data.keyword.powerSysFull}} service. This connectivity is defined by you and SAP, and can be one of the following types:
    * Site-to-site IPsec VPN
    * Direct Link
* **Peering - IBM Cloud to RISE with SAP on IBM {{site.data.keyword.powerSysFull}}** - This connectivity provides access between resources in your IBM Cloud account and your resources in RISE with SAP on IBM {{site.data.keyword.powerSysFull}}. There is also a variant of this connectivity type where your IBM Cloud account is a hub that connects to your on-premises or external locations and your IBM Cloud resources, including your surround workloads, to RISE with SAP on IBM {{site.data.keyword.powerSysFull}}.
* **Multi-cloud with RISE with SAP on IBM {{site.data.keyword.powerSysFull}}** - This connectivity option allows you to connect to other cloud providers, such as AWS or Azure. From the technical perspective, this option is similar to the peering or on-premises connectivity options, but the use case is slightly different.

This section provides a high level overview about the connectivity options and other considerations related to IP addressing and domain name server (DNS) resolution aspects.
