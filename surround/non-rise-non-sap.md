---

copyright:
  years: 2025
lastupdated: 2025-02-08

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Non-RISE non-SAP surround workloads
{: #non-rise-non-sap-surround-workloads}

Surround non-RISE non-SAP® workloads are those workloads that currently reside alongside your on-premise SAP systems hosted on {{site.data.keyword.IBM}} Power that you intend to migrate to IBM Cloud because they are tightly coupled to your SAP systems hosted in RISE with SAP on IBM Power Virtual Server.

![Figure 1. Non-RISE non-SAP surround workloads](../images/non-sap.svg "Non-RISE non-SAP surround workloads"){: caption="Non-RISE non-SAP surround workloads" caption-side="bottom"}

These surround non-rise non-SAP workloads cannot be hosted in the SAP owned RISE with SAP on IBM Power Virtual Server IBM Account, however, they can be migrated to your IBM Cloud account and peered with the SAP owned RISE with SAP on IBM Power Virtual Server IBM Account.

![Figure 2. Peering](../images/peering.svg "Peering"){: caption="peering" caption-side="bottom"}

## Solution guides for non-RISE non-SAP workloads
{: #non-rise-non-sap-surround-workloads-guides-workloads}

IBM Cloud solution guides for non-RISE non-SAP workloads include the following:

* [Microsoft Software on IBM Cloud](/docs/microsoft) - IBM Cloud has a strategic relationship with Microsoft to offer their suite of software. We offer their software natively in our cloud offerings and as Bring Your Own Licenses (BYOL). This solution guide discusses IBM Cloud Bare Metal servers in Classis as well as Microsoft SQL Server in VPC.
* [Oracle RAC on Power Virtual Server](/docs/pattern-oracle-rac-on-powervs?topic=pattern-oracle-rac-on-powervs-oracle-rac-on-powervs) - The reference architecture for Oracle RAC, High Availability, in a single zone region, represents a solution, based on best practices and use-cases.
* [Oracle Database Disaster Recovery on IBM PowerVS Cross Region](/docs/pattern-oracle-disaster-recovery-on-powervs?topic=pattern-oracle-disaster-recovery-on-powervs-Oracle-dr-ibm-pvs) - This reference architecture details how to design an Oracle Disaster recovery deployable architecture on IBM Power Virtual Server environment. This reference architecture assumes that there are x86 workloads hosted in the IBM Cloud VPC environment.
* [IBM Bare Metal Servers for Oracle workloads](https://www.ibm.com/products/bare-metal-servers-oracle) - This document discusses the IBM Cloud servers that are certified to run Oracle Linux and Virtualization and Oracle Hardware Certification List (HCL) compliant. IBM Bare Metal Servers for Oracle workloads are true, raw-performance, no-hypervisor, single-tenant bare metal servers and feature the latest generation of Intel® Xeon® processors for advanced core and memory demands.
* [Red Hat OpenShift on VPC](/docs/pattern-openshift-vpc-mz-resiliency?topic=pattern-openshift-vpc-mz-resiliency-openshift-on-vpc) - The Red Hat OpenShift architecture is deployed on VPC servers across three availability zones within a region. From the IBM Cloud catalog, you can select from the compatible and recommended nodes that are available for Red Hat OpenShift on IBM Cloud. Worker pools are classified as variations of CPU, memory, and operating system characteristics. Choose the variation that's best suited to your use case. Shared Virtual Servers instances are used for worker nodes to run stateful applications in a production environment. Associated with this reference architecture are two deployable architectures:
  
    * [Red Hat OpenShift Container Platform on VPC landing zone](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-ocp-ra) - Red Hat OpenShift Container Platform on VPC landing zone is a deployable architecture solution that is based on the IBM Cloud for Financial Services reference architecture. It creates secure and compliant Red Hat OpenShift Container Platform workload clusters on a Virtual Private Cloud (VPC) network.
    * [Red Hat OpenShift Container Platform on VPC landing zone - QuickStart variation](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-roks-ra-qs) - The QuickStart variation of the Red Hat OpenShift Container Platform on VPC landing zone deployable architecture creates a fully customizable Virtual Private Cloud (VPC) environment in a single region. The solution provides a single Red Hat OpenShift cluster in a secure VPC for your workloads. The QuickStart variation is designed to deploy quickly for demonstration and development.

* [Three-tier web application on VCFaaS across MZR](/docs/vcfaas-on-mzr?topic=vcfaas-on-mzr-web-app-multizone) - This reference architecture outlines a resilient, multi-zone, 3-tier web application deployment on IBM Cloud® for VMware Cloud Foundation as a Service (VCFaaS). Provision compute, storage, and network resources with other cloud services, all within a single region.
* [Web app multi-zone resiliency](/docs/pattern-vpc-vsi-multizone-resiliency?topic=pattern-vpc-vsi-multizone-resiliency-web-app-multi-zone) - The web app multi-zone resiliency architecture deploys a 3-tier web application on Virtual Servers for VPC by using compute, storage, and network cloud resources as well as other Cloud services provisioned across multiple availability zones within a single region.
* [Web app cross-region resiliency](/docs/pattern-vpc-vsi-cross-region-resiliency?topic=pattern-vpc-vsi-cross-region-resiliency-web-app-cross-region) - The web app cross-region resiliency architecture deploys a 3-tier web application on Virtual Servers for VPC using compute, storage, and network cloud resources as well as other Cloud services provisioned in multiple availability zones across two regions to protect from region-wide natural disasters or outages.
* [IBM Cloud Databases](/docs/cloud-databases) - The IBM Cloud® Databases portfolio contains database-as-a-service offerings on IBM Cloud, including the following

    * [IBM Cloud Databases for PostgreSQL](/docs/databases-for-postgresql)
    * [IBM Cloud Databases for MongoDB](/docs/databases-for-mongodb)
    * [IBM Cloud Databases for Redis](/docs/databases-for-redis)
    * [IBM Cloud Databases for Elasticsearch](/docs/databases-for-elasticsearch)
    * [IBM Cloud Databases for MySQL](/docs/databases-for-mysql)
    * [IBM Cloud Messages for RabbitMQ](/docs/messages-for-rabbitmq)
    * [IBM Cloud Databases for EnterpriseDB](/docs/databases-for-enterprisedb)

* [Deployable architecture for Maximo Application Suite](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-deployable-architecture-mas-components) - The IBM Maximo Application Suite deployable architecture provides a simple automated way to get started with Maximo Application Suite on IBM Cloud. Maximo Application Suite is a set of applications for asset monitoring, management, predictive maintenance, and reliability planning. It is a single, integrated cloud-based platform that uses Artificial Intelligence (AI), Internet of Things (IoT), and analytics to optimize performance, extend asset lifecycles, and reduce operational downtime and costs.
* [Dizzion Managed DaaS on IBM Cloud](https://www.ibm.com/cloud/dizzion) - Dizzion Managed Desktop as a Service (DaaS) on IBM Cloud can help enterprises build an agile, long-term remote work environment, using cloud desktops to optimize end-user performance, security and compliance. The solution can support a variety of challenging use cases, including streaming voice and video, compliant personal devices, and media-intense workloads.
* [IBM MQ SaaS](https://www.ibm.com/products/mq/saas) - IBM® MQ SaaS offers secure and reliable messaging across multiple clouds. Utilise IBM MQ SaaS as a fully managed service with quick and easy setup. IBM’s solution handles upgrades, patches, and many operational management tasks, allowing you to focus on integrating with your applications.

Broadcom provide VMware solution guidance documentation including the following:

* [SQL Server Failover Cluster Instance on VMware vSAN Native](https://www.vmware.com/docs/sql-server-failover-cluster-instance-on-vmware-vsan-native)
* [Using Oracle RAC on a vSAN Datastore](https://knowledge.broadcom.com/external/article/327037/using-oracle-rac-on-a-vsan-datastore.html)

## Solution guides to assist in migration and operations
{: #non-rise-non-sap-surround-workloads-guides-mig-ops}

These solution guides and product guides focus on how you can migrate to IBM Cloud and re-design existing processes to take advantage of IBM Cloud products:

* [IBM Cloud Essential Security and Observability Services](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-core-security-services-pattern) - This reference architecture summarizes the deployment and best practices on IBM Cloud for setting essential security services and their associated dependencies. IBM Cloud's essential security services are crucial for ensuring robust security and compliance for cloud-based applications and data. Their primary goal is to provide a framework for secure and compliant IBM Cloud workloads. These services include:

    * Key Protect - This service provides a secure and scalable way to manage encryption keys for your cloud applications. It ensures that sensitive data is protected by managing and safeguarding cryptographic keys, facilitating compliance with industry standards and regulatory requirements.
    * Secrets Manager - This service helps in securely storing and managing sensitive information such as API keys, credentials, and certificates. By centralizing secret management, it reduces the risk of exposure and simplifies the process of accessing and rotating secrets, thereby enhancing the security posture.
    * Security and Compliance Center - This platform offers a comprehensive suite of tools to assess, monitor, and maintain the security and compliance of your cloud environment. It provides insights and controls to help organizations meet regulatory requirements, adhere to best practices, and protect against threats.
    * IBM Cloud Security and Compliance Center Workload Protection - This service offers features to protect workloads, get deep cloud and container visibility, posture management (compliance, benchmarks, CIEM), vulnerability scanning, forensics, and threat detection and blocking.

* [IBM Cloud private connectivity offerings](/docs/private-connectivity?topic=private-connectivity-connect-privately-ibm-cloud) - This guide describes the various ways of connecting to IBM Cloud with a private connection using the following topologies:

    * Direct Link Dedicated - Single tenant connection to IBM Cloud Point of Presences (PoPs)
    * Direct Link Connect - Multi-tenant service provider connection to IBM Cloud PoPs
    * VPN (site-to-site) - VPN tunnel from on-premises firewall to IBM Cloud VPN
    * VPN (client-to-site) - VPN tunnel from laptop to IBM Cloud VPN
    * Satellite Connector - A layer-7, endpoint-oriented connection from IBM Cloud to access on-premises data source.

* [Extending your enterprise network to IBM Cloud](/docs/pattern-classic-edge-gateway?topic=pattern-classic-edge-gateway-extending-enterprise-network) - This guide describes on-premises data centers connectivity into IBM Cloud classic, with workloads in classic, Power Virtual Server, and Virtual Private Cloud (VPC). The diagram includes examples to show where workload compute instances, proxy servers, and jump servers are located.
* [Resiliency](/docs/resiliency) - This guide discusses the following resiliency topics:

    * [Understanding high availability](/docs/resiliency?topic=resiliency-understanding-ha) - A discussion on architecture patterns to design IBM Cloud services for high availability (HA), helping ensure resilience against different fault types that might impact the distributed IBM Cloud infrastructure. For HA in the cloud, it's important to understand the high-level concepts that you need to address if you're building or running a highly available cloud system. HA is achieved by using redundant system components and services, and by distributing these components across different environments. IBM Cloud delivers highly available cloud services by using redundant components and eliminating single points of failure. At the multizone regions (MZR) level, HA means having workloads running in multiple availability zones in the MZR, which provide the redundancy for local failures. 
    * [Understanding disaster recovery](/docs/resiliency?topic=resiliency-understanding-dr) - Disaster recovery (DR) the process of recovering one or more workloads to a working state in a second IBM Cloud region after an unplanned outage. HA is not the same as DR. Disasters are different. Disasters cause a workload to go down despite attempts to make it highly available. The worst disasters have widespread consequences, which means that affected workloads might require recovery in a different region altogether.
    * [Understanding cyber resiliency](/docs/resiliency?topic=resiliency-cyber-resiliency-overview) - Cyber resiliency is part of an organization's ability to prevent, withstand and recover from cybersecurity incidents, including ransomware attacks and other malicious actions. 

* [IBM® Power® Virtual Server resiliency on AIX](/docs/pattern-pvs-aix-resiliency?topic=pattern-pvs-aix-resiliency-power-virtual-server-on-AIX) - This is a baseline solution pattern containing the design and architecture decisions for a PowerVS resiliency solution for AIX workloads to meet common requirements.
* [IBM® Power® Virtual Server resiliency on IBM i](/docs/pattern-pvs-ibmi-resiliency?topic=pattern-pvs-ibmi-resiliency-power-virtual-server-on-ibmi) - This is a baseline solution pattern containing the design and architecture decisions for a PowerVS resiliency solution for IBM i workloads to meet common requirements.
* [Observability](/docs/observability-hub) - IBM Cloud offers Observability services that you can use to monitor, troubleshoot, and understand the activity in your account. You can also use them to keep records for auditing and compliance. This guide describes the following services:
  
    * [IBM Cloud Logs](/docs/cloud-logs) - IBM Cloud Logs is a scalable logging service that persists logs and provides users with capabilities for querying, tailing, and visualizing logs.
    * [IBM Cloud Monitoring](/docs/monitoring) - IBM Cloud Monitoring is a cloud-native, and container-intelligence management system that you can include as part of your IBM Cloud architecture. Use it to gain operational visibility into the performance and health of your applications, services, and platforms.
    * [IBM Cloud Activity Tracker Event Routing](/docs/atracker) - Use IBM Cloud Activity Tracker Event Routing to configure how to route auditing events, both global and location-based event data, in your IBM Cloud. Auditing events are critical data for security operations and a key element for meeting compliance requirements. Control of the storage location is critical to building enterprise-grade solutions on the IBM Cloud.
    * [IBM Cloud Logs Routing](/docs/logs-router) - You can use IBM Cloud Logs Routing to collect and route IBM Cloud logs from your account to a configured target.
    * [IBM Cloud Metrics Routing](/docs/metrics-router) - Use IBM Cloud Metrics Routing to configure how to route platform metrics in your IBM Cloud account.

* [IBM Cloud Internet Services](https://www.ibm.com/products/cloud-internet-services) - IBM Cloud Internet Services brings market-leading security and performance to your external web content and internet applications before they reach the cloud.
* [Veeam on IBM Cloud](https://www.ibm.com/products/veeam) - Veeam on IBM Cloud® can deliver reliable backup and predictable disaster recovery (DR) for virtual and physical workloads, wherever they reside—across your data center and the cloud.
* [IBM Cloud Backup](https://www.ibm.com/products/backup) - IBM Cloud® Backup is a full-featured, agent-based backup and recovery system managed through a web interface. Back up data between IBM Cloud servers in one or more IBM Cloud global data centers.
* [Zerto on IBM Cloud](https://www.ibm.com/products/zerto) - Zerto provides disaster recovery and cloud mobility for your VMware workloads within a single, simple, scalable solution.
* [IBM Cloud Object Storage](https://www.ibm.com/products/cloud-object-storage/systems) - IBM Cloud® Object Storage is a software-defined hyper-scale storage solution that runs on premises.
* [IBM Cloud Block Storage](https://www.ibm.com/products/block-storage) - High-performance data storage solutions with customizable IOPS and predictable billing.
* [IBM Cloud File Storage](https://www.ibm.com/products/file-storage) - Flash-backed, durable, fast and flexible NFS-based file storage—with customizable IOPS and predictable billing.
* [IBM Cloud for VMware Cloud Foundation as a Service](https://www.ibm.com/products/vmware/managed-services) - IBM Cloud for VCF as a Service is a managed service that delivers a VMware Cloud Director (VCD) based stack that enables businesses to build cloud computing environments that support their business needs. Whether opting for a single-tenant or multitenant model, IBM handles the configuration, capacity management, monitoring, patching, upgrades, and security of the underlying VMware infrastructure, through a highly available management plane, so you can quickly deploy your VMware-based cloud computing environments. You can purchase compute resources at the host level, leveraging several IBM Bare Metal Server and profiles, or on-demand compute resources at the vCPU, RAM, and Storage level. With our multitenant consumption model, you can start as small as 1 VM comprising 1vCPU, 1GB RAM, 20 GB vSAN, and 1 network efficiency edge.
* [IBM Cloud for VMware Solutions](https://www.ibm.com/products/vmware) - IBM Cloud for VMware Solutions enables you to seamlessly migrate and modernize VMware workloads to the cloud, allowing you to leverage your existing investments for a consistent VMware experience—retaining the same level of access, security and control.
* [IBM Cloud DNS Services](https://www.ibm.com/products/dns) - IBM Cloud® DNS Services offers public and private authoritative DNS services with fast response time, unparalleled redundancy and advanced security—managed through the IBM Cloud web interface or by API.
* [IBM Cloud Container Registry](https://www.ibm.com/products/container-registry) - Store and distribute container images in a fully managed private registry. Push private images to conveniently run them in the IBM Cloud® Kubernetes Service and other runtime environments. Images are checked for security issues so you can make informed decisions about your deployments.
* [Gateway appliances](https://www.ibm.com/products/network-appliances) - Gateway appliances are devices that give you enhanced control over network traffic, let you accelerate your network’s performance, and give your network a security boost. Manage your physical and virtual networks for routing multiple VLANs, for firewalls, VPN, traffic shaping and more.

## Hybrid Solution Guides
{: #non-rise-non-sap-surround-workloads-guides-hybrid}

These solution guides describe hybrid use cases linking on-premise applications with IBM Cloud:

* [Hybrid HPC with persistent cloud resource pools](/docs/hybrid-hpc-cloud-pool?topic=hybrid-hpc-cloud-pool-hybrid-hpc-pers-cloud-pool) - This reference architecture summarizes the best practices for deploying a Hybrid High Performance Computing (HPC) environment connecting an on-premises HPC environment to a persistent pool of HPC compute on IBM Cloud®. An organization with an existing HPC on-premises facility might decide to augment this with cloud-based resources.
* [Hybrid HPC with dynamic cloud resource pools](/docs/hybrid-hpc-cloud-pool?topic=hybrid-hpc-cloud-pool-hybrid-hpc-dyn-cloud-pool) - This reference architecture summarizes the best practices for deploying a Hybrid High Performance Computing (HPC) environment connecting an on-premises HPC environment to a dynamically provisioned pool of HPC compute resources on IBM Cloud®. An organization with an existing HPC on-premises facility might decide to augment this with these dynamic cloud-based resources.
* [Deploy Satellite on-premises or in hyperscaler](/docs/pattern-base-ibm-cloud-satellite?topic=pattern-base-ibm-cloud-satellite-base-ibm-cloud-satellite) - Due to privacy, regulatory, or compliance reasons, customers might not send or store data in the public cloud. In such scenarios, the best option is to create one or more Satellite locations on-premises and hosts the data locally to satisfy the data residency requirement. The Satellite on-premises or in hyperscaler pattern includes two common solution patterns:

* One or more IBM Cloud Satellite locations configured on-premises
* One Satellite location is configured on-premises, and another Satellite location is configured in the cloud

## Solution Guides for IBM Cloud Framework for Financial Services
{: #non-rise-non-sap-surround-workloads-guides-fs}

IBM Cloud for Financial Services® is designed to build trust and enable a transparent public cloud ecosystem with the features for security, compliance, and resiliency that financial institutions require. Financial institutions can confidently host their mission-critical applications in the cloud and transact quickly and efficiently. With a large partner ecosystem of independent software vendors (ISVs), Software as a Service (SaaS), and fintech partners, IBM Cloud for Financial Services offers a new generation of cloud for the enterprise. Financial institutions can now deploy on public cloud to enable innovation and deliver new outstanding customer experiences, while managing stringent industry regulations for sensitive data and complex workloads. See the solution guide [Getting started with IBM Cloud for Financial Services](/docs/framework-financial-services?topic=framework-financial-services-about) which describes the following reference architectures: 

* [Single-region IBM Cloud for Financial Services reference architecture for VPC with Virtual Servers for VPC](/docs/framework-financial-services?topic=framework-financial-services-vpc-architecture-detailed-vsi) - This architecture shows a deployment of the VPC that uses Virtual Servers for VPC as the primary compute.
* [Virtual Servers for VPC and Power Virtual Server reference architecture for IBM Cloud for Financial Services](/docs/framework-financial-services?topic=framework-financial-services-vpc-architecture-detailed-vsi-w-powervs) - This solution pattern contains the design and architecture decisions for cloud native and Power Virtual Server workloads in IBM Cloud for Financial Services.
* [Single-region IBM Cloud for Financial Services reference architecture for VPC with Red Hat OpenShift on IBM Cloud](/docs/framework-financial-services?topic=framework-financial-services-vpc-architecture-detailed-openshift) - Red Hat OpenShift on IBM Cloud extends the Kubernetes platform with built-in software to enhance app lifecycle development, operations, and security. The master nodes are entirely IBM's responsibility, while there is shared responsibility for the worker nodes.

In addition to the solution guide above, [Landing zone](/docs/secure-infrastructure-vpc) describes a number of VPC landing zone deployable architectures. These are Infrastructure as Code (IaC_) assets based on the IBM Cloud for Financial Services reference architecture. You can use the deployable architectures to create a secure and customizable Virtual Private Cloud (VPC) environments:

* [VPC landing zone](/docs/secure-infrastructure-vpc?topic=secure-infrastructure-vpc-vpc-ra) - This deployable architecture deploys a VPC landing zone with two Virtual Private Clouds (VPC); a Management VPC to manage the environment, and a Workload VPC that hosts the workload. Each VPC is a multi-zoned, multi-subnet implementation that keeps your workloads secure. A transit gateway connects the VPCs to each other and Virtual Private Endpoints are used connect to IBM Cloud services. IBM Cloud Flow Logs for VPC enables the collection and storage of information about the internet protocol (IP) traffic that is going to and from network interfaces within your VPC. In addition, Activity Tracker logs events from enabled services. IBM Cloud Flow Logs for VPC and Activity Tracker are included in this deployable architecture. You can add more security services, such as Hyper Protect Crypto Services.
* [VSI on VPC landing zone](/docs/secure-infrastructure-vpc?topic=secure-infrastructure-vpc-vsi-ra) - This deployable architecture creates a customizable and secure infrastructure, with virtual servers, to run your workloads with a Virtual Private Cloud (VPC) in multizone regions.
* [VSI on existing VPC landing zone - Extension](/docs/secure-infrastructure-vpc?topic=secure-infrastructure-vpc-vsi-ext-ra) - This deployable architecture extends an existing VPC deployable architecture by creating virtual server instances (VSI) in some or all of the subnets of any existing landing zone VPC deployable architecture.
* [VSI on VPC landing zone - QuickStart variation](/docs/secure-infrastructure-vpc?topic=secure-infrastructure-vpc-vsi-ra-qs) - The QuickStart variation of the VSI on VPC landing zone deployable architecture creates a fully customizable Virtual Private Cloud (VPC) environment in a single region. The solution provides virtual servers in a secure VPC for your workloads. The QuickStart variation is designed to deploy quickly for demonstration and development.
* [Red Hat OpenShift Container Platform on VPC landing zone](/docs/secure-infrastructure-vpc?topic=secure-infrastructure-vpc-ocp-ra) - Red Hat OpenShift Container Platform on VPC landing zone is a deployable architecture solution that is based on the IBM Cloud for Financial Services reference architecture. It creates secure and compliant Red Hat OpenShift Container Platform workload clusters on a Virtual Private Cloud (VPC) network.
* [Red Hat OpenShift Container Platform on VPC landing zone - QuickStart variation](/docs/secure-infrastructure-vpc?topic=secure-infrastructure-vpc-roks-ra-qs) - The QuickStart variation of the Red Hat OpenShift Container Platform on VPC landing zone deployable architecture creates a fully customizable Virtual Private Cloud (VPC) environment in a single region. The solution provides a single Red Hat OpenShift cluster in a secure VPC for your workloads. The QuickStart variation is designed to deploy quickly for demonstration and development.

## Solution Guides for AI
{: #non-rise-non-sap-surround-workloads-guides-ai}

The following solution guides are available for AI to enable you to leverage AI into your non-RISE, non-SAP workloads:

* [Gen AI Pattern for Watsonx on IBM Cloud](/docs/pattern-genai-rag?topic=pattern-genai-rag-genai-pattern) - This reference architecture summarizes the best practices for Watsonx Gen AI Pattern deployment on IBM Cloud. AI holds the promise to transform life and business but raises concerns around trust, security, and regulatory compliance. Understanding Gen AI and its infrastructure is vital for navigating its complex landscape. This reference architecture showcases how IBM Cloud and Watsonx provide a secure environment for deploying and governing Gen AI applications.
* [Watsonx.ai SaaS with Assistant and Governance](/docs/deployable-reference-architectures?topic=deployable-reference-architectures-watsonx-ai-reference-architecture) - The Watsonx.ai SaaS with Assistant and Governance deployable architecture is designed to automate the deployment and configuration of the IBM watsonx platform in an IBM Cloud account. The IBM watsonx platform is made up of several services working together to offer AI capabilities to end users who can explore them using IBM watsonx projects. The automation also configures a IBM watsonx starter project for an existing IBM Cloud user. A typical use case is to establish a ready to use IBM watsonx platform in an Enterprise account by granting administrator access to an AI Researcher. It enables an administrator to automatically install all of the services that the IBM watsonx platform is comprised of, as well as the setup of a starter watsonx project, allowing an AI Researcher to login to the platform and begin working immediately.
