---

copyright:
  years: 2025
lastupdated: "2026-04-16"

keywords: SAP, RISE, PowerVS, RISE with SAP on PowerVS, SAP on IBM Cloud, Benefits of RISE with SAP on IBM Cloud, IBM Power Virtual Server, SAP modernization

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Get started
{: #get-started}

This documentation provides architectural considerations and implementation guidance for integrating SAP workloads with SAP Cloud ERP Private on {{site.data.keyword.powerSysFull}}.
{: shortdesc}

For more than half a century, enterprises have relied on IBM infrastructure to run mission critical SAP&reg; systems, ensuring high availability, performance, and the protection of sensitive business data. As organizations continue their transition to Cloud Enterprise Resource Planning (ERP), SAP now offers IBM {{site.data.keyword.powerSys_notm}} as a certified hyperscaler infrastructure option for SAP Cloud ERP Private, enabling enterprises to modernize at their own pace while leveraging their existing investments in IBM Power–based SAP landscapes.

IBM {{site.data.keyword.powerSys_notm}} is a family of configurable, multitenant virtual IBM Power servers that are deeply integrated with {{site.data.keyword.cloud_notm}} services. It provides flexible, secure, and scalable compute capacity for SAP enterprise workloads. This also includes support for key SAP platform components such as SAP Business Warehouse in SAP Business Data Cloud (BDC), giving organizations a consistent, cloud-ready data foundation when modernizing analytics and ERP landscapes.

SAP Cloud ERP Private — the new name for RISE with SAP’s private edition offering — combines Cloud ERP based on SAP S/4HANA&reg;, infrastructure, and services to help customers redefine their enterprise operating model. IBM {{site.data.keyword.powerSys_notm}} offers a unique benefit for customers running SAP on IBM Power: it enables a streamlined, low disruption move to SAP Cloud ERP Private by preserving existing architecture patterns while delivering the scalability and operational efficiency of a hyperscaler cloud.


## RISE with SAP
{: #rise-with-sap}

The [RISE with SAP](https://www.sap.com/products/erp/rise.html){: external} offering is an SAP&reg; managed cloud service that helps organizations using on-premise ERP software that includes SAP ERP, SAP ECC, and SAP S/4HANA, to migrate to the SAP Business Suite securely and smoothly. RISE with SAP is tailored to help larger enterprises migrate their existing ERP data, processes, and capabilities to SAP Cloud ERP Private.

RISE with SAP is a fully accredited cloud infrastructure-managed service that includes technical system operations, software support, and security services based on best-practice cloud architecture, and includes management of the operating system, SAP HANA database, and SAP Cloud ERP Private application.

RISE with SAP:

- Is a single contract with a unified service level agreement (SLA) for the entire solution stack, helping ensure consistent service quality across all components, simplifying procurement and management.
- Includes ongoing support and maintenance for the entire solution stack, including infrastructure, platform, and application layers by using certified subject matter experts (SME) who handle operating system management tasks, such as patches, monitoring, and maintenance.
- Has the ability to scale up or down as needed with flexible pricing based on usage and consumption.
- Has enhanced security and compliance features with built-in controls and monitoring to help protect data and meet regulatory requirements.
- Enables integration with SAP Business Technology Platform, which provides advanced analytics, AI, and machine learning capabilities to help businesses make data-driven decisions and improve operational efficiency.
- Encompasses partners and developers that provide a wide range of complementary solutions and services that enhance the RISE with SAP offering.

For more information, including an overview, methodology, and cloud operations see [RISE with SAP](https://www.sap.com/uk/products/erp/rise.html?gclsrc=aw.ds&gad_source=1&gbraid=0AAAAAoV5MAX5yS4NBq8up4zvuErMQIF-Z&gclid=Cj0KCQiA4-y8BhC3ARIsAHmjC_HSyZuyRqHhIBD6sHB0YK_splrNwnJxGbHB_82swpzRbvCCVq3pAxwaAmOtEALw_wcB){: external}.

## RISE with SAP on IBM {{site.data.keyword.powerSys_notm}}
{: #rise-with-sap-power-vs}


Using {{site.data.keyword.powerSysFull}}, the cloud-based version of the mission critical IBM Power server platform used for on-premises Enterprise Resource Planning (ERP), you can rapidly transform on-premises SAP ERP systems, modernize business processes, and become more agile. Known for its high security, scalability and reliability, IBM Power servers are engineered for fewer disruptions and facilitates faster migration, supported by the highly resilient and secured {{site.data.keyword.cloud_notm}} platform.

SAP Cloud ERP Private is the software in the RISE with SAP on IBM {{site.data.keyword.powerSys_notm}} service that holds the client’s mission critical data and business processes. SAP provides a managed private environment with multi-layer defense-in-depth architecture handling infrastructure and technical managed services in line with their service level agreement (SLA).

SAP Cloud ERP Private is a single-tenant managed private environment for clients where SAP creates a separate IBM Cloud Account in their IBM Cloud Enterprise Account for each customer. The application and database virtual server instances are solely dedicated to a single client.

The following table describes the high-level responsibilities for RISE with SAP on IBM {{site.data.keyword.powerSys_notm}}:

| **Area**                                              | **Responsible**                                    |
| ------------------------------------------------------| ---------------------------------------------------|
| Application Management                                | Application Management Provider (IBM or other SI)  |
| Development and Extensions                            | Application Management Provider (IBM or other SI)  |
| Implementation                                        | System Integrator (IBM or other SI)                |
| Integration                                           | System Integrator (IBM or other SI)                |
| Upgrade and Migration                                 | System Integrator (IBM or other SI)                |
| Security Management                                   | SAP                                                |
| Software Maintenance                                  | SAP                                                |
| NetWeaver Stack (SAP Basis)                           | SAP                                                |
| Database Management                                   | SAP                                                |
| Data Backup and Restore                               | SAP                                                |
| System Governance                                     | SAP                                                |
| Operating System, SDN, SDS, and SDC                   | SAP                                                |
| Virtualization                                        | SAP                                                |
| Servers                                               | SAP                                                |
| Storage                                               | SAP                                                |
| DC and Networking                                     | SAP                                                |
| Licenses                                              | SAP                                                |
| Tools and Services for Migration and Readiness Check  | SAP                                                |
| SAP Business Technology Platform                      | SAP                                                |
| SAP Business Network                                  | SAP                                                |
| SAP Business Process Intelligence                     | SAP                                                |
{: caption=" High-level responsibilities for RISE with SAP on IBM Power Virtual Server" caption-side="bottom"}

## IBM offerings and products
{: #ibm-offerings-and-products}

### RISE with SAP – Premium Supplier
{: #premium-supplier}

Premium Suppliers are SAP partners who have demonstrated expertise in RISE with SAP and offer a wide range of services. The IBM RISE with SAP – Premium Supplier is a service offered by IBM Consulting that:
- Delivers Premium Supplier Services to SAP under the same service level agreement as Standard RISE.
- Uses the IBM’s HA clustered solution allowing for 99.9% SLA around system availability under the extended service level agreement option from SAP.
- Are built on the same Technical Architecture as Standard RISE.
- IBM’s Well Architected Digital Operations Management Plane that is built on IBM’s own Cloud Tenant, giving clients more control.
- Enables better total cost of ownership (TCO) efficiency with incremental scalability.

The following table shows a comparison between RISE with SAP – Premium Supplier and RISE with SAP on IBM {{site.data.keyword.powerSys_notm}}:

| **Area**                                           | **RISE with SAP Responsible**                      |**RISE with SAP – Premium Supplier Responsible**|
| ---------------------------------------------------| ------------------------------------------------|------------------------------------------------|
| Application Management                             | Application Management Provider (IBM or other SI)  | Application Management Provider (IBM or other SI)                                       |
| Development and Extensions                         | Application Management Provider (IBM or other SI)  | Application Management Provider (IBM or other SI)                                       |
| Implementation                                     | System Integrator (IBM or other SI)                | System Integrator (IBM other SI)                                             |
| Integration                                        | System Integrator (IBM or other SI)                | System Integrator (IBM or other SI)                                             |
| Upgrade and Migration                              | System Integrator (IBM other SI)                   | System Integrator (IBM other SI)                                             |
| Security Management                                | SAP                                                | IBM Security                                        |
| Software Maintenance                               | SAP                                                | BASIS Services (SAP)                                           |
| NetWeaver Stack (SAP Basis)                        | SAP                                                | BASIS Services (SAP)                                           |
| Database Management                                | SAP                                                | BASIS Services (SAP)                                          |
| Data Backup and Restore                            | SAP                                                | IBM Platform Engineering (PES)                                          |
| System Governance                                  | SAP                                                | IBM Platform Engineering (PES)                                          |
| Operating System, SDN, SDS, and SDC                | SAP                                                | IBM Platform Engineering (PES)                                          |
| Virtualization                                     | SAP                                                | IBM Cloud                                          |
| Servers                                            | SAP                                                | IBM Cloud                                          |
| Storage                                            | SAP                                                | IBM Cloud                                          |
| DC and Networking                                  | SAP                                                | IBM Cloud                                          |
| Licenses                                           | SAP                                                | SAP                                            |
|Tools and Services for Migration and Readiness Check| SAP                                                | SAP                                            |
|SAP Business Technology Platform                     | SAP                                               | SAP                                            |
|SAP Business Network                                 | SAP                                               | SAP                                            |
|SAP Business Process Intelligence                    | SAP                                               | SAP                                            |
{: caption=" RISE with SAP – Premium Supplier and RISE with SAP on IBM Power Virtual Server" caption-side="bottom"}

## SAP offerings and products
{: #sap-offerings-and-products}

- [SAP Products A-Z](https://www.sap.com/uk/products/a-z.html){: external}
- [What Is SAP?](https://learning.sap-press.com/what-is-sap){: external}
- [List of SAP products](https://en.wikipedia.org/wiki/List_of_SAP_products){: external}
