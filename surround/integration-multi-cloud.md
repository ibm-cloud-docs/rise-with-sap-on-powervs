---

copyright:
  years: 2025
lastupdated: "2025-06-11"

keywords: SAP, RISE, PowerVS, RISE with SAP on PowerVS, SAP on IBM Cloud, Benefits of RISE with SAP on IBM Cloud, IBM Power Virtual Server, SAP modernization

subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Multi-cloud
{: #integration-multi-cloud}

Multi-cloud is a cloud computing strategy where enterprises can utilize the services of multiple public cloud services concurrently. Multi-cloud integrates cloud services into a single environment through a combination of APIs, networking, and management tools. This allows enterprises to manage their cloud services centrally and to move workloads seamlessly between different cloud providers as and when they need to. See [What is multicloud?](https://www.ibm.com/think/topics/multicloud){: external}

To do multi-cloud efficiently and at scale, requires distributed cloud exchange points that enable private, secure, low-latency communication among multiple clouds and SaaS services. {{site.data.keyword.cloud}} Direct Link Connect provides private access to the IBM Cloud infrastructure and any other clouds that are linked to your service provider. Many of these service providers offer cloud exchange services which is perfect for creating multi-cloud connectivity. Many of these service providers are already connected to IBM Cloud and other clouds via multi-tenant, high capacity links known as network-to-network interfaces (NNI). See [Direct Link Connect service providers and locations](/docs/dl?topic=dl-locations#connect-locations)

The high-level pattern shown below describes how IBM Cloud Direct Link Connect and your cloud exchange provider enable an enterprises multi-cloud pattern.

![Figure 1. Integrating multi-cloud with RISE with SAP on IBM Power Virtual Server](../images/multicloud.svg "Integrating multi-cloud with RISE with SAP on IBM Power Virtual Server"){: caption="Integrating multi-cloud with RISE with SAP on IBM Power Virtual Server" caption-side="bottom"}

The pattern above shows:

* Your enterprise networks that contain:
    * Your IT administrators.
    * Your internal users of the RISE with SAP, non-RISE SAP and non-RISE non-SAP systems hosted in the multi-cloud environment.
    * Your surround workloads that remain in your locations.
    * A network gateway that connects your enterprise networks to external networks.
* The Cloud Exchange Provider is a client selected partner who offers the required connections to your multi-cloud resources including IBM.
* SAP&reg; Cloud Peering is a service that allows SAP customers to establish a direct, secure connection to SAP cloud services, like SAP BTP, Concur, Ariba, SuccessFactors and more. These SAP services, connected through a network of interconnection partners, bypass the public internet and provides high-speed, reliable connectivity for the SAP applications. Many of these interconnection partners are also known as cloud exchange providers.
* Other Cloud Providers are your cloud accounts in other cloud providers such as AWS, Azure and GCP. These cloud providers host your additional surround workloads and SaaS products that you consume.
* Public Networks are Internet connected resources such as external users of the RISE with SAP, non-RISE and non-RISE non SAP systems and the SaaS are those products that are not accessible via the Cloud Exchange Provider and need to be accessed via the Internet.
* The IBM Cloud Account for client is your account that contains all your non-RISE SAP and non-RISE non-SAP surround workloads that you are hosting in IBM Cloud:
    * IBM Cloud has three IaaS environments; VPC, Power Virtual Server and Classic, any of these IaaS environments can be used to host your surround workloads.
    * Additionally you can consume IBM Cloud Services such as DNS and more.
    * The pattern uses a transit VPC which enables a hub-and-spoke design where the hub is the transit VPC and the SAP VPC and your other VPCs, Power Workspace and Classic infrastructure are the spokes. All spoke-to-spoke traffic passes through the hub. An alternative design is an edge VPC which only receives traffic leaving or entering your IBM Cloud Account. Diagrammatically the two patterns look the same, the difference is enabled in the routing you have configured in the VPC routing tables. The transit VPC hosts your selected Virtual Network Function (VNF) appliances. VNF appliances, such as routers and firewalls running on virtual server instances, can monitor, log, route and filter the traffic through the transit VPC. See the [IBM Cloud Catalog](/catalog?search=firewall%20label%3Asoftware#search_results) for third party vendors like Palo Alto, Fortinet, Checkpoint and Juniper who offer VNFs in IBM Cloud VPC.
    * Integration of the different IBM Cloud IaaS environments, such as VPC, Classic, and PowerVS, is achieved by using the IBM Cloud Transit Gateway, which can be considered as a 'as a service Border Gateway Protocol (BGP) router'. The IBM Cloud transit gateway can be local, limited to a specific region or global, spanning multiple regions.
    * The diagram shows Direct Link Dedicated connecting your enterprise networks to your transit VPC and Direct Link Connect connecting to your selected Cloud Exchange Provider. An alternative is to use the Direct Link Connect for your enterprise network traffic.
    * Inbound Internet access would leverage public application load-balancers and optionally IBM Cloud Internet Services to provide the required security features. Note that VNFs in high-availability cannot be used for inbound Internet traffic. See [VNF limitations](/docs/vpc?topic=vpc-vnf-limitations).
    * Outbound Internet access uses a public gateway on the subnets in the transit VPC or Floating IPs attached to the VNFs, as described by the VNF type and deployment pattern.
* The IBM Cloud account for RISE on Power Virtual Server is SAPs IBM Cloud account that hosts yor RISE with SAP resources. The diagram shows three options to connect the IBM Cloud Account for Client and the IBM Cloud Account for RISE with SAP on Power Virtual Server; Client provided transit gateway, SAP provided transit gateway and VPN, only one of these connections is required. You will need to discuss your requirements with your SAP representative on which of these three option SAP will authorize to satisfy your needs.

## Virtual Network Functions
{: #integration-multi-cloud-vnf}

Virtual Network Functions (VNFs), are virtual appliances packaged as VPC virtual server instances. The third-party appliances interacts with the IBM Software-Defined Networking (SDN) controller to offer easy configuration of IBM VPC network features such as route tables and floating IPs. Deployed with IBM Cloud Schematics via the IBM Content catalog, clients are able to instantiate VNFs easily. Support for a highly available, highly resilient VNF can be achieved by using the routing mode feature of the IBM Cloud Network Load Balancer (NLB) for VPC. See [About HA VNF deployments](/docs/vpc?topic=vpc-about-vnf-ha) and [Deploying a VNF](/docs/vpc?topic=vpc-deploy-vnf). The following IBM Cloud VNF catalog offerings are available:

* Fortinet FortiGate Next-Generation Firewall.
* Palo Alto VM-Series.
* Check Point Security Gateway - CloudGuard Network Security Firewall with Threat Prevention.
* Juniper vSRX.
* F5 Big-IP.

High availability VNF deployments have the following known limitations.

* The VNF appliances must share one subnet with the Network Load Balancer (NLB).
* Routing public internet "ingress" traffic to a VNF is not supported.
* Auto-scaling with the VNF is not supported.

The following documentation is available for the deployment and configuration of VNFs:

* [Fortinet FortiGate Next-Generation Firewall - A/P HA](https://cloud.ibm.com/catalog/content/ibm-fortigate-AP-HA-terraform-deploy-5dd3e4ba-c94b-43ab-b416-c1c313479cec-global) - The IBM Catalog link to a Terraform script used in IBM Cloud Schematics to deploy an Active-Passive high availability Fortinet cluster in a single zone. This template makes use of the FortiGate IBM SDN connector to failover in the event of a VM shutdown.
    * [Deploying FortiGate-VM on IBM Cloud](https://docs.fortinet.com/document/fortigate-public-cloud/7.6.0/ibm-cloud-administration-guide/992669/deploying-fortigate-vm-on-ibm-cloud){: external} - A step-by-step guide of deploying the appliance in IBM Cloud VPC.
    * [Deploying FortiGate-VM A-P HA on IBM VPC Cloud (BYOL)](https://docs.fortinet.com/document/fortigate-public-cloud/7.6.0/ibm-cloud-administration-guide/944419/deploying-fortigate-vm-a-p-ha-on-ibm-vpc-cloud-byol){: external} - A configuration guide to enable FortiGate-VM unicast high availability failover that automatically triggers routing changes and floating IP address reassignment on the IBM Cloud via API.
    * [Deploying FortiGate-VM A-A HA load balancer sandwich](https://docs.fortinet.com/document/fortigate-public-cloud/7.6.0/ibm-cloud-administration-guide/524343/deploying-fortigate-vm-a-a-ha-load-balancer-sandwich){: external} - A configuration guide that describes the steps that you take to create  FortiGate-VM in active-active high availability failover leveraging network load balancers.
* [VM-Series Firewall - BYOL](https://cloud.ibm.com/catalog/content/ibmcloud-vmseries-1.9-6470816d-562d-4627-86a5-fe3ad4e94b30-global) - The IBM Catalog link to a Terraform script used in IBM Cloud Schematics to deploy a single VM-Series firewall appliance.
    * [Deploy the VM-Series Firewall Using IBM Cloud Schematics](https://docs.paloaltonetworks.com/vm-series/10-1/vm-series-deployment/set-up-the-vm-series-firewall-on-ibm-cloud/deploy-vm-series-firewall-on-ibm-cloud){: external} - Step-by-step guides for deploying a Palo Alto VM-Series firewall in IBM Cloud VPC.
    * [High Resiliency for VM-Series Firewall on IBM Cloud](https://docs.paloaltonetworks.com/vm-series/10-1/vm-series-deployment/set-up-the-vm-series-firewall-on-ibm-cloud/high-resiliency-for-vm-series-firewall-on-ibm-cloud){: external} - A configuration guide that describes the steps to deploy two VM-Series firewalls on IBM Cloud to ensure redundancy in the network by using active-active high availability configuration. The IBM Cloud Network Load Balancer (NLB) Route Mode feature is used to support the VM-Series HA. The ingress routing capability allows you to associate route tables with the VM-Series appliances and add route rules to redirect the application traffic through the VM-Series firewall. This redirection ensures that all internet traffic passes through the firewall without having to reconfigure the application endpoints.
* [CloudGuard Network Security Firewall with Threat Prevention](https://cloud.ibm.com/catalog/content/check-point-cloudguard-network-security-firewall-with-threat-prevention-1f1f50fe-e41d-4715-9ba6-02d37d76596c-global?catalog_query=aHR0cHM6Ly9jbG91ZC5pYm0uY29tL2NhdGFsb2c%2Fc2VhcmNoPWZpcmV3YWxsJTI1MjBsYWJlbCUyNTNBcGRyX2ZvcnRpbmV0X2luY18lMjUyMGxhYmVsJTI1M0FwZHJfY2hlY2tfcG9pbnRfc29mdHdhcmVfdGVjaG5vbG9naWVzJTI1MjBsYWJlbCUyNTNBcGRyX2p1bmlwZXJfbmV0d29ya3MlMjUyMGxhYmVsJTI1M0FwZHJfcGFsb19hbHRvX25ldHdvcmtzI3NlYXJjaF9yZXN1bHRz) - The IBM Catalog link to a Terraform script used in IBM Cloud Schematics to deploy a Check Point security gateway into a zone in an existing VPC environment.
* [Juniper Next-Gen SASE Firewall - BYOL](https://cloud.ibm.com/catalog/content/jnpr-nextgen-fw-vsrx-74b4b3ba-2a05-460d-afba-98e4d012f53a-global?catalog_query=aHR0cHM6Ly9jbG91ZC5pYm0uY29tL2NhdGFsb2c%2Fc2VhcmNoPWZpcmV3YWxsJTI1MjBsYWJlbCUyNTNBcGRyX2ZvcnRpbmV0X2luY18lMjUyMGxhYmVsJTI1M0FwZHJfY2hlY2tfcG9pbnRfc29mdHdhcmVfdGVjaG5vbG9naWVzJTI1MjBsYWJlbCUyNTNBcGRyX2p1bmlwZXJfbmV0d29ya3MlMjUyMGxhYmVsJTI1M0FwZHJfcGFsb19hbHRvX25ldHdvcmtzI3NlYXJjaF9yZXN1bHRz)- The IBM Catalog link to a Terraform script used in IBM Cloud Schematics to deploy a Juniper Next-Gen SASE Firewall into a zone in an existing VPC environment.
* [F5 BIG-IP Virtual Edition for VPC](https://cloud.ibm.com/catalog/content/ibmcloud_schematics_bigip_multinic_declared-1.0-d33f1544-e938-478a-b0dd-d883370f08d0-global?catalog_query=aHR0cHM6Ly9jbG91ZC5pYm0uY29tL2NhdGFsb2c%2Fc2VhcmNoPUY1JTI1MjBCaWctSVAjc2VhcmNoX3Jlc3VsdHM%3D) - The IBM Catalog link to a Terraform script used in IBM Cloud Schematics to deploy a single F5 BIG-IP Virtual Edition for VPC appliance in a single zone.
    * [Deploy F5 BIG-IP Virtual Edition in IBM Cloud VPC Gen 2](https://clouddocs.f5.com/cloud/public/v1/ibm/ibm_deploy.html){: external} - A step-by-step guide of deploying the appliance in IBM Cloud VPC.

## Connecting IBM Power Virtual Server to Microsoft Azure with Megaport
{: #integration-multi-cloud-pvs-azure-megaport}

The use case [Connecting IBM Power Virtual Server to Microsoft Azure with Megaport](/docs/power-iaas?topic=power-iaas-connect-azure-with-megaport) provides architectural solution guidelines for running IBM Power Virtual Servers and IBM Cloud with private connectivity between IBM Cloud and[Microsoft Azure](https://azure.microsoft.com/){: external} by using [Megaport](https://www.megaport.com/){: external}.

This solution provides private network connectivity between IBM Power Virtual Server and Microsoft Azure for high-performance peer-to-peer connection of cross-cloud workloads. The architecture uses private connection services through IBM Cloud Direct Link, which is coupled with Microsoft Azure ExpressRoute, and joined by the Megaport Cloud Router, as shown in the diagram below:

![Figure 2. Connecting IBM Power Virtual Server to Microsoft Azure with Megaport](/docs-content/v4/content/b26f89a5806299f299231da0f7dd0780cb84fc59/power-iaas/images/pvs_azure_architechture.svg "Connecting IBM Power Virtual Server to Microsoft Azure with Megaport"){: caption="Connecting IBM Power Virtual Server to Microsoft Azure with Megaport" caption-side="bottom"}
