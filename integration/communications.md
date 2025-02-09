---

copyright:
  years: 2025
lastupdated: 2025-02-09

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# System communication with RISE with SAP Power Virtual Server
{: #integration-system-communication}

Your RISE with SAP {{site.data.keyword.powerSysFull}} systems allow the following system communications:

* RFC -  Remote Function Calls (RFC) are a standard SAP® interface that allows communication between SAP systems and allows connections for functions such as Business Application Programming Interface (BAPI) and Intermediate Document (IDoc). BAPI is a standard SAP application interface that helps to integrate non-SAP applications with the SAP business process and enables providing data entry into the SAP system. IDoc is a standard format for exchanging business transaction data between SAP applications and non-SAP systemsIDoc, Applications can only access your SAP systems in RISE with SAP Power Virtual Server using RFC through private network address ranges and is, therefore, limited to applications hosted in your premises, in your IBM Cloud account or via third parties using VPN or DirectLink connections.
* HTTPS - Hypertext Transfer Protocol Secure (HTTPS) is used for Open Data Protocol (OData), REpresentational State Transfer (REST), and Simple Object Access Protocol (SOAP) Application Programming Interface (API). OData is a standard that defines a set of best practices for building and consuming RESTful APIs. REST is a type of API used to connect components in microservices architectures and integrate applications. SOAP is an API that uses Extensible Markup Language (XML) to send and receive messages between systems and applications. Applications can access through HTTPS on a publicly available IP, exposed by RISE with SAP Power Virtual Server or a through private network address ranges 
* ODBC/JDBC - Open Database Connectivity (ODBC) and Java Database Connectivity (JDBC) are standard APIs that allows applications to access data from database management systems such as SAP HANA. Applications can only access your SAP systems in RISE with SAP Power Virtual Server using ODBC/JDBC through private network address ranges and is, therefore, limited to applications hosted in your premises, in your IBM Cloud account or via third parties using VPN or DirectLink connections.

The system communications described above are facilitated by TCP/IP and your RISE with SAP Power Virtual Server can be accessed through the open network ports, when configured and opened by SAP for your use.

The diagram below, shows how the data connectors within your self-hosted integration runtime communicate with the SAP system hosted in SAP Power Virtual Server through the IBM Cloud private network. You can use security groups and network access control lists to limit which instances can communicate with the SAP system. HTTPS access can also requested from SAP from the public network.

![Figure 1. Communications](../images/communications.svg "Communications"){: caption="Communications" caption-side="bottom"}

You are responsible for deployment and operation of the self-hosted integration runtime within your IBM Cloud Account. RISE with SAP Power Virtual Server exposes the communication ports for your applications to use but has no knowledge or support for the connected application or service.

Contact SAP for details on communication paths available to you with RISE with SAP Power Virtual Server and the necessary steps to open them. SAP must also be contacted for any SAP license details for any implications accessing SAP data through any external applications.
