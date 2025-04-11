---

copyright:
  years: 2025
lastupdated: 2025-04-11

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Reference Architecture
{: #reference-architecture}

## Overview
{: #reference-architecture-overview}

Using {{site.data.keyword.powerSysFull}}, the cloud-based version of the mission-critical IBM Power server platform used for on-premises Enterprise Resource Planning (ERP), you can rapidly transform on-premises SAP ERP systems, modernize business processes and become more agile. Known for its high security, scalability and reliability, IBM Power servers are engineered for fewer disruptions and facilitates faster migration, supported by the highly resilient and secured IBM Cloud platform.

SAP S/4HANA Cloud Private Edition is the software in the RISE with SAP on IBM Power Virtual Server service that holds the client’s mission critical data and business processes. SAP Enterprise Cloud Services (ECS) provides a managed private environment with multi-layer defense in depth architecture handling infrastructure and technical managed services in line with their Service Level Agreement (SLA).

SAP S/4HANA Cloud Private Edition is a single-tenant managed private environment for clients where SAP creates a separate IBM Cloud Account in their IBM Cloud Enterprise Account for each customer. The application and database virtual server instances are solely dedicated to a single client.

SAP creates and manages the entire RISE with SAP on IBM Power Virtual Server architecture running in an IBM Cloud Enterprise Account owned by SAP. SAP defines, validates and deploys all technical resources deployed in this IBM Cloud Enterprise Account. 

Clients of RISE with SAP on IBM Power Virtual Server do not get access to the SAP IBM Cloud Enterprise Account. The SAP IBM Cloud Enterprise Account and all the resources within it are visible to and managed by SAP only.

The details of the RISE with SAP on IBM Power Virtual Server architecture architecture, is the intellectual property of SAP. Clients work with SAP on configuration and customization of the deployed RISE landscape, to fit their organization's requirements.
{: note}

## Application load balancers
{: #reference-architecture-alb}

It is important to understand that connectivity to your SAP systems in Power Virtual Server in IBM data center is via Application Load Balancers (ALB) hosted in the SAP managed IBM Cloud VPC. Therefore, all traffic to and from your SAP systems is routed via the ALBs (Direct Server Return is not used in ALB). The ALBs do source network address translation, so that all traffic to the SAP Power Virtual Servers is sourced from the ALBs and not directly from the client.

![Figure 1. Load Balancer](../images/lb.svg "Load Balancer"){: caption="Load Balancer" caption-side="bottom"}

## IP address schema
{: #reference-architecture-ip}

When you request the RISE with SAP on IBM Power Virtual Server service, you supply to SAP an IP address schema that will be used within the SAP managed IBM Cloud Enterprise Account. This IP address schema must not overlap with any IP addresses used elsewhere in your organization’s network or any peered resource from your IBM Cloud accounts, client managed or client’s service provider managed, or other interconnected cloud resource.

## Connectivity to RISE with SAP on IBM Power Virtual Server
{: #reference-architecture-connectivity}

It is the client's responsibility to ensure secure connectivity to RISE with SAP on IBM Power Virtual Server. There are essentially four different ways to connect to the service and the client can select the connections based on their specific requirements on security, compliance, bandwidth, and cost:

1. IPsec VPN - The client and SAP will configure the encryption parameters and authentication details for the VPN gateways to establish a secure IPsec tunnel.
2. Dedicated Private Connection - While many clients rely on Internet services, some clients may prefer a dedicated private connection to the RISE with SAP on IBM Power Virtual Server environment for added security and compliance when accessing their business processes and applications. IBM Cloud Direct Link and Direct Link Connect facilitate these private connections. Direct Link Connect in association with a Cloud Exchange Provider, provides access to other cloud providers, on-premise connections and SAP Cloud peering. SAP Cloud Peering is a reliable and secure connectivity option for client to SAP Cloud Services leveraging SAP’s global interconnection provider ecosystem. SAP Cloud Peering provides a secure connectivity option, because the traffic traverses the Cloud Exchange Provider's network, to connect to SAP SuccessFactors, SAP Ariba, SAP BTP, SAP Concur and more SAP solutions.
3. Peering - Many clients considering using RISE with SAP on IBM Power Virtual Server may already have an existing IBM Cloud Account, where they are hosting their own applications. In order to integrate the clients exiting IBM cloud account, a secure connection is needed between the client’s IBM Cloud Account and the “RISE with SAP on IBM Power Virtual Server IBM Cloud Account”, managed by SAP ECS. In IBM Cloud peering is facilitated by Transit Gateway cross-account connections.. In IBM Cloud peering is facilitated by Transit Gateway cross-account connections.
4. Internet - Some clients may want to access RISE with SAP on IBM Power Virtual Server via the Internet directly. This can be achieved via traffic traversing through the IBM Cloud Internet Services (CIS) Web Application Firewall (WAF). For inbound Internet connection, only HTTPS/TLS1.2 is allowed.

The high-level RISE with SAP on IBM Power Virtual Server is shown in the diagram below along with the connectivity options.

![Figure 2. RISE with SAP on IBM Power Virtual Server Overview](../images/overview.svg "RISE with SAP on IBM Power Virtual Server Overview"){: caption="RISE with SAP on IBM Power Virtual Server Overview" caption-side="bottom"}

## System communication with RISE with SAP Power Virtual Server
{: #reference-architecture-system-communication}

Your RISE with SAP {{site.data.keyword.powerSysFull}} systems allow the following system communications:

* RFC -  Remote Function Calls (RFC) are a standard SAP® interface that allows communication between SAP systems and allows connections for functions such as Business Application Programming Interface (BAPI) and Intermediate Document (IDoc). BAPI is a standard SAP application interface that helps to integrate non-SAP applications with the SAP business process and enables providing data entry into the SAP system. IDoc is a standard format for exchanging business transaction data between SAP applications and non-SAP systemsIDoc, Applications can only access your SAP systems in RISE with SAP Power Virtual Server using RFC through private network address ranges and is, therefore, limited to applications hosted in your premises, in your IBM Cloud account or via third parties using VPN or DirectLink connections.
* HTTPS - Hypertext Transfer Protocol Secure (HTTPS) is used for Open Data Protocol (OData), REpresentational State Transfer (REST), and Simple Object Access Protocol (SOAP) Application Programming Interface (API). OData is a standard that defines a set of best practices for building and consuming RESTful APIs. REST is a type of API used to connect components in microservices architectures and integrate applications. SOAP is an API that uses Extensible Markup Language (XML) to send and receive messages between systems and applications. Applications can access through HTTPS on a publicly available IP, exposed by RISE with SAP Power Virtual Server or through private network address ranges.
* ODBC/JDBC - Open Database Connectivity (ODBC) and Java Database Connectivity (JDBC) are standard APIs that allows applications to access data from database management systems such as SAP HANA. Applications can only access your SAP systems in RISE with SAP Power Virtual Server using ODBC/JDBC through private network address ranges and is, therefore, limited to applications hosted in your premises, in your IBM Cloud account or via third parties using VPN or DirectLink connections.

The system communications described above are facilitated by TCP/IP and your RISE with SAP Power Virtual Server can be accessed through the open network ports, when configured and opened by SAP for your use.

The diagram below, shows how the data connectors within your self-hosted integration runtime communicate with the SAP system hosted in SAP Power Virtual Server through the IBM Cloud private network. You can use security groups and network access control lists to limit which instances can communicate with the SAP system. HTTPS access can also be requested from SAP from the public network.

![Figure 3. Communications](../images/communications.svg "Communications"){: caption="Communications" caption-side="bottom"}

You are responsible for deployment and operation of the self-hosted integration runtime within your IBM Cloud Account. RISE with SAP Power Virtual Server exposes the communication ports for your applications to use but has no knowledge or support for the connected application or service.

Contact SAP for details on communication paths available to you with RISE with SAP Power Virtual Server and the necessary steps to open them. SAP must also be contacted for any SAP license details for any implications accessing SAP data through any external applications.
{: note}

## DNS Considerations
{: #reference-architecture-dns}

When you request the RISE with SAP on {{site.data.keyword.powerSysFull}}, you supply your domain name e.g. `<customer>.com`. SAP® create a sub-domain e.g. `sap.<customer>.com` on the DNS servers in their {{site.data.keyword.cloud}} Enterprise Account that hosts the fully qualified domain names and IP addresses for the services they host for you. SAP allow a zone transfer from their SAP DNS servers to your DNS servers, so that name resolution on your network can occur.

In some circumstances SAP will allow DNS forwarding of requests from your DNS servers to SAP's DNS servers. You must request this non-preferred method from your SAP representative.

SAP have documented DNS considerations for AWS, Azure and GCP at [DNS integration with SAP RISE in multi-cloud environment series guide](https://community.sap.com/t5/enterprise-resource-planning-blogs-by-sap/dns-integration-with-sap-rise-in-multi-cloud-environment-series-guide-gcp/ba-p/13557022){: external}. These guides can be referred to, as the majority of the information is common with RISE with SAP on Power Virtual Server. Further IBM specific clarification is described in the sections below.

### IBM Cloud Transit Gateway in the SAP account
{: #reference-architecture-dns-sap-tgw}

SAP may decide that to achieve your connectivity requirements, they will use the transit gateway in their IBM Cloud account to connect to your IBM Cloud account. The diagram below illustrates the SAP preferred method of DNS zone transfer to your DNS service provisioned from the IBM catalog in your IBM Cloud Account. A secondary zone is a read-only copy of the primary DNS zone, communicated via a process known as a zone transfer. In this use case SAP own the primary DNS zone. See [Understanding secondary zones](/docs/dns-svcs?topic=dns-svcs-sec-zones-about).

![Figure 4. IBM Cloud DNS with the Transit Gateway in the SAP account](../images/dns-sap-tgw.svg "IBM Cloud DNS with the Transit Gateway in the SAP account"){: caption="IBM Cloud DNS with the Transit Gateway in the SAP account" caption-side="bottom"}

The process steps to achieve this use case include the following:

1. Request the service from SAP, providing the IP addresses of your DNS customer resolvers.
2. SAP provide the IP addresses of their SAP DNS servers.
3. Create a DNS secondary zone, see [Creating a secondary zone from the CLI](/docs/dns-svcs?topic=dns-svcs-create-secondary-zone&interface=cli), using the IP addresses supplied by SAP in the `--transfer-from` value parameter. You can use the IBM Cloud UI or API if preferred.

You may host your own DNS software on IBM Cloud VSIs, as shown in the diagram below:

![Figure 5. Client DNS with the Transit Gateway in the SAP account](../images/client-dns-sap-tgw.svg "Client DNS with the Transit Gateway in the SAP account"){: caption="Client DNS with the Transit Gateway in the SAP account" caption-side="bottom"}

The process steps to achieve this use case include the following:

1. Request the service from SAP, providing the IP addresses of your DNS servers.
2. SAP provide the IP addresses of their SAP DNS servers.
3. Follow the instructions for your DNS software to enable the zone transfer.

### IBM Cloud Transit Gateway in the client account
{: #reference-architecture-dns-client-tgw}

SAP may decide that to achieve your connectivity requirements, they will use the transit gateway in your IBM Cloud account to connect to the RISE with SAP IBM Cloud account. The diagram below illustrates the SAP preferred method of DNS zone transfer to your DNS service provisioned from the IBM catalog in your IBM Cloud Account. A secondary zone is a read-only copy of the primary DNS zone, communicated via a process known as a zone transfer. In this use case SAP own the primary DNS zone. See [Understanding secondary zones](/docs/dns-svcs?topic=dns-svcs-sec-zones-about).

![Figure 6. IBM DNS with the Transit Gateway in the Client account](../images/dns-client-tgw.svg "IBM DNS with the Transit Gateway in the Client account"){: caption="IBM DNS with the Transit Gateway in the Client account" caption-side="bottom"}

The process steps to achieve this use case include the following:

1. Request the service from SAP, providing the IP addresses of your DNS customer resolvers.
2. SAP provide the IP addresses of their SAP DNS servers.
3. Create a DNS secondary zone, see [Creating a secondary zone from the CLI](/docs/dns-svcs?topic=dns-svcs-create-secondary-zone&interface=cli), using the IP addresses supplied by SAP in the `--transfer-from` value parameter. You can use the IBM Cloud UI or API if preferred.

You may host your own DNS software on IBM Cloud VSIs, as shown in the diagram below:

![Figure 7. Client DNS with the Transit Gateway in the Client account](../images/client-dns-client-tgw.svg "Client DNS with the Transit Gateway in the Client account"){: caption="Client DNS with the Transit Gateway in the SAP account" caption-side="bottom"}

The process steps to achieve this use case include the following:

1. Request the service from SAP, providing the IP addresses of your DNS servers.
2. SAP provide the IP addresses of their SAP DNS servers.
3. Follow the instructions for your DNS software to enable the zone transfer.

### IBM Cloud Site-to-Site VPN pattern
{: #reference-architecture-dns-vpn}

The diagram below illustrates the SAP preferred method of DNS zone transfer to your DNS service provisioned from the IBM catalog in your IBM Cloud Account. A secondary zone is a read-only copy of the primary DNS zone, communicated via a process known as a zone transfer. In this use case SAP own the primary DNS zone. See [Understanding secondary zones](/docs/dns-svcs?topic=dns-svcs-sec-zones-about).

![Figure 8. IBM DNS with VPN](../images/dns-vpn.svg "IBM DNS with VPN"){: caption="IBM DNS with VPN" caption-side="bottom"}

The process steps to achieve this use case include the following:

1. Request the service from SAP, providing the IP addresses of your DNS customer resolvers.
2. SAP provide the IP addresses of their SAP DNS servers.
3. Create a DNS secondary zone, see [Creating a secondary zone from the CLI](/docs/dns-svcs?topic=dns-svcs-create-secondary-zone&interface=cli), using the IP addresses supplied by SAP in the `--transfer-from` value parameter. You can use the IBM Cloud UI or API if preferred.

You may host your own DNS software on IBM Cloud VSIs, as shown in the diagram below:

![Figure 9. Client DNS with VPN](../images/client-dns-vpn.svg "Client DNS with VPN"){: caption="Client DNS with VPN" caption-side="bottom"}

The process steps to achieve this use case include the following:

1. Request the service from SAP, providing the IP addresses of your DNS servers.
2. SAP provide the IP addresses of their SAP DNS servers.
3. Follow the instructions for your DNS software to enable the zone transfer.
