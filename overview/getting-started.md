---

copyright:
  years: 2025
lastupdated: 2025-02-07

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}


# Get started
{: #get-started}

The following documentation provides considerations and guidance for RISE with SAP on {{site.data.keyword.powerSysFull}}. For over half a century, enterprises have used IBM's infrastructure to host their mission-critical SAP® systems for round-the-clock operations and safeguarding sensitive business data. As the next step to help accelerate their move to Cloud Enterprise Resource Planning (ERP), SAP will offer IBM Power Virtual Server as the hyperscaler cloud infrastructure for RISE with SAP.  

RISE with SAP brings together outcome-driven services, Cloud ERP with SAP S/4HANA®, and additional platforms to rethink the enterprise operating model. IBM Power Virtual Server offers a unique advantage to the enterprises that run SAP landscape on IBM Power servers: It is designed for a faster and non-disruptive move to RISE with SAP. See [RISE with SAP on IBM Power Virtual Server](https://www.ibm.com/cloud/rise-with-sap){: external}. 
{: shortdesc}

## Before you begin
{: #get-started-before-you-begin}

Review the documentation at the following locations:

* [RISE with SAP](https://www.sap.com/uk/products/erp/rise.html){: external}
* [RISE with SAP on IBM Power Virtual Server](https://www.ibm.com/cloud/rise-with-sap){: external}
* [Overview of IBM Cloud for SAP](/docs/sap?topic=sap-overview-sap-offerings-overview)

It is helpful that you have an understanding of SAP terminology. The following sections provides a short description

### SAP ERP
{: #get-started-sap-erp}

SAP Enterprise Resource Planning (ERP) made its first appearance in 1972 and known as SAP R/2, an early mainframe-based ERP software system. In the 1990s, SAP R/3 brought ERP technology to the client-server environment. SAP R/3 was superseded by SAP ECC SAP introduced SAP S/4HANA, an ERP suite that used the power of in-memory computing to deliver faster processing and real-time analytics. Later, SAP expanded this vision with SAP S/4HANA Cloud, a cloud ERP system that offered the benefits of enterprise resource planning with the cost-effectiveness and scalability of the cloud.

SAP ERP is an integrated software solution that incorporates the key business functions of the organization i.e. Material Management, Sales and Distribution, Finance, Human Resources etc. SAP incorporates these functions as business modules. These business modules are developed in Advanced Business Application Programming (ABAP) while the Enterprise Portal (EP) and Process Integration (PI) modules are developed mostly in Java. These modules are deployed on application Servers i.e. ABAP Web Application Server for ABAP modules and Java Web Application Servers for Java modules.

SAP NetWeaver is the runtime environment for the SAP applications and is built primarily using the ABAP programming language, but also uses C, C++, and Java.

In large organizations, many of the business functions use their own proprietary tools which run alongside to the SAP ERP system. These are often called legacy systems, or in this documentation surround workloads. These surround workloads need to be integrated into the SAP ERP system using SAP PI.

Additionally, in these large organizations, SAP ERP does not consist of a single system but several integrated systems i.e. CRM, SRM and FICO etc. SAP PI to provide a single point of integration for all systems to provide end to end integration between SAP and non-SAP applications inside and outside the organization boundary.

### SAP ECC
{: #get-started-sap-ecc}

SAP ERP Central Component (ECC) is the previous generation of ERP and has been replaced with SAP S/4HANA. It is also known as SAP ECC with AnyDB. SAP ECC is the core business product inside SAP Business Suite, and provides an integrated and updated overview of an organization’s core business processes–from financial to human resources.

### SAP S/4HANA
{: #get-started-sap-s4hana}

SAP S/4HANA is the ERP designed to run solely on SAP HANA and does not run on any other database. It was launched in 2015, and users can choose between a cloud solution, an on-premise solution, or a combination of both. Many companies are planning the migration over to S/4HANA using SAP's Activate framework due to SAP ending support for ECC and previous versions in 2027.

* SAP S/4HANA Cloud Public Edition - This multi-tenanted software-as-a-service (SaaS) solution allows businesses to share the same cloud infrastructure and software instance, however, each business’s data is securely separated, helping ensure privacy and security. The benefit of this model is that it’s cost-effective, as resources are shared among many users, with updates or maintenance automatically applied across all tenants. However, customization options are typically more limited due to the shared infrastructure.
* SAP S/4HANA Cloud Private Edition - This private managed cloud offering is a more tailored solution to meet specific business needs. In a private managed cloud, each business has its own dedicated, infrastructure and software instance. This means the company has full control over its environment, allowing for greater customization and flexibility. SAP S/4HANA Cloud Private Edition is used in RISE with SAP on Power Virtual Server.

### SAP NetWeaver Process Integration
{: #get-started-sap-pi}

SAP NetWeaver Process Integration (SAP PI) is SAP's enterprise application integration (EAI) software, a component of the NetWeaver product group used to facilitate the exchange of information among a company's internal software and systems and those of external parties.

### SAP Process Orchestration
{: #get-started-sap-po}

SAP Process Orchestration (PO) is a tool that makes it easy to synchronize data between different systems to automate and optimize business processes. PO has all the functionality of SAP PI in a single Java stack plus unified features such as Business Rule Management (BRM), Business Process Management (BPM), Enterprise Service Repository (ESR), B2B Collaboration and cloud integration, and for application integration.

### SAP Global Trade Services
{: #get-started-sap-gts}

SAP Global Trade Services (GTS) is software that allows organizations to support and define import and export trade processes in SAP ERP. GTS reduces the time and costs of complying with global trade regulations and provides visibility into the supply chain while goods are in transit.

### SAP Business Technology Platform
{: #get-started-sap-btp}

SAP Business Technology Platform (BTP) is a SaaS product that runs in the SAP Cloud. The SAP Cloud is a global network of data centers that include SAP’s data centers as well as public cloud providers such as Amazon Web Services (AWS) and Microsoft Azure, Google Cloud Platform (GCP) and Alibaba Cloud. The SAP Cloud provides lot of flexibility for those enterprises that want to co-locate SAP BTP along with their existing workloads. Once a customer subscribes to SAP BTP, they can create sub-accounts for extension and integration scenarios on any of the available regions/IaaS providers. 

SAP BTP is a flexible and scalable cloud-based platform that provides enterprises with the tools and services to build, deploy, and manage their custom applications securely and efficiently.

SAP BTP exposes a catalog of services which customers can subscribe to. Some of these services such as PostgreSQL and Object Store, for example, which leverages the underlying cloud providers capabilities while others SAP build on the cloud providers infrastructure.

To provide access to the SAP BTP SaaS from their SAP systems, SAP Cloud Connectors are deployed in the on-premise or cloud locations. SAP systems can be connected to multiple SAP BTP SaaS locations for redundancy.

SAP Private Link Service in SAP BTP allows private connectivity between the SAP BTP services to the SAP systems in their own Cloud accounts. The SAP Private Link Service leverages the cloud providers underlying service. For example, in AWS SAP Private Link Service leverages AWS PrivateLink and allows access to selected AWS services including; Amazon Simple Storage Service (S3) and Amazon Simple Notification Service (SNS).

### GROW and RISE with SAP
{: #get-started-sap-grow-and-rise}

SAP offers ERP SaaS solutions for companies of all sizes with the following:

* GROW with SAP - A complete offering of solutions, adoption acceleration services, community, and learning so companies of all sizes can implement SAP S/4HANA Cloud Public Edition.
* RISE with SAP - A comprehensive package that includes an AI-enabled SAP S/4HANA Cloud Private Edition that’s managed and optimized by SAP. It provides services and tools so you can migrate on-premise systems, transform business processes, drive continuous innovation, and unlock cloud agility.

## Next steps
{: #get-started-next-steps}

Review the documentation on this site starting with the [Overview](/docs/rise-with-sap-on-powervs?topic=overview)
