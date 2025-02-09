---

copyright:
  years: 2025
lastupdated: 2025-02-09

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Integrating on-premises and IBM Cloud with RISE with SAP on IBM Power Virtual Server
{: #integration-hybrid}

This hybrid use case illustrates a desire to connect on-premise or external locations to your {{site.data.keyword.cloud}} Account and then connect your IBM Cloud Account to the RISE with SAP on {{site.data.keyword.powerSysFull}} as shown in the diagram below:

![Figure 1. Integrating on-premises and IBM Cloud with RISE with SAP on IBM Power Virtual Server](../images/hybrid.svg "Integrating on-premises and IBM Cloud with RISE with SAP on IBM Power Virtual Server"){: caption="Integrating on-premises and IBM Cloud with RISE with SAP on IBM Power Virtual Server" caption-side="bottom"}

This use case is useful if a client already has an IBM Cloud presence linked to their on-premise location and then subsequently adds the RISE with SAP on IBM Power Virtual Server service. This use case is also applicable for new client IBM Accounts as part of a move to IBM and Cloud and RISE with SAP on IBM Power Virtual Server.

* The connectivity between the Enterprise Network and the IBM Cloud Account for Client can be optionally Direct Link or VPN or both depending on client requirements:
    * VPN - Enable access from your Enterprise Network to your IBM Cloud account with an IBM Cloud VPN for VPC site-to-site gateway. Traffic between IBM Cloud and your Enterprise Network is encrypted via Internet Protocol security (IPsec) and transferred through a secure tunnel over the Internet. This option is efficient, and faster to implement when compared to the IBM Direct Link. IBM Cloud VPN for VPC provides a simple, yet powerful solution for highly scalable and robust site-to-site VPN gateways. With this service, you can create site-to-site VPN tunnels for secure, encrypted connectivity. Connect from on-premises sites to IBM Cloud through a VPN gateway on an IBM Cloud VPC, and a peer gateway on-premises. This service provides a mixture of industry-standard security and encryption options as well as support for Pre-Shared Key (PSK) authentication. This service also provides the ability to quickly add and remove VPN connections with the option to use pre-defined configurations.  See [About site-to-site VPN gateways](/docs/vpc?topic=vpc-using-vpn).
    * Direct Link - Use the IBM Direct Link if you require a higher throughput or more consistent network experience than an Internet-based connection. IBM Direct Link connects your on-premises resources to your cloud resources and offers more consistent, higher-throughput connectivity, keeping traffic within the IBM Cloud network. See [Getting started with IBM Cloud Direct Link](/docs/dl?topic=dl-get-started-with-ibm-cloud-dl). The following IBM Direct Link services are available:
        * Direct Link Dedicated - Terminate a single-tenant, fiber-based, cross-connect into your own IBM Cloud Private network connection. The speeds that are supported for the Direct Link Dedicated offering are 1 Gbps, 2 Gbps, 5 Gbps, and 10 Gbps.
        * Direct Link Connect - Use a service provider to quickly establish and deliver connectivity to IBM Cloud. These service providers are already connected to the IBM Cloud network and use a multi-tenant, high capacity links, known as network-to-network interfaces (NNI). Available speeds are based on your provider and provider's location. Partners include: AT&T, Cologix, Console Connect, DE-CIX, Digital Realty, Equinix, Megaport, and Verizon SCI.
* The peering between the IBM Cloud Account for Client and RISE with SAP on IBM Power Virtual Server can be via a Client provided Transit Gateway or the SAP Transit Gateway. Not shown in the diagram, but there is an option to connect the IBM Cloud Account for Client to the RISE with SAP on IBM Power Virtual Server using a VPN, however, peering using a transit gateway is the preferred option.

The diagram does not show the use of a Virtual Network Functions (VNFs) appliance. VNF appliances, are packaged 3rd party firewall offerings available on the IBM Catalog. See [About virtual network functions over VPC](https://cloud.ibm.com/docs/vpc?topic=vpc-about-vnf) and [Available IBM Cloud VNF catalog offerings](https://cloud.ibm.com/docs/vpc?topic=vpc-deploy-vnf#available-vnf-offerings). See the enterprise scale hybrid integration for the use of a VNF in the architecture.

{: note}
When connecting to RISE with SAP discuss with your SAP representative on the transit gateway connection they provide to enable peering between your IBM Cloud Account and the RISE with SAP IBM Cloud Account.

The documentation [Extending your enterprise network to IBM Cloud](https://cloud.ibm.com/docs/pattern-classic-edge-gateway?topic=pattern-classic-edge-gateway-extending-enterprise-network) takes a different approach and defines a reference architecture used to direct all network traffic to flow through an IBM Cloud Classic firewall or gateway appliance for inspection before going to the downstream workloads within IBM Cloud.
