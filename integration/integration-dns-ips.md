---

copyright:
  years: 2025
lastupdated: "2026-04-17"

keywords: SAP, RISE, PowerVS, RISE with SAP on PowerVS, SAP on IBM Cloud, Benefits of RISE with SAP on IBM Cloud, IBM Power Virtual Server, SAP modernization


subcollection: rise-with-sap-on-powervs

---

{{site.data.keyword.attribute-definition-list}}

# DNS and IP considerations
{: #integration-dns-ips}

Integration of your networks with cloud based infrastructure requires careful planning for IP addressing. In addition, providing a seamless domain name resolution is a critical part of a successful onboarding project.
{: shortdesc}

## IP address schema
{: #integration-dns-ips-ip-schema}

When you request the RISE with SAP on IBM {{site.data.keyword.powerSysFull}} service, you supply to SAP an IP address schema that will be used within the SAP managed {{site.data.keyword.cloud}} Enterprise Account. This IP address schema must not overlap with any IP addresses used elsewhere in your organization’s network or any peered resource from your {{site.data.keyword.cloud}} accounts, client managed or client’s service provider managed, or other interconnected cloud resource.


## DNS Considerations
{: #integration-dns-ips-dns}

When you request the RISE with SAP on {{site.data.keyword.powerSysFull}}, you supply your domain name for example `<customer>.com`. SAP&reg; create a sub-domain for example `sap.<customer>.com` on the DNS servers in their {{site.data.keyword.cloud}} Enterprise Account that hosts the fully qualified domain names and IP addresses for the services they host for you. SAP allow a zone transfer from their SAP DNS servers to your DNS servers, so that name resolution on your network can occur.

In some circumstances SAP will allow DNS forwarding of requests from your DNS servers to SAP's DNS servers. You must request this non-preferred method from your SAP representative.

The selected inter-connectivity option will influence how the connectivity between your DNS servers and RISE with SAP DNS servers must be setup.
