---

copyright:
  years: 2025
lastupdated: 2025-03-17

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Reference Architecture
{: #reference-architecture}

Using {{site.data.keyword.powerSysFull}}, the cloud-based version of the mission-critical IBM Power server platform used for on-premises Enterprise Resource Planning (ERP), you can rapidly transform on-premises SAP ERP systems, modernize business processes and become more agile. Known for its high security, scalability and reliability, IBM Power servers are engineered for fewer disruptions and faster migration, supported by the highly resilient and secured IBM Cloud platform.

SAP S/4HANA Cloud Private Edition is the software in the RISE with SAP on IBM Power Virtual Server service that holds the client’s mission critical data and business processes. SAP Enterprise Cloud Services (ECS) provides a managed private environment with multi-layer defense in depth architecture handling infrastructure and technical managed services in line with their Service Level Agreement (SLA).

SAP S/4HANA Cloud Private Edition is a single-tenant managed private environment for clients where SAP creates a separate account IBM Cloud Account in their IBM Cloud Enterprise Account for each customer. The application and database virtual server instances are solely dedicated to a single client.

SAP creates and manages the entire RISE with SAP on IBM Power Virtual Server architecture running in an IBM Cloud Enterprise Account owned by SAP. SAP defines, validates and deploys all technical resources deployed in this IBM Cloud Enterprise Account. 

Clients of RISE with SAP on IBM Power Virtual Server do not get access to the SAP IBM Cloud Enterprise Account. The SAP IBM Cloud Enterprise Account and all the resources within it are visible to and managed by SAP only.

The details of the RISE with SAP on IBM Power Virtual Server architecture architecture, is the intellectual property of SAP. Clients work with SAP on configuration and customization of the deployed RISE landscape, to fit their organization's requirements.

It is important to understand that connectivity to your SAP systems in Power Virtual Server in IBM data center is via Application Load Balancers (ALB) hosted in the SAP managed IBM Cloud VPC. Therefore, all traffic to and from your SAP systems is routed via the ALBs (Direct Server Return is not used in ALB). The ALBs do source network address translation, so that all traffic to the SAP Power Virtual Servers is sourced from the ALBs and not directly from the client.

![Figure 1. Load Balancer](../images/lb.svg "Load Balancer"){: caption="Load Balancer" caption-side="bottom"}

When you request the RISE with SAP on IBM Power Virtual Server service, you supply to SAP an IP address schema that will be used within their IBM Cloud Enterprise Account. This IP address schema must not overlap with any IP addresses used elsewhere in your organization or in IBM Cloud.

It is the client's responsibility to ensure secure connectivity to RISE with SAP on IBM Power Virtual Server. There are essentially four different ways to connect to the service and the client can select the connections based on their specific requirements on security, compliance, bandwidth, and cost:

1. IPsec VPN - The client and SAP will configure the encryption parameters and authentication details for the VPN gateways to establish a secure IPsec tunnel.
2. Dedicated Private Connection - While many clients rely on Internet services, some clients may prefer a dedicated private connection to the RISE with SAP on IBM Power Virtual Server environment for added security and compliance when accessing their business processes and applications. IBM Cloud Direct Link and Direct Link Connect facilitate these dedicated private connections. Direct Link Connect in association with a Cloud Exchange Provider, provides access to other cloud providers, on-premise connections and SAP Cloud peering. SAP Cloud Peering is a reliable and secure connectivity option for client to SAP Cloud Services leveraging SAP’s global interconnection provider ecosystem. SAP Cloud Peering provides a secure connectivity option, because the traffic traverses the Cloud Exchange Provider's network, to connect to SAP SuccessFactors, SAP Ariba, SAP BTP, SAP Concur and more SAP solutions.
3. Peering - Many clients using RISE with SAP on IBM Power Virtual Server may have an existing IBM Cloud Account, where they are hosting their own applications. As a part of integration, a secure connection is needed between the client IBM Cloud Account and the RISE with SAP on IBM Power Virtual Server IBM Cloud Account managed by SAP ECS. In IBM Cloud peering is facilitated by Transit Gateway cross-account connections.
4. Internet - Some clients may want to access RISE with SAP on IBM Power Virtual Server via via the Internet directly. This can be allowed via traffic traversing via the IBM Cloud Internet Services (CIS) Web Application Firewall (WAF). For inbound Internet connection, only HTTPS/TLS1.2 is allowed. 

The high-level RISE with SAP on IBM Power Virtual Server is shown in the diagram below along with the connectivity options.

![Figure 2. RISE with SAP on IBM Power Virtual Server Overview](../images/overview.svg "RISE with SAP on IBM Power Virtual Server Overview"){: caption="RISE with SAP on IBM Power Virtual Server Overview" caption-side="bottom"}

## System communication with RISE with SAP Power Virtual Server
{: #reference-architecture-system-communication}

Your RISE with SAP {{site.data.keyword.powerSysFull}} systems allow the following system communications:

* RFC -  Remote Function Calls (RFC) are a standard SAP® interface that allows communication between SAP systems and allows connections for functions such as Business Application Programming Interface (BAPI) and Intermediate Document (IDoc). BAPI is a standard SAP application interface that helps to integrate non-SAP applications with the SAP business process and enables providing data entry into the SAP system. IDoc is a standard format for exchanging business transaction data between SAP applications and non-SAP systemsIDoc, Applications can only access your SAP systems in RISE with SAP Power Virtual Server using RFC through private network address ranges and is, therefore, limited to applications hosted in your premises, in your IBM Cloud account or via third parties using VPN or DirectLink connections.
* HTTPS - Hypertext Transfer Protocol Secure (HTTPS) is used for Open Data Protocol (OData), REpresentational State Transfer (REST), and Simple Object Access Protocol (SOAP) Application Programming Interface (API). OData is a standard that defines a set of best practices for building and consuming RESTful APIs. REST is a type of API used to connect components in microservices architectures and integrate applications. SOAP is an API that uses Extensible Markup Language (XML) to send and receive messages between systems and applications. Applications can access through HTTPS on a publicly available IP, exposed by RISE with SAP Power Virtual Server or a through private network address ranges 
* ODBC/JDBC - Open Database Connectivity (ODBC) and Java Database Connectivity (JDBC) are standard APIs that allows applications to access data from database management systems such as SAP HANA. Applications can only access your SAP systems in RISE with SAP Power Virtual Server using ODBC/JDBC through private network address ranges and is, therefore, limited to applications hosted in your premises, in your IBM Cloud account or via third parties using VPN or DirectLink connections.

The system communications described above are facilitated by TCP/IP and your RISE with SAP Power Virtual Server can be accessed through the open network ports, when configured and opened by SAP for your use.

The diagram below, shows how the data connectors within your self-hosted integration runtime communicate with the SAP system hosted in SAP Power Virtual Server through the IBM Cloud private network. You can use security groups and network access control lists to limit which instances can communicate with the SAP system. HTTPS access can also requested from SAP from the public network.

![Figure 3. Communications](../images/communications.svg "Communications"){: caption="Communications" caption-side="bottom"}

You are responsible for deployment and operation of the self-hosted integration runtime within your IBM Cloud Account. RISE with SAP Power Virtual Server exposes the communication ports for your applications to use but has no knowledge or support for the connected application or service.

Contact SAP for details on communication paths available to you with RISE with SAP Power Virtual Server and the necessary steps to open them. SAP must also be contacted for any SAP license details for any implications accessing SAP data through any external applications.
