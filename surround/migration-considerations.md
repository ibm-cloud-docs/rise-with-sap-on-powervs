---

copyright:
  years: 2025
lastupdated: 2025-03-17

keywords: SAP, {{site.data.keyword.cloud_notm}} SAP-Certified Infrastructure, {{site.data.keyword.ibm_cloud_sap}}, SAP Workloads

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Migration considerations
{: #migration-considerations}

When approaching the migration of your surrounding workloads, it is helpful to understand the migration timeline and classify each of the surround workloads as a tactical or strategic migration:

* Tactical - In the tactical approach, the surround workload needs to be migrated in the same time frame as your SAP systems in RISE with SAP on IBM Power Virtual Server.
* Strategic - In the strategic approach, the surround workload does not need to be migrated in the same time frame as your SAP systems in RISE with SAP on IBM Power Virtual Server. The timeline is then governed by you business needs and requirements rather than the migration of your SAP systems.

In addition, classify the workloads into:

* Non-RISE SAP - These workloads are SAP systems that cannot be migrated to RISE with SAP Power Virtual Server because the are not SAP ERP, SAP ECC, or SAP S/4HANA. Many of these workloads can move to IBM Cloud and be hosted in your IBM Cloud Account. See [IBM Cloud for SAP and IBM Power Virtual Servers for SAP](https://cloud.ibm.com/docs/sap).
* Non-RISE non-SAP - These workloads are not SAP systems and cannot move to RISE with SAP. Many of these workloads can move to IBM Cloud and be hosted in your IBM Cloud Account. See [IBM Cloud Solution Library](https://cloud.ibm.com/docs?tab=solutions).

## Migration strategy
{: #migration-migration-strategy}

If the surround workload has been classified as tactical then it important to consider the strategy of achieving the migration in the timeline. These cloud migration strategies include re-hosting, re-platforming, refactoring, repurchasing and retiring.

* Re-hosting - Re-hosting, also known as Lift and Shift, involves moving applications from your on-premises environment to the cloud without making significant changes. An example is moving from on-premise VMware to [IBM Cloud for VMWare Solutions](https://www.ibm.com/products/vmware)
* Re-platforming - With a re-platforming migration, some adjustments or optimizations are made to the applications before moving them to the cloud. An example of this strategy is moving a VMware VM to run on [IBM Cloud Virtual Server for VPC](https://www.ibm.com/products/virtual-servers).
* Refactoring - Refactoring involves modifying or redesigning applications to fully leverage cloud-native features. This migration type often involves breaking down monolithic applications into microservices, making them more scalable in the cloud environment. Migrating applications to run on [IBM Cloud Kubernetes Services](https://www.ibm.com/products/kubernetes-service) or [Red Hat OpenShift on IBM Cloud](https://www.ibm.com/products/openshift)
* Repurchasing - Repurchasing involves retiring an existing application and replacing it with a SaaS alternative. Instead of migrating the application to the cloud, businesses opt for a cloud-based SaaS solution that meets their needs. An example may be [IBM MQ SaaS](https://www.ibm.com/products/mq/saas)
* Retiring - Retiring involves decommissioning outdated or unused applications as part of the migration process. This helps in reducing maintenance costs and eliminating redundant resources.

For surround workloads that have been classified as strategic, the same strategies apply, however, the decision on the selection of the strategy can be taken at a later date inline with your timeline.

There is a lot of documented migration strategies available, for example see [What is cloud migration?](https://www.ibm.com/think/topics/cloud-migration) and [Lift and shift VMware on-premises to IBM Cloud](https://cloud.ibm.com/docs/pattern-migration-options-vmware-workloads?topic=pattern-migration-options-vmware-workloads-whitepaper). The short blog, [Cloud migration best practices: Optimizing your cloud migration strategy](https://www.ibm.com/think/insights/cloud-migration-strategy), describes how IBM Turbonomic can simulate the migration of on-premises virtual machines (VMs) to the cloud, or the migration of VMs from one cloud provider to another, focusing on performance and cost optimization. The blog provides some insight on the following topics:

* Why migrate to the cloud?
* Types of cloud migration.
* Cloud migration strategies.
* Common cloud migration challenges.

## Migration program
{: #migration-migration-program}

The move of the surround workload is supported by your migration program. An example of a migration program may include 5 phases: Discovery, Assessment, Minimum Viable Product (MVP), Migration, and Operate.

* Phase 1: Discovery - Data is collected across technical, sales, and business teams to understand the motivation and internal factors driving the move to cloud. Identify priorities such as scalability, solving functional issues, lack of in-house skills, reducing infrastructure, and IT expenses. Identify and document current infrastructure, applications, relationships, and dependencies including drift from the expected business required state.
* Phase 2: Assessment - Data that is collected in the discovery phase is used to assess the migration to cloud viability to and choosing the right target platform solution. Right-size the target environment and take advantage of cloud elasticity. The outcome of the assessment phase is a high-level architecture of the cloud environments with an associated bill of materials. See [IBM Turbonomic](https://www.ibm.com/products/turbonomic)
* Phase 3: Minimum Viable Product (MVP) - Provides the confidence in the viability of the proposed solution. It is important to clearly define and articulate upfront the success criteria of the MVP as well as to identify the approving stakeholders. The successful MVP builds trust and confidence in the solution and provides the go ahead for the migration of the surround workload. The MVP familiarizes your operations team with the cloud platform and guides towards a smooth adoption.
* Phase 4: Migration - The surround workloads are migrated to cloud. The duration of the migration phase depends on the complexity and criticality of the surround workload. [IBM Technology Expert Labs](https://www.ibm.com/products/expertlabs) includes accelerator services to migrate workloads to IBM Cloud.
* Phase 5: Operate: Refers to tooling and processes to maintain the surround workload operational after the migration to IBM Cloud and leveraging cloud services. IBM Cloud services arranged by key operational processes includes:
    * Backup - [IBM Cloud Backup](https://www.ibm.com/products/backup), [Veeam on IBM Cloud](https://www.ibm.com/products/veeam), [Backup-as-a-Service for AIX/Linux On Power Virtual Server With Cobalt Iron Compass](https://cloud.ibm.com/docs/pvs-baas-with-compass?topic=pvs-baas-with-compass-white-paper) 
    * Observability - [IBM Cloud Logs](https://www.ibm.com/products/cloud-logs), [IBM Cloud Monitoring](https://www.ibm.com/products/cloud-monitoring) 
    * Compliance. - [IBM Security and Compliance Center](https://www.ibm.com/products/security-and-compliance-center), [Getting started with IBM Cloud Security and Compliance Center Workload Protection](https://cloud.ibm.com/docs/workload-protection?topic=workload-protection-getting-started), [Caveonix RiskForesight on IBM Cloud overview](https://cloud.ibm.com/docs/workload-protection?topic=workload-protection-getting-started)


Review [About migration](/docs/infrastructure-hub?topic=infrastructure-hub-about-migration-infra)

## Post migration
{: #migration-post-migration}

The diagram below illustrates the post-migration state of your SAP systems and surround workloads after adopting the migration strategy and migration program described above.

![Figure 1. Post Migration Surround Workloads](../images/surround-post.svg "Post Migration Surround Workloads"){: caption="Post Migration Surround workloads" caption-side="bottom"}

* Your SAP systems have migrated to RISE for SAP on Power Virtual Server.
* Your non-RISE SAP surround workloads have migrated to IBM Cloud and hosted in your own IBM Cloud Account.
* Your non-RISE non-SAP surround workloads have also migrated to either IBM Cloud or to other clouds.
* Your designated strategic loosely coupled surround workloads remain in your data centers awaiting migration according to your timeline.
