---

copyright:
  years: 2025
lastupdated: 2025-02-08

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Integrating IBM Cloud with RISE with SAP on IBM Power Virtual Server
{: #integration-overview}

This document explains the concepts and best practices to follow for a performant and secure solution to connect your {{site.data.keyword.ibm_cloud}} workloads with your workloads hosted in RISE with SAP on IBM Power Virtual Server.

## RISE with SAP on IBM Power Virtual Server architecture
{: #integration-overview-arch}

SAP® creates and manages the entire RISE with SAP on IBM Power Virtual Server architecture running in an IBM Cloud Enterprise Account owned by SAP. SAP defines, validates and deploys all technical resources deployed in this IBM Cloud Enterprise Account. 

Clients of RISE with SAP on IBM Power Virtual Server do not get access to the SAP IBM Cloud Enterprise Account. The SAP IBM Cloud Enterprise Account and all the resources within it are visible to and managed by SAP only.

The details of the RISE with SAP on IBM Power Virtual Server architecture architecture, is the intellectual property of SAP. Clients work with SAP on configuration and customization of the deployed RISE landscape, to fit their organization's requirements.

It is important to understand that connectivity to your SAP systems in Power Virtual Server in IBM data center is via Application Load Balancers (ALB) hosted in the SAP managed IBM Cloud VPC. Therefore, all traffic to and from your SAP systems is routed via the ALBs (Direct Server Return is not used in ALB). The ALBs do source network address translation, so that all traffic to the SAP Power Virtual Servers is sourced from the ALBs and not directly from the client.

![Figure 1. Load Balancer](../images/lb.svg "Load Balancer"){: caption="Load Balancer" caption-side="bottom"}

### RISE with SAP on IBM Power Virtual Server IP schema
{: #integration-overview-arch-ip}

When you request the RISE with SAP on IBM Power Virtual Server service, you supply to SAP an IP address schema that will be used within their IBM Cloud Enterprise Account. This IP address schema must not overlap with any IP addresses used elsewhere in your organization or in IBM Cloud.

## RISE with SAP on IBM Power Virtual Server inter-connectivity
{: #integration-overview-arch-connectivity}

The diagram below shows the inter-connectivity options provided by RISE with SAP on IBM Power Virtual Server.

![Figure 2. Inter-connectivity](../images/interconnectivity.svg "Inter-connectivity"){: caption="Inter-connectivity" caption-side="bottom"}

The connections to RISE with SAP on IBM Power Virtual Server are defined as follows:

* On-premises to RISE with SAP on IBM Power Virtual Server - This connection connects your user/workloads on-premises or other non-IBM Cloud locations to the RISE with SAP on IBM Power Virtual Server service. This connectivity is defined by you and SAP and can can be one of the following types:
    * Site-to-site IPsec VPN.
    * Direct Link.
* Internet to RISE with SAP on IBM Power Virtual Server - This connectivity provides application access from the Internet
* Peering - IBM Cloud to RISE with SAP on IBM Power Virtual Server - This connectivity provides access between resources in your IBM Cloud account and your resources in RISE with SAP on IBM Power Virtual Server. There is also a variant of this connectivity type where your IBM Cloud account is a hub that connects to your on-premise or external locations and your IBM Cloud resources to RISE with SAP on IBM Power Virtual Server.

These documents defines the following three integration patterns:

* Internet integration - Integrating RISE with SAP on IBM Power Virtual Server with resources on the Internet such as SaaS and 3rd party providers.
* IBM cloud integration - Integrating RISE with SAP on IBM Power Virtual Server with your non-RISE SAP and non-RISE non-SAP workloads in IBM Cloud.
* Hybrid cloud integration - Integrating RISE with SAP on IBM Power Virtual Server with your non-RISE SAP and non-RISE non-SAP on-premises workloads.
* Multi-cloud integration - Integrating RISE with SAP on IBM Power Virtual Server with your non-RISE SAP and non-RISE non-SAP workloads hosted with other cloud providers.
