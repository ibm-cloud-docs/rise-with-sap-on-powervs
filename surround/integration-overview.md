---

copyright:
  years: 2025
lastupdated: 2025-03-17

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Overview
{: #integration-overview}

With RISE with SAP on {{site.data.keyword.powerSysFull}}, the SAP® Enterprise Cloud Services (ECS) team manages the SAP systems, however, it is your responsibility to establish network connectivity to RISE with SAP on Power Virtual Server. IBM recommends that you consult with your SAP representative to understand the available options on how to connect your on-premises networks and your IBM Cloud Account networks to the RISE with SAP on Power Virtual Server networks.

This document explains the concepts and best practices to follow for a performant and secure solution to connect your networks with the RISE with SAP on IBM Power Virtual Server networks.

In this document the term **surround workloads** is used to define a workload that integrates with your SAP system hosted in RISE with SAP on Power Virtual Server. These surround workloads can be non-RISE SAP or non-RISE non-SAP workloads. These surround workloads can be hosted:

* On-premises - These surround workloads are typically loosely coupled workloads that do not require high bandwidth or low latency connections.
* Internet - Typically SaaS based services.
* On another cloud - Your workloads or SaaS based services.
* IBM Cloud - your IBM Cloud workloads, hosted in one of the three IBM Cloud infrastructure environments; IBM Cloud Classic, IBM Cloud VPC or IBM Power Virtual Server in IBM data center.

While your RISE with SAP on IBM Power Virtual Server workloads are running in the SAP IBM Cloud Account, your IBM Cloud surround workloads run in your own IBM Cloud Account.

## Virtual Private Cloud
{: #integration-overview-arch-vpc}

A Virtual Private Cloud (VPC) provides network isolation and security in the IBM Cloud. See [Virtual Private Cloud Overview]( /docs/vpc?topic=vpc-about-vpc). A VPC can be a logical container for an enterprise division's resources e.g. marketing, development, or accounting or a collection of resources operated by an enterprise team. VPCs can be connected to an enterprise's locations, to each other and VPCs in other IBM Cloud accounts.

With IBM Cloud Transit Gateway, you can define and control communication between resources hosted in the IBM Cloud infrastructure environments and/or on-premise networks. See [Getting started with IBM Cloud Transit Gateway](/docs/transit-gateway?topic=transit-gateway-getting-started). The IBM Cloud infrastructure environments are:

* IBM Cloud VPC.
* IBM Cloud Classic infrastructure.
* Power Virtual Server workspaces.

## Transit Gateway
{: #integration-overview-arch-tgw}

With an IBM Cloud Transit Gateway, you can connect:

* VPCs in your account or a different account.
* IBM Cloud classic infrastructure in your account or a different account.
* Direct Link in your account or a different account.
* IBM PowerVS in IBM data center in your account or a different account.
* Unbound Generic Routing Encapsulation (GRE) tunnels allow a connection between a zone and an endpoint in IBM Cloud Classic in your account or a different account.
* Redundant Generic Routing Encapsulation (GRE) tunnels allow a connection between two zones and an endpoint in IBM Cloud Classic or a VPC in your account or a different account.

## RISE with SAP on IBM Power Virtual Server inter-connectivity
{: #integration-overview-arch-connectivity}

The diagram below shows the inter-connectivity options provided by RISE with SAP on IBM Power Virtual Server.

![Figure 1. Inter-connectivity](../images/interconnectivity.svg "Inter-connectivity"){: caption="Inter-connectivity" caption-side="bottom"}

The connections to RISE with SAP on IBM Power Virtual Server are defined as follows:

* On-premises to RISE with SAP on IBM Power Virtual Server - This connection connects your user/workloads on-premises or other non-IBM Cloud locations to the RISE with SAP on IBM Power Virtual Server service. This connectivity is defined by you and SAP and can be one of the following types:
    * Site-to-site IPsec VPN.
    * Direct Link.
* Internet to RISE with SAP on IBM Power Virtual Server - This connectivity provides application access from the Internet.
* Peering - IBM Cloud to RISE with SAP on IBM Power Virtual Server - This connectivity provides access between resources in your IBM Cloud account and your resources in RISE with SAP on IBM Power Virtual Server. There is also a variant of this connectivity type where your IBM Cloud account is a hub that connects to your on-premise or external locations and your IBM Cloud resources, including your surround workloads, to RISE with SAP on IBM Power Virtual Server.

These documents define the following integration patterns:

* [IBM Cloud integration](/docs/rise-with-sap-on-powervs?topic=rise-with-sap-on-powervs-integration-ibm-cloud) - Integrating RISE with SAP on IBM Power Virtual Server with your non-RISE SAP and non-RISE non-SAP workloads in IBM Cloud.
* [Hybrid cloud integration](/docs/rise-with-sap-on-powervs?topic=rise-with-sap-on-powervs-integration-hybrid) - Integrating RISE with SAP on IBM Power Virtual Server with your non-RISE SAP and non-RISE non-SAP on-premises workloads.
* [Multi-cloud integration](/docs/rise-with-sap-on-powervs?topic=rise-with-sap-on-powervs-integration-multi-cloud) - Integrating RISE with SAP on IBM Power Virtual Server with your non-RISE SAP and non-RISE non-SAP workloads hosted with other cloud providers.
