---

copyright:
  years: 2025
lastupdated: 2025-06-03

keywords: SAP, RISE, PowerVS, RISE with SAP on PowerVS, SAP on IBM Cloud, Benefits of RISE with SAP on IBM Cloud, IBM Power Virtual Server, SAP modernization

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Surround workloads by platform
{: #surround-workloads-by-platform}

This section lists the available solution guides, reference architectures or deployable architectures by IBM Cloud platform.

A deployable architecture is cloud automation for deploying a common architectural pattern that combines one or more cloud resources. It is designed to provide simplified deployment by users, scalability, and modularity. See [What is a deployable architecture?](/docs/secure-enterprise?topic=secure-enterprise-understand-module-da#what-is-da).

An IBM Cloud project is a management tool that is designed to organize and provide visibility into a real-world project that exists in your organization. A project manages all of the configured instances of a deployable architecture and the resources that are related to the real-world reasons that they are deployed. See [https://cloud.ibm.com/docs/secure-enterprise?topic=secure-enterprise-understand-module-da#what-are-projects](https://cloud.ibm.com/docs/secure-enterprise?topic=secure-enterprise-understand-module-da#what-are-projects).

## IBM Cloud Virtual Private Cloud
{: #surround-workloads-by-platform-vpc}

IBM Cloud Virtual Private Cloud (VPC) is a highly resilient and highly secure software-defined network (SDN) on which you can build isolated private clouds for your business operations while maintaining essential public cloud benefits. You choose your compute, storage and networking resources and IBM provides maximum availability and scalability, plus various cost-effective options for your workload demands. IBM Cloud VPC is purpose-built for your cloud needs with solutions for VMware, SAP, and more. See [IBM Cloud VPC Solutions](https://www.ibm.com/cloud/vpc).

The following reference architectures are documented for non-RISE SAP on IBM Cloud VPC:

* [SAP HANA scale-out Reference Architecture](/docs/sap?topic=sap-refarch-hana-scaleout) - This reference architecture describes the Intel Bare Metal servers on Classic Infrastructure and Intel Virtual Servers in VPC Infrastructure (Gen2).
* [SAP NetWeaver 7.x on UNIX with Sybase on IBM Cloud VPC](/docs/sap?topic=sap-sap-refarch-nw-sybase) - This reference architecture describes SAP NetWeaver 7.x APAB stack, Java stack, and dual stack (ABAP+Java) architectural design on Virtual server instances on IBM Cloud VPC.
* [SAP NetWeaver 7.x on UNIX with Db2 on IBM Cloud VPC](/docs/sap?topic=sap-sap-refarch-nw-db2) - This reference architecture describes two deployments on Virtual server instances on IBM Cloud VPC using IBM Db2; standard and distributed.
* [SAP NetWeaver 7.x on Windows Servers with MS SQL on IBM Cloud VPC](/docs/sap?topic=sap-sap-refarch-nw-mssql) - This reference architecture describes two deployments on Virtual server instances on IBM Cloud VPC using Microsoft SQL; standard and distributed.
* [SAP NetWeaver 7.x with SAP HANA IBM Cloud VPC](/docs/sap?topic=sap-sap-refarch-nw-hana) - This reference architecture describes two deployments on Virtual server instances on IBM Cloud VPC using SAP HANA; single-host HANA system and multiple-host SAP HANA system.
* [SAP Solutions and IBM Cloud Intel Bare Metal Servers on VPC Infrastructure](/docs/sap?topic=sap-fast-path-site-map-intel-bm-vpc)
* [SAP Solutions and IBM Cloud Intel Virtual Servers on VPC Infrastructure](/docs/sap?topic=sap-fast-path-site-map-intel-vs-gen2)
* [Overview of SAP on VPC](/docs/pattern-sap-on-vpc?topic=pattern-sap-on-vpc-overview) - This pattern can be used as a guide to meet typical customer requirements and provide a base reference solution for a secure and resilient SAP NetWeaver and HANA or SAP NetWeaver and AnyDB deployment to IBM Cloud VPC.

The following reference architectures are documented for non-RISE, non-SAP on IBM Cloud VPC:

* [Microsoft Software on IBM Cloud](/docs/microsoft) - IBM Cloud has a strategic relationship with Microsoft to offer their suite of software. We offer their software natively in our cloud offerings and as Bring Your Own Licenses (BYOL). This solution guide discusses IBM Cloud Bare Metal servers in Classis as well as Microsoft SQL Server in VPC.
* [Red Hat OpenShift on VPC](/docs/pattern-openshift-vpc-mz-resiliency?topic=pattern-openshift-vpc-mz-resiliency-openshift-on-vpc) - The Red Hat OpenShift architecture is deployed on VPC servers across three availability zones within a region. From the IBM Cloud catalog, you can select from the compatible and recommended nodes that are available for Red Hat OpenShift on IBM Cloud. Worker pools are classified as variations of CPU, memory, and operating system characteristics. Choose the variation that's best suited to your use case. Shared Virtual Servers instances are used for worker nodes to run stateful applications in a production environment. Associated with this reference architecture are two deployable architectures:
  
    * [Red Hat OpenShift Container Platform on VPC landing zone](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-ocp-ra) - Red Hat OpenShift Container Platform on VPC landing zone is a deployable architecture solution that is based on the IBM Cloud for Financial Services reference architecture. It creates secure and compliant Red Hat OpenShift Container Platform workload clusters on a Virtual Private Cloud (VPC) network.
    * [Red Hat OpenShift Container Platform on VPC landing zone - QuickStart variation](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-roks-ra-qs) - The QuickStart variation of the Red Hat OpenShift Container Platform on VPC landing zone deployable architecture creates a fully customizable Virtual Private Cloud (VPC) environment in a single region. The solution provides a single Red Hat OpenShift cluster in a secure VPC for your workloads. The QuickStart variation is designed to deploy quickly for demonstration and development.

* [Web app multi-zone resiliency](/docs/pattern-vpc-vsi-multizone-resiliency?topic=pattern-vpc-vsi-multizone-resiliency-web-app-multi-zone) - The web app multi-zone resiliency architecture deploys a 3-tier web application on Virtual Servers for VPC by using compute, storage, and network cloud resources as well as other Cloud services provisioned across multiple availability zones within a single region.
* [Web app cross-region resiliency](/docs/pattern-vpc-vsi-cross-region-resiliency?topic=pattern-vpc-vsi-cross-region-resiliency-web-app-cross-region) - The web app cross-region resiliency architecture deploys a 3-tier web application on Virtual Servers for VPC using compute, storage, and network cloud resources as well as other Cloud services provisioned in multiple availability zones across two regions to protect from region-wide natural disasters or outages.
* [Deployable architecture for Maximo Application Suite](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-deployable-architecture-mas-components) - The IBM Maximo Application Suite deployable architecture provides a simple automated way to get started with Maximo Application Suite on IBM Cloud. Maximo Application Suite is a set of applications for asset monitoring, management, predictive maintenance, and reliability planning. It is a single, integrated cloud-based platform that uses Artificial Intelligence (AI), Internet of Things (IoT), and analytics to optimize performance, extend asset lifecycles, and reduce operational downtime and costs.
* [Dizzion Managed DaaS on IBM Cloud](https://www.ibm.com/cloud/dizzion) - Dizzion Managed Desktop as a Service (DaaS) on IBM Cloud can help enterprises build an agile, long-term remote work environment, using cloud desktops to optimize end-user performance, security and compliance. The solution can support a variety of challenging use cases, including streaming voice and video, compliant personal devices, and media-intense workloads.
* [IBM MQ SaaS](https://www.ibm.com/products/mq/saas) - IBM&reg; MQ SaaS offers secure and reliable messaging across multiple clouds. Utilise IBM MQ SaaS as a fully managed service with quick and easy setup. IBM’s solution handles upgrades, patches, and many operational management tasks, allowing you to focus on integrating with your applications.

### VPC for SAP HANA NetWeaver ABAP deployable architecture
{: #surround-workloads-by-platform-vpc-hana}

The [VPC for SAP HANA NetWeaver ABAP](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-sap-vpc-automation-hana-nw-abap-c0fc9daf-791b-42d2-9fe3-406f267b89ac-global) automation solution is designed for the deployment of a SAP NetWeaver application server VSI and a SAP HANA DB VSI in an existing VPC, using an existing bastion host with secure remote SSH access. It uses Terraform to deploy the VSIs and associated block storage and Ansible to customize the infrastructure and install SAP. This automation requires the following:

* VPC, subnet, security group.
* A deployment server, also known as a bastion server in the same VPC, with the SAP kits from the SAP Portal downloaded to it.

### VPC with Additional Application Server ABAP on Linux for SAP HANA deployable architecture
{: #surround-workloads-by-platform-vpc-add}

The [VPC with Additional Application Server ABAP on Linux for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-sap-vpc-automation-hana-nw-abap-aas-51f5ccbc-23fe-42d0-a17c-7a90b73da835-global) automation deploys a SAP NetWeaver application server VSI in an existing VPC. The automation has been designed to add an additional SAP NetWeaver application server after the [VPC for SAP HANA NetWeaver ABAP](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-sap-vpc-automation-hana-nw-abap-c0fc9daf-791b-42d2-9fe3-406f267b89ac-global) deployable architecture has been used. A Terraform script is used for the deployment of the VSI, in an existing VPC, that contains a subnet and a security group. An Ansible script is used to install and configure the SAP NetWeaver application server. This automation requires the following:

* VPC, subnet, security group.
* A deployment server, also known as a bastion server in the same VPC, with the SAP kits from the SAP Portal downloaded to it.

## IBM Cloud Power Virtual Server
{: #surround-workloads-by-platform-powervs}

IBM Power Virtual Server offers a powerful and flexible cloud platform with built in security, reliability, availability and performance, allowing clients to meet their requirements for a variety of complex and highly regulated workloads.

With the latest update to IBM Cloud Security and Compliance Center (SCC) Workload Protection, Power servers on IBM Cloud and on-premises are now supported for compliance posture management, bringing a new layer of security to your critical workloads running on PowerVS. This new capability ensures that critical enterprise applications and workloads like SAP, Oracle, and DB2, can be protected and monitored more efficiently with a comprehensive security and compliance solution.

SCC Workload Protection now provides compliance posture management capabilities for critical workloads on PowerVS, including AIX and Enterprise Linux on Power. With compliance posture management, these capabilities are designed to provide unified monitoring of your workloads’ posture to help access and manage compliance against regulatory and industry standards, such as CIS Benchmarks, in addition to advanced workload protection capabilities with vulnerability scanning and real-time threat detection for Linux on Power. See [Easily secure your IBM Cloud PowerVS Workloads with IBM Cloud Security and Compliance Center Workload Protection](https://www.ibm.com/new/announcements/easily-secure-your-ibm-cloud-powervs-workloads){: external}.

When a PowerVS workspace is created, automatically a SCC Workload Protection instance is created with cloud security posture management (CSPM) for IBM Cloud enabled enabled by default. See [About IBM Cloud Security Posture Management (CSPM)](docs/workload-protection?topic=workload-protection-about)

The following reference architectures are documented for non-RISE SAP on IBM Power Virtual Server:

* [SAP Solutions on IBM Power Virtual Server](/docs/sap?topic=sap-fast-path-site-map-power-vs)
* [SAP on Power Virtual Server](/docs/pattern-sap-on-powervs) -  This pattern illustrates a Single-Zone, Multi-Region design deployed to IBM Power Virtual Server, which can provide both DR and HA to provide 99.95 availability for an SAP NetWeaver/HANA or SAP NetWeaver/AnyDB solution to meet typical customer requirements.

The following reference architectures are documented for non-RISE, non-SAP SAP on IBM Power Virtual Server:

* [Oracle RAC on Power Virtual Server](/docs/pattern-oracle-rac-on-powervs?topic=pattern-oracle-rac-on-powervs-oracle-rac-on-powervs) - The reference architecture for Oracle RAC, High Availability, in a single zone region, represents a solution, based on best practices and use-cases.
* [Oracle Database Disaster Recovery on IBM PowerVS Cross Region](/docs/pattern-oracle-disaster-recovery-on-powervs?topic=pattern-oracle-disaster-recovery-on-powervs-Oracle-dr-ibm-pvs) - This reference architecture details how to design an Oracle Disaster recovery deployable architecture on IBM Power Virtual Server environment. This reference architecture assumes that there are x86 workloads hosted in the IBM Cloud VPC environment.

### Power Virtual Server with VPC landing zone - 'Standard Variation' deployable architecture
{: #surround-workloads-by-platform-pwr-with-vpc-std}

The [Power Virtual Server with VPC landing zone - 'Standard Variation'](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-deploy-arch-ibm-pvs-inf-standard) deployment of the Power Virtual Server with VPC landing zone creates VPC services and a Power Virtual Server workspace and interconnects them. A proxy service for public internet access from the PowerVS workspace is configured. You can optionally configure some management components on VPC (such as an NFS service, NTP forwarder, and DNS forwarder).

### Power Virtual Server with VPC landing zone - 'Standard Extend Variation' deployable architecture
{: #surround-workloads-by-platform-pwr-with-vpc-std-ext}

The [Power Virtual Server with VPC landing zone - 'Standard Extend Variation'](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-deploy-arch-ibm-pvs-inf-extension) creates an additional Power Virtual Server workspace and connects it with the already created Power Virtual Server with VPC landing zone. It builds on the existing Power Virtual Server with VPC landing zone deployed as a standard variation.

### Power Virtual Server with VPC landing zone - 'Quickstart Variation' deployable architecture
{: #surround-workloads-by-platform-pwr-with-vpc-quick}

The [Power Virtual Server with VPC landing zone - 'Quickstart Variation'](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-deploy-arch-ibm-pvs-inf-standard-plus-vsi) deployment of the Power Virtual Server with VPC landing zone creates VPC services, a Power Virtual Server workspace, and interconnects them. It also deploys a Power Virtual Server of chosen T-shirt size or custom configuration. Supported operating systems are AIX, IBMi, and Linux images. A proxy service for public internet access from the PowerVS workspace is configured. You can optionally configure some management components on VPC (such as an NFS service, NTP forwarder, and DNS forwarder).

### Power Virtual Server with VPC landing zone - as 'Import' deployment deployable architecture
{: #surround-workloads-by-platform-pwr-with-vpc-import}

The [Power Virtual Server with VPC landing zone - as 'Import' deployment](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-power-virtual-server-with-vpc-landing-zone-as-import-deployment) solution helps to install the deployable architecture 'Power Virtual Server for SAP HANA' on top of a pre-existing Power Virtual Server landscape. This import solution creates a schematics workspace by taking the pre-existing VPC and PowerVS infrastructure resource details as inputs. The ID of the existing schematics workspace will be the pre-requisite workspace ID required by this deployment.

### Power Virtual Server for SAP HANA - variation 'SAP ready PowerVS' deployable architecture
{: #surround-workloads-by-platform-pwr-hana-ready}

The [Power Virtual Server for SAP HANA](/docs/sap-powervs) deployable architecture is designed to assist you in deploying SAP ERP software landscapes into IBM Cloud on the IBM Power Virtual Server infrastructure. This is the second step in the deployment process for creating a full environment. Before starting this step, you should first deploy 'Power Virtual Server with VPC landing zone' deployable architecture. Once this is completed, you are prepared to deploy this deployable architecture.

The [Power Virtual Server for SAP HANA - variation 'SAP ready PowerVS'](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-sap-ready-to-go) variation of the Power Virtual Server for SAP HANA architecture creates a basic and expandable SAP system landscape. The variation builds on the foundation of the VPC landing zone and Power Virtual Server with VPC landing zone. PowerVS instances for SAP HANA, SAP NetWeaver, and optionally for shared SAP files are deployed and pre-configured for SAP installation. Services such as DNS, NTP, and NFS running in VPC and provided by Power Virtual Server with VPC landing zone are leveraged. The transit gateway provide the network bridge between the IBM Power infrastructure and the IBM Cloud VPC and public internet. The resulting SAP landscape leverages the services such as Activity Tracker, Cloud Object Storage, Key Management from the VPC landing zone and the network connectivity configuration provided by Power Virtual Server with VPC landing zone.

### Power Virtual Server for SAP HANA - variation 'SAP S/4HANA or BW/4HANA' deployable architecture
{: #surround-workloads-by-platformpwr-hana-hana}

The [Power Virtual Server for SAP HANA](/docs/sap-powervs) deployable architecture is designed to assist you in deploying SAP ERP software landscapes into IBM Cloud on the IBM Power Virtual Server infrastructure. This is the second step in the deployment process for creating a full environment. Before starting this step, you should first deploy 'Power Virtual Server with VPC landing zone' deployable architecture. Once this is completed, you are prepared to deploy this deployable architecture.

The [Power Virtual Server for SAP HANA - variation 'SAP S/4HANA or BW/4HANA'](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-sap-s4hana-bw4hana) - variation of the Power Virtual Server for SAP HANA architecture creates a basic and expandable SAP system landscape built on the foundation of Power Virtual Server with VPC landing zone. Power Virtual Server instances for SAP HANA, SAP NetWeaver, and optionally for shared SAP files are deployed and pre-configured for SAP installation. The S/4HANA or BW/4HANA solution is installed based on the selected version. Services such as DNS, NTP, and NFS running in VPC and provided by Power Virtual Server with VPC landing zone are leveraged. Transit gateway connections provide the network bridge between the IBM Power infrastructure and the IBM Cloud VPC and public internet. The resulting SAP landscape leverages the services such as Activity Tracker, Cloud Object Storage, Key Management from the VPC landing zone and the network connectivity configuration provided by Power Virtual Server with VPC landing zone.

## IBM Cloud Classic
{: #surround-workloads-by-platform-classic}

The IBM Cloud Classic IaaS environment leverages a traditional network architecture, best suited for lift and shift workloads so you can move applications quickly and keep the same architecture. See [IBM Cloud Bare Metal Servers on Classic Infrastructure](https://www.ibm.com/products/bare-metal-servers/classic?mhsrc=ibmsearch_a&mhq=classic%20infrastructure%20-%20ibm%20cloud), [IBM Cloud Virtual Servers on IBM Cloud Classic Infrastructure](https://www.ibm.com/products/virtual-servers-classic) and [Classic Infrastructure environment introduction](/docs/sap?topic=sap-classic-env-introduction).

The following reference architectures are documented for non-RISE SAP on IBM Cloud Classic:

[SAP Solutions and IBM Cloud Intel Bare Metal Servers on Classic Infrastructure](/docs/sap?topic=sap-fast-path-site-map-intel-bm)

The following documentation is applicable for non-RISE, non-SAP on IBM Cloud Classic:

* [IBM Bare Metal Servers for Oracle workloads](https://www.ibm.com/products/bare-metal-servers-oracle) - This document discusses the IBM Cloud servers that are certified to run Oracle Linux and Virtualization and Oracle Hardware Certification List (HCL) compliant. IBM Bare Metal Servers for Oracle workloads are true, raw-performance, no-hypervisor, single-tenant bare metal servers and feature the latest generation of Intel&reg; Xeon&reg; processors for advanced core and memory demands.
* [Gateway appliances](https://www.ibm.com/products/network-appliances) - Gateway appliances are devices that give you enhanced control over network traffic, let you accelerate your network’s performance, and give your network a security boost. Manage your physical and virtual networks for routing multiple VLANs, for firewalls, VPN, traffic shaping and more.

## IBM Cloud for VMware Solutions
{: #surround-workloads-by-platform-vmware}

[IBM Cloud for VMware Cloud Foundation as a Service](https://www.ibm.com/products/vmware/managed-services) is a managed service that delivers a VMware Cloud Director (VCD) based stack that enables businesses to build cloud computing environments that support their business needs. Whether opting for a single-tenant or multitenant model, IBM handles the configuration, capacity management, monitoring, patching, upgrades, and security of the underlying VMware infrastructure, through a highly available management plane, so you can quickly deploy your VMware-based cloud computing environments. You can purchase compute resources at the host level, leveraging several IBM Bare Metal Server and profiles, or on-demand compute resources at the vCPU, RAM, and Storage level. With our multi-tenant consumption model, you can start as small as 1 VM comprising 1vCPU, 1GB RAM, 20 GB vSAN, and 1 network efficiency edge.

[IBM Cloud for VMware Solutions](https://www.ibm.com/products/vmware) enables you to seamlessly migrate and modernize VMware workloads to the cloud, allowing you to leverage your existing investments for a consistent VMware experience—retaining the same level of access, security and control.

The following reference architecture are documented for non-RISE SAP on IBM Cloud for VMware Solutions:

* [SAP Solutions and IBM Cloud for VMware on Classic Infrastructure](/docs/sap?topic=sap-fast-path-site-map-vmware-sddc)
* [Solution design for the deployment of SAP to VMware Cloud Foundation (VCF) for Classic on IBM Cloud](/docs/pattern-sap-on-vcenter-server) - This pattern can be used as a guide to meet typical customer requirements and provide a base reference solution for a secure and resilient SAP NetWeaver and SAP HANA or SAP NetWeaver and SAP AnyDB deployment to VMware Cloud Foundation (VCF) for Classic on IBM Cloud. Broadcom provides guidelines for SAP HANA, see [Architecture guidelines and best practices for deployments of SAP HANA on VMware vSphere architecture and technical considerations guide](https://www.vmware.com/docs/sap_hana_on_vmware_vsphere_best_practices_guide-white-paper){: external}.

The following reference architectures are documented for non-RISE, non-SAP on IBM Cloud for VMware Solutions:

* [Three-tier web application on VCFaaS across MZR](/docs/vcfaas-on-mzr?topic=vcfaas-on-mzr-web-app-multizone) - This reference architecture outlines a resilient, multi-zone, 3-tier web application deployment on IBM Cloud&reg; for VMware Cloud Foundation as a Service (VCFaaS). Provision compute, storage, and network resources with other cloud services, all within a single region.
* [SQL Server Failover Cluster Instance on VMware vSAN Native](https://www.vmware.com/docs/sql-server-failover-cluster-instance-on-vmware-vsan-native){: external}.
* [Using Oracle RAC on a vSAN Datastore](https://knowledge.broadcom.com/external/article/327037/using-oracle-rac-on-a-vsan-datastore.html){: external}.

## IBM Cloud Services
{: #surround-workloads-by-platform-services}

IBM Cloud services is a suite of Platform as a Service (PaaS), and Software as a Service (SaaS) offerings hosted on the IBM Cloud platform. With these offerings you can consume the service without managing the infrastructure and software. To view these services see the IBM Cloud [Catalog](https://cloud.ibm.com/catalog?label%3Aservices=services#ibm_products). The following reference architectures are documented for non-RISE, non-SAP on IBM Cloud Services:

* [IBM Cloud Databases](/docs/cloud-databases) - The IBM Cloud&reg; Databases portfolio contains database-as-a-service offerings on IBM Cloud, including the following

    * [IBM Cloud Databases for PostgreSQL](/docs/databases-for-postgresql).
    * [IBM Cloud Databases for MongoDB](/docs/databases-for-mongodb).
    * [IBM Cloud Databases for Redis](/docs/databases-for-redis).
    * [IBM Cloud Databases for Elasticsearch](/docs/databases-for-elasticsearch).
    * [IBM Cloud Databases for MySQL](/docs/databases-for-mysql).
    * [IBM Cloud Messages for RabbitMQ](/docs/messages-for-rabbitmq).
    * [IBM Cloud Databases for EnterpriseDB](/docs/databases-for-enterprisedb).

* [IBM Cloud private connectivity offerings](/docs/private-connectivity?topic=private-connectivity-connect-privately-ibm-cloud) - This guide describes the various ways of connecting to IBM Cloud with a private connection using the following topologies:

    * Direct Link Dedicated - Single tenant connection to IBM Cloud Point of Presences (PoPs)
    * Direct Link Connect - Multi-tenant service provider connection to IBM Cloud PoPs
    * VPN (site-to-site) - VPN tunnel from on-premises firewall to IBM Cloud VPN
    * VPN (client-to-site) - VPN tunnel from laptop to IBM Cloud VPN
    * Satellite Connector - A layer-7, endpoint-oriented connection from IBM Cloud to access on-premises data source.

* [Observability](/docs/observability-hub) - IBM Cloud offers Observability services that you can use to monitor, troubleshoot, and understand the activity in your account. You can also use them to keep records for auditing and compliance. This guide describes the following services:
  
    * [IBM Cloud Logs](/docs/cloud-logs) - IBM Cloud Logs is a scalable logging service that persists logs and provides users with capabilities for querying, tailing, and visualizing logs.
    * [IBM Cloud Monitoring](/docs/monitoring) - IBM Cloud Monitoring is a cloud-native, and container-intelligence management system that you can include as part of your IBM Cloud architecture. Use it to gain operational visibility into the performance and health of your applications, services, and platforms.
    * [IBM Cloud Activity Tracker Event Routing](/docs/atracker) - Use IBM Cloud Activity Tracker Event Routing to configure how to route auditing events, both global and location-based event data, in your IBM Cloud. Auditing events are critical data for security operations and a key element for meeting compliance requirements. Control of the storage location is critical to building enterprise-grade solutions on the IBM Cloud.
    * [IBM Cloud Logs Routing](/docs/logs-router) - You can use IBM Cloud Logs Routing to collect and route IBM Cloud logs from your account to a configured target.
    * [IBM Cloud Metrics Routing](/docs/metrics-router) - Use IBM Cloud Metrics Routing to configure how to route platform metrics in your IBM Cloud account.

* [IBM Cloud Internet Services](https://www.ibm.com/products/cloud-internet-services) - IBM Cloud Internet Services brings market-leading security and performance to your external web content and internet applications before they reach the cloud.
* [Veeam on IBM Cloud](https://www.ibm.com/products/veeam) - Veeam on IBM Cloud can deliver reliable backup and predictable disaster recovery (DR) for virtual and physical workloads, wherever they reside—across your data center and the cloud.
* [IBM Cloud Backup](https://www.ibm.com/products/backup) - IBM Cloud Backup is a full-featured, agent-based backup and recovery system managed through a web interface. Back up data between IBM Cloud servers in one or more IBM Cloud global data centers.
* [Zerto on IBM Cloud](https://www.ibm.com/products/zerto) - Zerto provides disaster recovery and cloud mobility for your VMware workloads within a single, simple, scalable solution.
* [IBM Cloud Object Storage](https://www.ibm.com/products/cloud-object-storage/systems) - IBM Cloud&reg; Object Storage is a software-defined hyper-scale storage solution that runs on premises.
* [IBM Cloud Block Storage](https://www.ibm.com/products/block-storage) - High-performance data storage solutions with customizable IOPS and predictable billing.
* [IBM Cloud File Storage](https://www.ibm.com/products/file-storage) - Flash-backed, durable, fast and flexible NFS-based file storage—with customizable IOPS and predictable billing.
* [IBM Cloud DNS Services](https://www.ibm.com/products/dns) - IBM Cloud DNS Services offers public and private authoritative DNS services with fast response time, unparalleled redundancy and advanced security—managed through the IBM Cloud web interface or by API.
* [IBM Cloud Container Registry](https://www.ibm.com/products/container-registry) - Store and distribute container images in a fully managed private registry. Push private images to conveniently run them in the IBM Cloud&reg; Kubernetes Service and other runtime environments. Images are checked for security issues so you can make informed decisions about your deployments.

To use IBM Cloud services hosted in your IBM Cloud account directly with your SAP workloads hosted in RISE with SAP on Power Virtual Server, IBM Cloud VPC Virtual Private Endpoints will need to be utilized. See [About virtual private endpoint gateways](/docs/vpc?topic=vpc-about-vpe) and [VPE-enabled services](/docs/vpc?topic=vpc-vpe-supported-services#vpe-enabled-supported-services).

### IBM Cloud Essential Security and Observability Services deployable architecture
{: #surround-workloads-by-platform-services-observability}

The [IBM Cloud Essential Security and Observability Services](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-core-security-services-pattern) deployable architecture summarizes the deployment and best practices on IBM Cloud for setting essential security services and their associated dependencies. IBM Cloud's essential security services are crucial for ensuring robust security and compliance for cloud-based applications and data. Their primary goal is to provide a framework for secure and compliant IBM Cloud workloads. These services include:

* Key Protect - This service provides a secure and scalable way to manage encryption keys for your cloud applications. It ensures that sensitive data is protected by managing and safeguarding cryptographic keys, facilitating compliance with industry standards and regulatory requirements.
* Secrets Manager - This service helps in securely storing and managing sensitive information such as API keys, credentials, and certificates. By centralizing secret management, it reduces the risk of exposure and simplifies the process of accessing and rotating secrets, thereby enhancing the security posture.
* Security and Compliance Center - This platform offers a comprehensive suite of tools to assess, monitor, and maintain the security and compliance of your cloud environment. It provides insights and controls to help organizations meet regulatory requirements, adhere to best practices, and protect against threats.
* IBM Cloud Security and Compliance Center Workload Protection - This service offers features to protect workloads, get deep cloud and container visibility, posture management (compliance, benchmarks, CIEM), vulnerability scanning, forensics, and threat detection and blocking.
