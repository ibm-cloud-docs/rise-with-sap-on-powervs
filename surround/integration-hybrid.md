---

copyright:
  years: 2025
lastupdated: 2025-02-09

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Hybrid
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

## The Enterprise hybrid pattern
{: #integration-hybrid-enterprise}

Larger enterprises that have adopted {{site.data.keyword.cloud}} have additional requirements, see [Enterprise architecture](/docs/enterprise-account-architecture?topic=enterprise-account-architecture-about) and [Adopting the Enterprise Architecture](/docs/adopt-enterprise-architecture?topic=adopt-enterprise-architecture-intro).

The diagrams below show a high-level pattern for an enterprise scale hybrid integration scenario. A number of surround workloads are shown hosted in the IBM Cloud infrastructure environments in your own IBM Cloud Account. The IBM Cloud Account for Client is peered with the IBM Cloud Account for RISE with SAP on {{site.data.keyword.powerSysFull}} using a cross-account transit gateway connection. See [Adding a cross-account connection](/docs/transit-gateway?topic=transit-gateway-adding-cross-account-connections&interface=ui).

The pattern uses a transit VPC which enables a hub-and-spoke design where the hub is the transit VPC and the SAP VPC and your other VPCs, Power Workspace and Classic infrastructure are the spokes and all spoke-to-spoke traffic passes through the hub. An alternative design is an edge VPC which only receives traffic leaving or entering your IBM Cloud Account. Diagrammatically the two patterns look the same, the difference is enabled in the routing.

While the diagrams show a Direct Link Dedicated connection to the Enterprise Networks, this connection could be Direct Link Connection or a VPN depending on your requirements. 

The diagram below shows a scenario where SAP® own the transit gateway and when you request SAP to peer they issue a connection request to your VPC.

![Figure 2. The Enterprise hybrid high-level pattern with SAP TGW](../images/hybrid-enterprise-high-level-sap-tgw.svg "The Enterprise hybrid high-level pattern with SAP TGW"){: caption="The Enterprise hybrid high-level pattern with SAP TGW" caption-side="bottom"}

The diagram below shows a scenario where the client owns the transit gateway.

![Figure 3. The Enterprise hybrid high-level pattern with client TGW](../images/hybrid-enterprise-high-level-client-tgw.svg "The Enterprise hybrid high-level pattern with client TGW"){: caption="The Enterprise hybrid high-level pattern with client TGW" caption-side="bottom"}

The diagram below shows a scenario where VPN is used to connect the two accounts.

![Figure 4. The Enterprise hybrid high-level pattern with VPN](../images/hybrid-enterprise-high-level-vpn.svg "The Enterprise hybrid high-level pattern with VPN"){: caption="The Enterprise hybrid high-level pattern with client TGW" caption-side="bottom"}

You will need to discuss your requirements with your SAP representative on which of these three patterns SAP will authorize to satisfy your needs.


## The Enterprise hybrid pattern in detail
{: #integration-hybrid-enterprise-detail}

The diagram below shows an enterprise scale hybrid integration scenario with a number of surround workloads hosted in the IBM Cloud infrastructure environments in your own IBM Cloud Account. The IBM Cloud Account for Client is peered with the IBM Cloud Account for RISE with SAP on iBM Power Virtual Server using a cross-account transit gateway connection. See [Adding a cross-account connection](/docs/transit-gateway?topic=transit-gateway-adding-cross-account-connections&interface=ui). The diagram shows a scenario where SAP® own the transit gateway and when you request SAP to peer they issue a connection request to your VPC.

![Figure 5. The Enterprise hybrid pattern](../images/hybrid-enterprise.svg "The Enterprise hybrid pattern"){: caption="The Enterprise hybrid pattern" caption-side="bottom"}

Key aspects of this pattern include the following:

* The transit hub VPC is the central point for routing of traffic routing between:
    1. The enterprise locations - IBM Cloud Direct Link offerings provide connectivity from an external source into a customer's IBM Cloud private network. Direct Link is designed for customers that need consistent, higher-throughput connectivity between a remote network and their IBM Cloud environments. See [About IBM Cloud Direct Link](/docs/dl?topic=dl-dl-about).
    2. Third party VPNs - IBM Cloud VPN for VPC offers two VPN services; site-to-site gateways connect external networks to the IBM Cloud VPC network, while client-to-site servers allow remote clients to connect using a secure tunnel. See [VPNs for VPC overview](/docs/vpc?topic=vpc-vpn-overview)
    3. Internet egress from IBM Cloud - Egress to the Internet from your IBM Cloud instances is via a public gateway. See [About public gateways](/docs/vpc?topic=vpc-about-public-gateways).
    4. Internet ingress to IBM Cloud - Ingress from the Internet to your instances in IBM Cloud is via public Application Load Balancers. See [About application load balancers](/docs/vpc?topic=vpc-load-balancers-about). Internet access should be protected using IBM Cloud Internet Services (CIS). CIS, powered with Cloudflare, offers three main capabilities to enhance your workflow: security, reliability, and performance. CIS provides features such as Web Application Firewall (WAF) and Global Load Balancing. See [About IBM Cloud Internet Services](/docs/cis?topic=cis-about-ibm-cloud-internet-services-cis).
* The transit hub VPC can host Virtual Network Function (VNF) devices, such as routers and firewalls running on virtual machines. These appliances can monitor, log, route and filter the traffic from the locations listed above to your instances in IBM Cloud. See the [IBM Cloud Catalog](/catalog?search=firewall%20label%3Asoftware#search_results) for third party vendors like Palo Alto, Fortinet, Checkpoint and Juniper who offer VNFs in IBM Cloud.
* Some of the VNF appliances require the use of a Network Load Balancer (NLB) with routing mode enabled when the VNF appliances are placed in different zones. NLB route mode has two IP addresses; active and standby. When a failover occurs, route mode updates all routing rules created under the same VPC with the next_hop of the Standby appliance IP. See [Creating a private network load balancer with routing mode](/docs/vpc?topic=vpc-nlb-vnf&interface=ui).
* The transit hub VPC can host enterprise shared resources such as DNS, see [About DNS Services](/docs/dns-svcs?topic=dns-svcs-about-dns-services) and Virtual Private Endpoints gateways. IBM Cloud VPE enables the connection of supported IBM Cloud services from your VPC network by using the IP addresses allocated from a subnet within your VPC. See [About virtual private endpoint gateways](/docs/vpc?topic=vpc-about-vpe)
* The spoke VPCs contains applications running on IBM Cloud virtual server instances, see [About virtual server instances for VPC](/docs/vpc?topic=vpc-about-advanced-virtual-servers), and bare metal servers, see [About Bare Metal Servers for VPC](/docs/vpc?topic=vpc-about-bare-metal-servers) logically grouped as needed.
* One of the spoke VPCs can be designated a Management VPC and host enterprise management tooling. Alternatively, if business unit level management is required than additional spokes can host management tooling for each business unit
* IBM Cloud Classic infrastructure environment contains the classic resources such as IBM Cloud VMware Solutions VMware Cloud Foundation (VCF) Classic. See [Overview of VCF for Classic - Automated](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vcenterserveroverview).
* The VCF as a Service (VCFaaS) Virtual Data Centers (VDC) hosts applications running on virtual machines and virtual appliances. See [VCF as a Service overview](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-aas-overview).
* Power Virtual Server workspace hosts applications running on AIX, IBMi or Linux on Power virtual server instances. See [Getting started with IBM Power Virtual Server](/docs/power-iaas?topic=power-iaas-getting-started)
* IBM Cloud Services hosts services including security, logging, monitoring, databases and other SaaS based offerings. See [IBM Cloud Catalog](/catalog)
* IBM Cloud Internet Services (CIS) provides secure and available access to web applications from the Internet. To secure or filter traffic entering the environment, capabilities such as DDoS mitigation or web application firewall (WAF) should be considered. IBM CIS includes these capabilities as well as the capability to act as a global load balancer (GLB), allowing to increase the availability and resiliency of the workloads running in IBM Cloud. For more information, see [Getting started with IBM Cloud Internet Services](/docs/cis?topic=cis-getting-started).

This architecture can be modified to match additional use-case:

* If required spoke-to-spoke communications can be defined so that for some IP routes are not routed via the transit hub for more efficient traffic flow. This accomplished using either the default or custom VPC routing tables.
* If dynamic routing is required between the enterprise and the VNFs, then GRE and BGP can be used linking the routers in your enterprise and the VNFs.
* Direct Link supports BGP routing, however, If the Direct Link is connected to a transit gateway this can also support BGP via GRE.
* If route prefix filtering is required then the DirectLink can be connected to a transit gateway that connects to the transit hub VPC. Transit gateway connections allow route prefix filtering. See [Adding and deleting prefix filters](/docs/transit-gateway?topic=transit-gateway-adding-prefix-filters&interface=ui).
* Additional transit gateways can be added to assist in separtaion, however, be aware of the [Service Limits](/docs/transit-gateway?topic=transit-gateway-helpful-tips&interface=ui#service-limits).
* To add disaster recovery to the reference architecture, connect another mult-izone region using a global transit gateway.

{: note}
1. When creating VPCs that are also intended to be interconnected with your IBM Cloud classic infrastructure, do not use prefixes in your VPCs that overlap with the 10.0.0.0/14, 10.200.0.0/14, and 10.198.0.0/15 blocks. Also, don't use addresses from your classic infrastructure subnets.
2. You can connect a VPC, Direct Link, or classic infrastructure to multiple local gateways and a single global gateway.
3. A classic connection allows you to communicate with all of your global classic infrastructure resources across MZRs, even if it is connected to a transit gateway provisioned with local routing.

## Routing
{: #integration-hybrid-enterprise-routing}

In the enterprise pattern it is important to understand routing in IBM Cloud, especially for the:

* Transit Gateway.
* VPC.

### Transit gateway
{: #integration-hybrid-enterprise-routing-tgw}

Integration of the different IBM Cloud IaaS environments, such as VPC, Classic, and PowerVS, is achieved by using the IBM Cloud Transit Gateway, which can be considered as a 'as a service Border Gateway Protocol (BGP) router'. IBM Cloud transit gateway can be local, limited to a specific region or global, spanning multiple regions. IBM Cloud Transit Gateway can also be used as the termination point for direct-link connectivity and Generic Routing Encapsulation (GRE) tunnels.

The Transit Gateway learns the routes advertised from it's connections. These routes are advertised from the VPC or, the connected traffic sources. Each VPC will advertise its address prefixes and any VPC ingress routing tables if defined, which allows VPCs to communicate with each other after connecting to a Transit Gateway. You do not have any access to manipulate the routing table on the transit gateway other than filtering the prefixes [Adding and deleting prefix filters](/docs/transit-gateway?topic=transit-gateway-adding-prefix-filters). For cross-account connections, only the account owner of the respective connection can modify prefix filters. Other accounts can view the connection, but cannot modify the filters. GRE tunnel configurations are not implemented as connections. Instead, their routes are learned directly on BGP sessions that are established over the tunnel. For this reason, prefix filtering is not enabled for these connections.

You can request a report of all routes known to a transit gateway and each of its connections. The report shows BGP information associated with these routes, which connections supply which routes, and overlapping routes. See [Generating a route report](/docs/transit-gateway?topic=transit-gateway-route-reports)

### VPC Routing
{: #integration-hybrid-enterprise-routing-vpc}

Traffic in a VPC, to a VPC, and from a VPC is controlled by VPC routing tables. VPC routing uses the following terms:

* Ingress - Ingress routing is the routing of traffic into the VPC zone from a traffic source. A traffic source can be: Direct Link, Transit gateway, VPC zone, or the Internet.
* Egress - Egress routing is the routing from the subnets in the VPC.

VPC has the following routing tables:

* Default Routing Table:
    * VPC automatically generates a default routing table for the VPC to manage traffic, by default, this routing table is empty.
    * You can add routes to the default routing table, or create one or more custom routing tables and then add routes.
    * The default routing table defines the egress routing from the subnets in the VPC.
    * Subnets can be reassigned to custom routing table.
    * Subnets can be added to the default routing table.
    * The default routing table can accept routes from VPN servers and VPN gateways.
    * In the default routing, you cannot select a traffic source (Direct link, Transit gateway, VPC zone, Public internet) that will use this routing table to route its traffic to the VPC.
    * To change the default routing policy that affects all subnets in the zone use the default routing table.
* System Routing Table:
    * A system-implicit routing table is maintained for each VPC.
    * A VPC can have a presence in multiple zones, and the VPC's system-implicit routing table is different in each zone.
    * For ingress routing, the system-implicit routing table contains only routes to each network interface in the VPC’s zone. This behavior can be avoided with a custom routing table default route with an action of drop.
    * You cannot configure a routing table to use the system-implicit routing table; it is populated automatically.
    * The system-implicit routing table is used when no matching route is found in the custom or default routing table that is associated with the subnet where the traffic is egressing. If no match is found, the packet is dropped.
    * The system-implicit routing table contains:
        * Routes to the CIDR of each subnet in the VPC.
        * Routes to subnets within the zone (statically maintained).
        * Routes to subnets in other zones that are learned through BGP.
        * Dynamic routes learned through BGP (for example, Direct Link and Transit Gateway).
        * The default route for internet traffic (used when a public gateway or floating IP is associated with the VPC).
        * Routes to the classic infrastructure service network CIDRs (used when a service gateway is associated with the VPC), for example: 10.0.0.0/14, 10.200.0.0/14, 10.198.0.0/15, and 10.254.0.0/16 are classic infrastructure service network CIDRs. Cloud service endpoint source addresses are the IP addresses that identify a VPC and zone combination outside of the VPC. For example, a source address is used when a service outside of the VPC is called through a cloud service endpoint. The IP address of the virtual server instance is replaced with an IPv4 address, the source address, which identifies the VPC to the cloud service endpoint
* Custom Routing Tables:
    * Custom routing tables can be added as needed.
    * Subnets can be added to custom routing tables to define routing for that subnet.
    * Adding a subnet removes the subnet from the default routing table.
    * You can choose if VPN servers or VPN gateways can create routes in the custom routing table. 
    * You can select which traffic source (Direct link, Transit gateway, VPC zone, Public internet) can use this routing table to route its traffic to the VPC. When selected the VPC prefixes are advertised to the traffic source. Optionally you can advertise the route to ingress sources that are outside the address prefix range of the VPC.
    * For the Direct link, Transit gateway, VPC zone, Public internet traffic sources, only one custom routing table can be enabled.
    * The Public internet traffic source allows public internet ingress traffic destined to a floating IP to be routed to a VPC next-hop IP.

It is important to understand the following:

1. Routing tables are evaluated in the order; custom, default, system.
2. Routing tables are associated with one or more subnets.
3. Each subnet has one routing table assigned to it, which is responsible for managing the subnet's egress traffic. You can change the routing table that a subnet uses to manage its egress traffic at any time.
4. Egress routes control traffic, which originates within a subnet and travels towards the public internet, or to another VM in same or different zone. For egress custom routes, when you add a destination route, you must select a zone. However, the next hop doesn't have to be in the same zone.
5. Ingress routes enable you to customize routes on incoming traffic to a VPC from traffic sources external to the VPC's availability zone (IBM Cloud Direct Link, IBM Cloud Transit Gateway, another availability zone in the same VPC, or the public internet). For ingress custom routes, the next hop must be in the same zone.
6. Only one custom routing table can be associated with a particular ingress traffic source. However, you can use different routing tables for different traffic sources. For example, routing table A might use Transit Gateway and VPC Zone, while routing table B uses Direct Link.
