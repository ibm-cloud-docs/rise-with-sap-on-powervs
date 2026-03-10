---

copyright:
  years: 2025
lastupdated: "2026-03-10"

keywords: SAP, RISE, PowerVS, RISE with SAP on PowerVS, SAP on IBM Cloud, Benefits of RISE with SAP on IBM Cloud, IBM Power Virtual Server, SAP modernization

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Reference Architecture
{: #reference-architecture}

## Overview
{: #reference-architecture-overview}

Using {{site.data.keyword.powerSysFull}}, the cloud-based version of the mission-critical IBM Power server platform used for on-premises Enterprise Resource Planning (ERP), you can rapidly transform on-premises SAP ERP systems, modernize business processes and become more agile. Known for its high security, scalability and reliability, IBM Power servers are engineered for fewer disruptions and facilitates faster migration, supported by the highly resilient and secured IBM Cloud platform.

SAP S/4HANA Cloud Private Edition is the software in the RISE with SAP on IBM Power Virtual Server service that holds the client’s mission critical data and business processes. SAP Enterprise Cloud Services (ECS) provides a managed private environment with multi-layer defense in depth architecture handling infrastructure and technical managed services in line with their Service Level Agreement (SLA).

![Figure 1. RISE with SAP on IBM Power Virtual Server Overview](../images/architecture-overview.svg "RISE with SAP on IBM Power Virtual Server Overview"){: caption="RISE with SAP on IBM Power Virtual Server Overview" caption-side="bottom"}

SAP S/4HANA Cloud Private Edition is a single-tenant managed private environment for clients where SAP creates a separate IBM Cloud Account in their IBM Cloud Enterprise Account for each customer. The application and database virtual server instances are solely dedicated to a single client.

SAP creates and manages the entire RISE with SAP on IBM Power Virtual Server architecture running in an IBM Cloud Enterprise Account owned by SAP. SAP defines, validates and deploys all technical resources deployed in this IBM Cloud Enterprise Account.

Clients of RISE with SAP on IBM Power Virtual Server do not get access to the SAP IBM Cloud Enterprise Account. The SAP IBM Cloud Enterprise Account and all the resources within it are visible to and managed by SAP only.

The details of the RISE with SAP on IBM Power Virtual Server architecture architecture, is the intellectual property of SAP. Clients work with SAP on configuration and customization of the deployed RISE landscape, to fit their organization's requirements.
{: note}


## Connectivity to RISE with SAP on IBM Power Virtual Server
{: #reference-architecture-connectivity}

It is the client's responsibility to ensure secure connectivity to RISE with SAP on IBM Power Virtual Server. There are essentially four different ways to connect to the service and the client can select the connections based on their specific requirements on security, compliance, bandwidth, and cost:

1. **IPsec VPN** - The client and SAP will configure the encryption parameters and authentication details for the VPN gateways to establish a secure IPsec tunnel.
2. **Dedicated Private Connection** - While many clients rely on Internet services, some clients may prefer a dedicated private connection to the RISE with SAP on IBM Power Virtual Server environment for added security and compliance when accessing their business processes and applications. IBM Cloud Direct Link and Direct Link Connect facilitate these private connections. Direct Link Connect in association with a Cloud Exchange Provider, provides access to other cloud providers, on-premise connections and SAP Cloud peering. SAP Cloud Peering is a reliable and secure connectivity option for client to SAP Cloud Services leveraging SAP’s global interconnection provider ecosystem. SAP Cloud Peering provides a secure connectivity option, because the traffic traverses the Cloud Exchange Provider's network, to connect to SAP SuccessFactors, SAP Ariba, SAP BTP, SAP Concur and more SAP solutions.
3. **Peering** - Many clients considering using RISE with SAP on IBM Power Virtual Server may already have an existing IBM Cloud Account, where they are hosting their own applications. In order to integrate the clients exiting IBM cloud account, a secure connection is needed between the client’s IBM Cloud Account and the RISE with SAP on IBM Power Virtual Server IBM Cloud Account, managed by SAP ECS. In IBM Cloud peering is facilitated by Transit Gateway cross-account connections.
4. **Internet** - Some clients may want to access RISE with SAP on IBM Power Virtual Server via the Internet directly. This can be achieved via traffic traversing through the IBM Cloud Internet Services (CIS) Web Application Firewall (WAF). For inbound Internet connection, only HTTPS/TLS1.2 is allowed.
