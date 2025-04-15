---

copyright:
  years: 2025
lastupdated: 2025-04-11

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Get started
{: #get-started}

The following documentation provides considerations and guidance for integrating surround workloads with RISE with SAP on {{site.data.keyword.powerSysFull}}. For over half a century, enterprises have used IBM's infrastructure to host their mission-critical SAP&reg; systems for round-the-clock operations and safeguarding sensitive business data. As the next step to help accelerate their move to Cloud Enterprise Resource Planning (ERP), SAP will offer IBM Power Virtual Server as the hyperscaler cloud infrastructure for RISE with SAP.

IBM Power Virtual Server is a family of configurable, multi-tenant, virtual IBM Power servers with access to IBM Cloud services. You can provision flexible, secure, and scalable compute capacity for Power enterprise workloads. See [IBM Power Virtual Server](https://www.ibm.com/products/power-virtual-server) and [Getting started with IBM Power Virtual Server](/docs/power-iaas?topic=power-iaas-getting-started).

RISE with SAP brings together outcome-driven services, Cloud ERP with SAP S/4HANA&reg;, and additional platforms to rethink the enterprise operating model. IBM Power Virtual Server offers a unique advantage to the enterprises that run SAP landscape on IBM Power servers: It is designed for a faster and non-disruptive move to RISE with SAP. See [RISE with SAP on IBM Power Virtual Server](https://www.ibm.com/cloud/rise-with-sap){: external}.

Surround workloads communicate and interact with your SAP core systems, see [Surround workloads overview](/docs/rise-with-sap-on-powervs?topic=rise-with-sap-on-powervs-surround-overview). These surround workloads can be non-RISE SAP, non-SAP and be hosted in IBM Cloud, other clouds, on-premises, or Software as a Service SaaS products.
{: shortdesc}

## RISE with SAP
{: #get-started-rise-with-sap}

The RISE with SAP offering is a SAP&reg; managed cloud service that helps organizations using on-premise ERP software, that includes SAP ERP, SAP ECC, and SAP S/4HANA, to migrate to the SAP Cloud, securely and smoothly. RISE with SAP is tailored to help larger enterprises migrate their existing ERP data, processes, and capabilities to SAP S/4HANA Cloud Private Edition.

RISE with SAP is a fully accredited cloud infrastructure managed service that includes technical system operations, software support, and security services based on best-practice cloud architecture, and includes management of the operating system, SAP HANA database, and SAP S/4HANA Cloud Private Edition application.

RISE with SAP:

* is a single contract with a unified service-level agreement (SLA) for the entire solution stack, helping ensure consistent service quality across all components, simplifying procurement and management.
* includes ongoing support and maintenance for the entire solution stack, including infrastructure, platform, and application layers using certified subject-matter experts who handle operating system management tasks, such as patches, monitoring, and maintenance.
* has the ability to scale up or down as needed with flexible pricing based on usage and consumption.
* has enhanced security and compliance features with built-in controls and monitoring to help protect data and meet regulatory requirements.
* enables integration with SAP Business Technology Platform, which provides advanced analytics, AI, and machine learning capabilities to help businesses make data-driven decisions and improve operational efficiency.
* encompasses partners and developers that provide a wide range of complementary solutions and services that enhance the RISE with SAP offering.

For more information, including an overview, methodology, and cloud operations see [RISE with SAP](https://www.sap.com/uk/products/erp/rise.html?gclsrc=aw.ds&gad_source=1&gbraid=0AAAAAoV5MAX5yS4NBq8up4zvuErMQIF-Z&gclid=Cj0KCQiA4-y8BhC3ARIsAHmjC_HSyZuyRqHhIBD6sHB0YK_splrNwnJxGbHB_82swpzRbvCCVq3pAxwaAmOtEALw_wcB){: external}.

## RISE with SAP on IBM Power Virtual Server
{: #get-started-rise-with-sap-power-vs}

Using {{site.data.keyword.powerSysFull}}, the cloud-based version of the mission-critical IBM Power server platform used for on-premises Enterprise Resource Planning (ERP), you can rapidly transform on-premises SAP ERP systems, modernize business processes and become more agile. Known for its high security, scalability and reliability, IBM Power servers are engineered for fewer disruptions and facilitates faster migration, supported by the highly resilient and secured IBM Cloud platform.

SAP S/4HANA Cloud Private Edition is the software in the RISE with SAP on IBM Power Virtual Server service that holds the client’s mission critical data and business processes. SAP Enterprise Cloud Services (ECS) provides a managed private environment with multi-layer defense in depth architecture handling infrastructure and technical managed services in line with their Service Level Agreement (SLA).

SAP S/4HANA Cloud Private Edition is a single-tenant managed private environment for clients where SAP creates a separate IBM Cloud Account in their IBM Cloud Enterprise Account for each customer. The application and database virtual server instances are solely dedicated to a single client.

The following table describes the high-level responsibilities for RISE with SAP on IBM Power Virtual Server:

| Area | Responsible |
|:---------|:----------|
| Application Management | Application Management Provider (IBM/Other SI) |
| Development & Extensions | Application Management Provider (IBM/Other SI) |
| Implementation | System Integrator (IBM/Other SI) |
| Integration | System Integrator (IBM/Other SI) |
| Upgrade / Migration | System Integrator (IBM/Other SI) |
| Security Management | SAP |
| Software Maintenance | SAP |
| NetWeaver Stack (SAP Basis) | SAP |
| Database Management | SAP |
| Data Backup and Restore | SAP |
| System Governance | SAP |
| Operating System / SDN / SDS / SDC | SAP |
| Virtualization | SAP |
| Servers | SAP |
| Storage | SAP |
| DC and Networking | SAP |
| Licenses | SAP |
| Tools & Services for Migration & Readiness Check | SAP |
| SAP Business Technology Platform | SAP |
| SAP Business Network | SAP |
| SAP Business Process Intelligence | SAP |
{: caption="RISE with SAP on IBM Power Virtual Server Responsibilities" caption-side="bottom"}

SAP owns and manages the IBM Cloud account where RISE with SAP on Power Virtual Server is deployed, and is responsible for the IBM Cloud services used to serve your SAP landscape on IBM Cloud.
{: note}

For more information, including an overview, benefits, the IBM investment program, IBM Transformation Suite for SAP applications, transformation in action, an IDC Whitepaper, and next steps see [RISE with SAP on IBM Power Virtual Server](https://www.ibm.com/cloud/rise-with-sap){: external}. The next steps includes a link to [schedule a meeting with IBM](https://www.ibm.com/account/reg/us-en/signup?formid=urx-53520){: external}.

## Surround workloads
{: #get-started-surround-workloads}

When considering moving your SAP systems to RISE with SAP on IBM Power Virtual Server, you also need to consider the surround workloads. These surround workloads communicate and interact with your SAP core systems. You should consider moving these surround workloads to an IBM Cloud account peered with RISE with SAP on IBM Power Virtual Server to enable low latency connections, innovation, scalability and resiliency.

Once moved to IBM Cloud, you can easily and quickly create new surround workloads leveraging IBM Cloud services such as AI and Machine Learning with Watsonx, IBM’s data fabric, IoT Integration, cloud native applications using Red Hat OpenShift, key management, logging and monitoring, security and compliance with IBM Cloud Security and Compliance Centre and Workload Protection. For further information see:

* [Surround workloads overview](/docs/rise-with-sap-on-powervs?topic=rise-with-sap-on-powervs-surround-overview).
* [Surround workloads by platform](/docs/rise-with-sap-on-powervs?topic=rise-with-sap-on-powervs-surround-workloads-by-platform).
* [Surround workloads by use-case](/docs/rise-with-sap-on-powervs?topic=rise-with-sap-on-powervs-surround-workloads-by-use-case).
* [Surround Workloads for RISE on IBM PowerVS: Unlock the Full Power of SAP](https://community.ibm.com/community/user/blogs/lauri-mcinnis/2025/04/03/surround-workloads-for-rise-on-ibm-powerv).
* [Realize the promise of AI with watsonx](https://www.ibm.com/watsonx).
* [Data fabric solutions](https://www.ibm.com/data-fabric).
* [IoT solutions](https://www.ibm.com/cloud/internet-of-things).
* [Container solutions](https://www.ibm.com/containers).
* [IBM Key Protect for IBM Cloud](https://www.ibm.com/products/key-protect).
* [IBM Cloud Hyper Protect Crypto Services](https://www.ibm.com/products/hyper-protect-crypto).
* [IBM Cloud Logs](https://www.ibm.com/products/cloud-logs).
* [IBM Cloud Monitoring](https://www.ibm.com/products/cloud-monitoring)
* [IBM Security and Compliance Center](https://www.ibm.com/products/security-and-compliance-center).
* [Getting started with IBM Cloud Security and Compliance Center Workload Protection](/docs/workload-protection?topic=workload-protection-getting-started).

You must create a separate IBM Cloud account or use your existing IBM Cloud account that is not managed by SAP for hosting existing or creating new surround workloads with IBM Cloud services.
{: note}

## Surround workloads professional services
{: #get-started-surround-workloads-professional-services}

IBM Technology Expert Labs-Cloud is a professional services organization powered by an experienced team of IBM Cloud specialists with deep technical expertise, valuable tools, and proven methodologies to architect and build IBM Cloud solutions. By teaming with IBM Technology Expert Labs–Cloud, clients can improve the time to value of their IBM Cloud investment by taking the guesswork, re-work and on-the-job learning out of adopting IBM Cloud technologies. See [IBM Technology Expert Labs – Cloud](https://www.ibm.com/cloud/expert-labs).

## Surround workloads managed services
{: #get-started-surround-workloads-managed-services}

IBM Cloud Platform Engineering Services designs, implements and operates complex hybrid cloud infrastructure. PRISM, IBM’s cloud management platform for automated planning, provisioning, and management of workloads on multi-cloud environments, integrates with cloud-native services, IBM and third-party tools to provide a single pane of glass and a unified services delivery model. The services use [IBM Consulting AIOps](https://www.ibm.com/consulting/aiops), which leverages generative AI and Machine Learning, to autonomously manage IT by observing processes and solutions, detecting anomalies, predicting outages, analyzing their impact on business, and prescribing solutions to proactively avoid them. See [Cloud Platform Engineering Services](https://www.ibm.com/consulting/platform-engineering-services)

## IBM Transformation Suite for SAP Applications
{: #get-started-transformation-suite}

To further accelerate Cloud ERP migration, IBM Transformation Suite for SAP Applications brings software and services from IBM and partners such as SNP that automates essential migration tasks, including technical assessments, data and code migration, code analysis, and automated testing.

With the IBM Transformation Suite for SAP Applications, organizations can:

* Accelerate the transition to SAP S/4HANA.
* Unlock the potential of RISE with SAP.
* Simplify their IT landscape while driving innovation.

For more information on IBM Transformation Suite for SAP Applications, see [Accelerate your SAP S/4HANA journey with IBM Transformation Suite for SAP Applications](https://www.ibm.com/new/announcements/accelerate-your-sap-s-4hana-journey-with-ibm-transformation-suite-for-sap-applications).

## Migration Acceleration Program
{: #get-started-map}

The migration acceleration program for IBM Cloud is designed to help you assess, plan and migrate your enterprise workloads, data and applications to IBM Cloud. This program provides technology accelerators and cloud credits for IBM Cloud solutions for IBM Power Virtual Server, VMware and SAP workloads. The goal is to meet you where you are in your cloud-adoption journey, with a streamlined migration process that helps you achieve your goals while reducing risk and offsetting the initial migration costs. See [Migration acceleration program for IBM Cloud](https://www.ibm.com/downloads/documents/us-en/10c317759fd40154).

## Next Steps
{: #get-started-next-steps}

To review the following topics for RISE with SAP on IBM Power Virtual Server, see [RISE with SAP on IBM Power Virtual Server](https://www.ibm.com/cloud/rise-with-sap){: external}.

* Overview.
* Benefits.
* Investment program.
* IBM Transformation Suite for SAP.
* Applications.
* Transformation in action.
* IDC Whitepaper.
* Next steps.

To review the following topics for non-RISE SAP, see [IBM Cloud for SAP](https://www.ibm.com/cloud/sap){: external}.

* Benefits.
* ROI of IBM Cloud for SAP.
* RISE with SAP.
* Solutions for SAP HANA and S/4HANA.
* Solutions for SAP NetWeaver.
* Case studies.
* Migration Acceleration Program.
* Business Partner Ecosystem.
* Community Resources.
* Next steps.

For non-SAP, non-RISE surround workloads, see [IBM Cloud: AI-ready, secure, and hybrid by design](https://www.ibm.com/cloud){: external}.
