---

copyright:
  years: 2025
lastupdated: 2025-04-10

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Migration tooling and services
{: #migration-tooling}

This section high-lights some tooling and services to enable the migration of your surround workloads to IBM Cloud.

## IBM Transformation Suite for SAP Applications
{: #migration-tooling-transformation-suite}

To further accelerate Cloud ERP migration, IBM Transformation Suite for SAP Applications brings software and services from IBM and partners such as SNP that automates essential migration tasks, including technical assessments, data and code migration, code analysis, and automated testing.

With the IBM Transformation Suite for SAP Applications, organizations can:

* Accelerate the transition to SAP S/4HANA.
* Unlock the potential of RISE with SAP.
* Simplify their IT landscape while driving innovation.

For more information on IBM Transformation Suite for SAP Applications, see [Accelerate your SAP S/4HANA journey with IBM Transformation Suite for SAP Applications](https://www.ibm.com/new/announcements/accelerate-your-sap-s-4hana-journey-with-ibm-transformation-suite-for-sap-applications).

## RackWare RMM Server
{: #migration-tooling-rmm}

RackWare's RMM migrations are an automated, easy, and convenient way to migrate existing workloads from your current location to IBM Cloud. RMM creates an exact duplicate of a running image without the burden of rebuilding or recreating template images and applications. It decouples the application stack from the underlying platform, allowing it to be ported to the IBM Cloud infrastructure with ease. RMM simplifies migration of large, complex environments through a simple interface and reduces the time required from weeks to days, reducing capital and operating expenses. RackWare RMM includes discovery, analysis, and automation features, allowing all processes to be fast, easy, and error-free. The supported use cases include:

* VMware virtual machine (On-premises) to IBM Cloud VPC virtual servers.
* Hyper-V virtual machine (On-premises) to IBM Cloud VPC virtual servers.
* On-premises physical machines to IBM Cloud VPC virtual servers.
* GCP, AWS, Azure, virtual machines and OCI Baremetal to IBM Cloud VPC virtual servers.
* Migration of popular databases (e.g., MSSQL, MySQL, PostgreSQL etc.).

The key benefits include the following:

* Live and Non-Disruptive Migrations.
* Highly secure and efficient data transfer.
* Auto discovery of VMware vSphere and Hyper-V workloads.
* Auto provision of target Virtual Server Instance.
* Include / Exclude Lists: Capture and sync only specific files and directories rather than entire systems.
* Delta Sync: Sync only the changed parts of files during the final data sync, drastically lowering cut-over times.
* Network optimization: bandwidth usage limitations, compression and check point restart for all sync operations.

[RackWare - CloudMotion](https://cloud.ibm.com/catalog/content/IBM-MarketPlace-P2P-1.3-22935832-bd76-49ab-b53e-12fc5d04c266-global?kind=terraform&format=vsi-image&version=3629c1a1-262a-4bcd-90cb-be4d1f62944b-global) can be installed via the IBM Catalog. The RMM software comes preinstalled as part of the virtual server provisioning process. After the virtual server is deployed, you can access RMM through the CLI or GUI. A license is required via contact with RackWare. For more information, visit [RackWare CloudMotion](https://www.rackwareinc.com/cloud-migration){: external}

## Wancloud's Migrations as a Service
{: #migration-tooling-maas}

[Custom Migrations DR and Management as a Service](https://cloud.ibm.com/catalog/services/custom-migrations-dr-and-management-as-a-service#about) is a fully-managed and accelerated way of taking your current environment, be it on-premises or cloud, and migrating to your desired IBM cloud account and region. With this offering you can migrate the following to IBM Cloud:

* On-premise VMware VMs and data.
* On-Premise Linux, Windows,Kubernetes and Red Hat Openshift.
* On-premise IBM Power System LPARs (AIX, IBMi, Linux on Power).
* AWS / Google Cloud / Microsoft Azure VMs.

## FNTS Cloud Migration Services
{: #migration-tooling-fnts}

[FNTS Cloud Migration Services](https://cloud.ibm.com/catalog/services/fnts-cloud-migration-services#about) is a service that migrate IBMi, AIX, Linux and Windows workloads to IBM Cloud. The service has the following features and capabilities:

* Create a cloud migration plan - Build a custom migration plan based on current technology stack, RTO/RPO and business requirements
* Prepare Target Cloud Environment - Provision and configure network, virtual servers and related infrastructure required for the target environment.
* Migrate Data to Cloud - Migrate data using supported backup and replication tools.

See [Give new life to legacy AIX and IBM i Operating Systems](https://www.fnts.com/cloud/ibm-power-cloud){: external}.

## Komprise Elastic Data Migration
{: #migration-tooling-komprise}

[Komprise Elastic Data Migration](https://cloud.ibm.com/catalog/services/komprise-elastic-data-migration#about) enables fast, predictable and cost-efficient data migration for file and object data from on-premise NAS to IBM Cloud. Komprise runs data migrations faster with an elastic architecture and reliably migrates petabytes of data. Features and capabilities include the following:

* Analyze Before You Migrate - Use Komprise Analysis to understand what data to migrate and plan your migration. Know first with dashboards, reports and move smarter.
* Migrate Faster - Migrate 25+ times faster (NFS, SMB, S3/object) vs point tools across heterogeneous clouds and storage. Elastic parallelism. WAN optimized.
* Migrate NAS Reliably - Komprise migrates with all file permissions, access controls, data integrity intact. MD5 checksums performed on every file chain of command.
* Migrate Across Clouds - Migrate any file or object data across data center and public clouds. Migrate hot and cold data to the appropriate storage classes and save.
* Simplify Management - Dashboards and reports to monitor and manage hundreds of simultaneous migrations and get status updates.

See [Komprise](https://www.komprise.com/support/){: external}.

## Power i Migrate 23 Services
{: #migration-tooling-poweri-migrate23}

[Power i Migrate 23 Services](https://cloud.ibm.com/catalog/services/power-i-migrate-23-services#about) offers a professional services team to take care of the entire migration process of transitioning to the IBM PowerVS cloud from start to finish, including, initial planning, data capture and final system setup. See [BUS4i Services Information](https://wiki.bus4i.com/bin/view/Main/BUS4i/BUS4i%20Service%20Information){: external}.

## Lyve Data Transfer Services
{: #migration-tooling-lyve-dts}

[Lyve Data Transfer Services](https://cloud.ibm.com/catalog/services/lyve-data-transfer-services#about) is fully a fully managed service that delivers white glove service to ensure a successful transfer of data from the edge or on-premise to IBM COS. The scalable Data Transfer Service utilizes Seagate's mass capacity storage arrays, alongside Seagate's Cloud-Import Software and expert IBM COS Cloud-Import Services, making Lyve Mobile a complete, simple, low-cost, secure solution for fast, data transfer and data mobility projects, at scale, without the worries of network latency. See [Lyve Management Porta](https://www.seagate.com/gb/en/manuals/lyve-management-portal/){: external}

## Migrate Workloads to IBM Power Virtual Server
{: #migration-tooling-tel-pvs}

The [Migrate Workloads to IBM Power Virtual Server](https://cloud.ibm.com/catalog/services/partner-with-technology-expert-labs?id=82883374-ade2-48de-ae40-ac6023b9ca92) service is designed to assist you with migrating AIX, IBMi or SAP HANA workloads to IBM Power Virtual Server (PowerVS). The benefits of the service includes the following:

* Utilizing our deep technical skills and broad PowerVS experience can accelerate your migration time by up to 2x.
* The service will ensure that you use best practices established over multiple migrations for your applications, data and networking.

The service includes the following activities:

* Plan the migration including workload selection and network design requirements.
* Build new PowerVS environment aligned to solution design.
* Configure basic VPN networking connectivity from client on-premise location to PowerVS.
* Perform migration of 2 client LPARs to PowerVS.
* Advise on best practices for running workloads in PowerVS, including additional automation, modernization, performance or security components.
* Additional follow-on billable services:
    * Backups configuration, including Virtual Tape Library.
    * HA/DR configuration.
    * Migrating additional workloads.
    * Additional or more complex network configuration.

See [IBM Technology Expert Labs – Cloud](https://www.ibm.com/cloud/expert-labs){: external}. Other IBM Technology Expert Labs available in the catalog include the following:

* [Partner with IBM Technology Expert Labs](https://cloud.ibm.com/catalog/services/partner-with-technology-expert-labs)
* [Build SAP HANA Starter Edition on IBM Power](https://cloud.ibm.com/catalog/services/partner-with-technology-expert-labs?id=3e39e603-fb69-45ff-9a3d-9494c6786f41)
* [Build IBM Storage Protect Solution for Power Virtual Server](https://cloud.ibm.com/catalog/services/partner-with-technology-expert-labs?id=69e6b868-27ef-4137-900b-93d8a3ceb5e6&catalog_query=aHR0cHM6Ly9jbG91ZC5pYm0uY29tL2NhdGFsb2c%2Fc2VhcmNoPW1pZ3JhdGlvbiNzZWFyY2hfcmVzdWx0cw%3D%3D)

## VMware Cloud Migration Services
{: #migration-tooling-primaryio}

[VMware Cloud Migration Services](https://cloud.ibm.com/catalog/services/vmware-cloud-migration-services) is a selection of services for VMware customers seeking to modernize and embrace various IBM cloud options as either a production or disaster recovery target site. Offered by PrimaryIO, this collection is comprised of advisory services and optionally professional services. See [PrimaryIO](https://hdm.primaryio.com/lp/vmwaas){: external}.

## ConvertIO VMware Workload Migration and Conversion
{: #migration-tooling-convertio}

[ConvertIO VMware Workload Migration and Conversion](https://cloud.ibm.com/catalog/services/convertio-vmware-workload-migration-and-conversion#about) uses the ConvertIO product, wrapped in services, to enable VMware customers to modernize and embrace IBM cloud-native Virtual Server Instances (VSI) workloads running in IBM Cloud VPC, reducing their VMware VCF estate and become more cloud-native. Each project is fully detailed with project plan, associated cost and transparency to the project status with focus on rapid achievement of critical path objectives. See [ConvertIO Solution Brief](https://www.primaryio.com/wp-content/uploads/2025/01/ConvertIO-Solution-Brief.pdf){: external}.

## Veeam
{: #migration-tooling-veeam}

[Veeam](https://cloud.ibm.com/infrastructure/vmware-solutions/console/newserviceentry/VeeamVM/vcs_nsx_t) Backup and Replication seamlessly integrates directly with your VMware hypervisors to help your enterprise achieve high availability. The recovery feature enables VMs to be migrated from on-premise to IBM Cloud for VMware Solutions self-managed offerings. See [VM Migration and VMware Migration Tools](https://www.veeam.com/blog/vm-migration-vmware-migration-tools.html){: external}

## Zerto
{: #migration-tooling-zerto}

[Zerto](https://www.veeam.com/blog/vm-migration-vmware-migration-tools.html) provides on-premise and IBM Cloud customers with a secure, flexible and scalable Disaster Recovery (DR) solution. The VMware Virtual Machine (VM) replication feature that underpins the DR capability enables the migration use-case, enabling clients to migrate their on=premise workloads to IBM Cloud for VMware Solutions self-managed offerings. See [Migrations with Zerto](https://www.zerto.com/solutions/use-cases/migrations/){: external}.

## HCX
{: #migration-tooling-hcx}

[HCX](https://cloud.ibm.com/infrastructure/vmware-solutions/console/newserviceentry/HCX/vcs_nsx_t) seamlessly extends the networks of on-premises data centers into IBM Cloud, which enables you to migrate VMware Virtual Machines (VMs) to and from the IBM Cloud for VMWare Solutions self-managed offerings without any conversion or change. HCX creates an abstraction layer that enables application mobility and infrastructure hybridity through securely stretched networks. See [VMware HCX](https://www.vmware.com/products/cloud-infrastructure/hcx){: external}.

## VMware Cloud Director Availability (VCDA)
{: #migration-tooling-vcda}

[VMware Cloud Director Availability (VCDA)](https://cloud.ibm.com/vmware/newserviceentry/VCDA/vcda#about) service is included by default in all multi-tenant IBM Cloud for VMware Cloud Foundation as a Service (VCFaaS) virtual data centers (VDCs) and optionally included in your single-tenant VCFaaS at no charge. VCFaaS with VCDA supports several migration scenarios:

* Migrate vCenter virtual machine workloads from on-premises or IBM Cloud environments to VCFaaS over the public or private network.
* Migrate workloads from VCFaaS single-tenant and multi-tenant instances to another VCFaaS instance over the private network.
