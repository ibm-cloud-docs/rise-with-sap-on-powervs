---

copyright:
  years: 2025
lastupdated: 2025-02-08

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# IBM Cloud
{: #integration-ibm-cloud}

While your RISE with SAP on {{site.data.keyword.powerSysFull}} workloads are running in the SAP® IBM Cloud Account, your IBM Cloud surround workloads run in your own IBM Cloud Account.

![Figure 1. IBM Cloud Surround Workloads](../images/workloads.svg "IBM Cloud Surround Workloads"){: caption="IBM Cloud Surround Workloads" caption-side="bottom"}

There are two types of connectivity patterns for peering your IBM Cloud surround workloads to your RISE with SAP on IBM Power Virtual Server workloads:

* IBM Cloud Transit Gateway.
* IBM Cloud Site-to-Site VPN.

## The IBM Cloud Transit Gateway pattern
{: #integration-ibm-cloud-tgw}

With IBM Cloud Transit Gateway, you can define and control communication between resources hosted in the IBM Cloud infrastructure environments and/or on-premise networks. See [Getting started with IBM Cloud Transit Gateway](/docs/transit-gateway?topic=transit-gateway-getting-started). With an IBM Cloud Transit Gateway, you can connect:

* VPCs in your account or a different account.
* IBM Cloud classic infrastructure in your account or a different account.
* Direct Link in your account or a different account.
* IBM PowerVS in IBM data center in your account or a different account.
* Unbound Generic Routing Encapsulation (GRE) tunnels allow a connection between a zone and an endpoint in IBM Cloud Classic in your account or a different account.
* Redundant Generic Routing Encapsulation (GRE) tunnels allow a connection between two zones and an endpoint in IBM Cloud Classic or a VPC in your account or a different account.

The IBM Cloud Transit Gateway pattern has two sub-patterns:

* IBM Cloud Transit Gateway in the SAP account.
* IBM Cloud Transit Gateway in the client account.

{: note}
When connecting to RISE with SAP discuss with your SAP representative on the transit gateway connection they provide to enable peering between your IBM Cloud Account and the RISE with SAP IBM Cloud Account.

### IBM Cloud Transit Gateway in the SAP account
{: #integration-ibm-cloud-tgw-sap}

This pattern uses the IBM Cloud Transit Gateway in the RISE with SAP on IBM Power Virtual Server IBM Cloud Account. As this IBM Cloud Transit Gateway has the local routing option, it only supports your VPCs in the same region as the RISE with SAP on IBM Power Virtual Server VPC.

![Figure 2. IBM Cloud Transit Gateway in the SAP account](../images/sap-tgw.svg "IBM Cloud Transit Gateway in the SAP account"){: caption="IBM Cloud Transit Gateway in the SAP account" caption-side="bottom"}

1. Request the service from SAP and supply:
   1. VPC: your VPC CRN.
   2. Classic: Account ID.
   3. PowerVS: Power Systems Virtual Server CRN.
2. SAP adds a new connection to their existing gateway to your designated VPC, Classic or PowerVS environment.
3. You approve the connection request.

The diagram below illustrates traffic flow between a Client's VPC and SAP resources in RISE with SAP on Power Virtual Server.

![Figure 3. IBM Cloud Transit Gateway in the SAP account traffic flow](../images/lb-sap-tgw.svg "IBM Cloud Transit Gateway in the SAP account traffic flow"){: caption="IBM Cloud Transit Gateway in the SAP account traffic flow" caption-side="bottom"}

{: note}
While the diagram shows the IBM Cloud surround workload in a VPC, they can be hosted in the Classic or Power Virtual Server infrastructure environments.

### IBM Cloud Transit Gateway in the client account
{: #integration-ibm-cloud-tgw-client}

To establish a connection with your RISE with SAP on IBM Power Virtual Server workload use a new or existing IBM Cloud Transit Gateway in your account, with a cross account connection. Once approved by SAP, your Transit Gateway will have a connection to the VPC networks hosting your RISE with SAP on IBM Power Virtual Server workloads in the SAP IBM Cloud Enterprise Account.

You can select either a IBM Cloud Transit Gateway with local or global routing options depending on the locations of the your VPC and the location of the RISE with SAP on IBM Power Virtual Server VPC. If the VPCs are in the same region, local routing can be selected. If in different regions, then the global routing option must be selected.

![Figure 4. IBM Cloud Transit Gateway in the client account](../images/client-tgw.svg "IBM Cloud Transit Gateway in the client account"){: caption="IBM Cloud Transit Gateway in the client account" caption-side="bottom"}

1. Request SAP for the their VPC CRN.
2. On a new or existing TGW add a connection to a VPC in a different account and enter the VPC CRN supplied to you from SAP.
3. SAP will approve the request.

The diagram below illustrates traffic flow between a Client's VPC and SAP resources in RISE with SAP on Power Virtual Server.

![Figure 5. IBM Cloud Transit Gateway in the client account traffic flow](../images/lb-client-tgw.svg "IBM Cloud Transit Gateway in the client account traffic flow"){: caption="IBM Cloud Transit Gateway in the client account traffic flow" caption-side="bottom"}

## IBM Cloud Site-to-Site VPN pattern
{: #integration-ibm-cloud-vpn}

This pattern uses the IBM Cloud VPN for VPC service to securely connect your VPC to the RISE with SAP on IBM Power Virtual Server. It can leverage a static, route-based VPN, or a policy-based VPN to set up an IPsec site-to-site tunnel between the two VPCs

See [About site-to-site VPN gateways](/docs/vpc?topic=vpc-using-vpn) and [Planning considerations for VPN gateways](/docs/vpc?topic=vpc-planning-considerations-vpn)

![Figure 6. IBM Cloud Site-to-Site VPN pattern](../images/vpn.svg "IBM Cloud Site-to-Site VPN pattern"){: caption="IBM Cloud Site-to-Site VPN pattern" caption-side="bottom"}

1. Request the service from SAP.
2. SAP respond with their VPN endpoint details.
3. Create a site-to-site VPN and configure with the SAP provided details.
4. Provide SAP with your endpoint details.
