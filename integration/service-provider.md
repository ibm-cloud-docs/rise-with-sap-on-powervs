---

copyright:
  years: 2025
lastupdated: 2025-02-09

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Integrating with Service Providers
{: #integration-service-providers}

This document considers the integration of service provider and SaaS provider with RISE with SAP {{site.data.keyword.powerSysFull}} non-RISE SAP and non-RISE non-SAP workloads. 

## Management Service Provider
{: #integration-service-providers-mgmt}

IBM SAP® Ecosystem Partners deliver services such as assessments, transformations, migrations, and also operate RISE with SAP on IBM Power Virtual Server surround workloads.

Surround workloads are defined as those workloads outside of the RISE with SAP on IBM Power Virtual Server service but hosted in IBM Cloud accounts owned by the clients or their service providers.

Service Providers host services in IBM Cloud and make those services available to IBM Cloud clients. These services can vary from management services, where the service provider manages clients infrastructure, operating systems and applications, or they offer SaaS type of services.

![Figure 1. Management Service Provider](../images/service-provider.svg "Management Service Provider"){: caption="Management Service Provider" caption-side="bottom"}

## SaaS Provider
{: #integration-service-providers-saas}

The diagram below shows a variant of the service provider architecture, where the provider exposes their SaaS offering via private path services. Private path services provide private connectivity for service providers to their consumers. The service uses a Virtual Private Endpoint (VPE) gateway for consumers to connect to the service. See [About Private Path services](/docs/vpc?topic=vpc-private-path-service-intro).

Private Path service only supports providers and consumers in the same region using TCP and the VPE can only be connected-to from within the VPC it resides in. See [Private Path service limitations](/docs/vpc?topic=vpc-ppsg-limitations).

![Figure 1. SaaS Provider](../images/saas-provider.svg "SaaS Service Provider"){: caption="SaaS Service Provider" caption-side="bottom"}

For consuming IBM SAP Ecosystem Partner's SaaS services directly from RISE with SAP IBM Power Virtual Server discuss with your SAP representative.
