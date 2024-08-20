---

copyright:
  years: 2017, 2024
lastupdated: "2024-08-20"

keywords: bypass, bypassing, firewall, rules, enable, enabling

subcollection: hardware-firewall-shared

---

{{site.data.keyword.attribute-definition-list}}

# Gateways and Firewalls
{: #ga-raci

New topic title needed.
Intro paragraph needed. 

## Monitoring
{: #ga-raci-monitoring}

Explain table contents below

| Activity                                                                 | Client | IBM | Relevant Information |
|--------------------------------------------------------------------------|--------|-----|----------------------|
| Supervision and technical monitoring of devices (gateways, firewalls, bare metal / virtual servers, etc.) | R, A    | C, I | The client (or their managed services provider) is responsible for monitoring the performance, connectivity, and hardware of their devices. IBM Cloud does not monitor individual customer devices, their configurations, or network status or assignments. Should an issue arise, a support ticket can be submitted to schedule hardware replacement. |
| Supervision and technical monitoring of hardware infrastructure outside of the direct customer environment | C, I    | R, A |                      |
| Customer hardware & component monitoring                                 | R, A    | C, I |                      |

## MRO (Maintenance, Repair, and Operations)
{: #ga-raci-mro}

Explain table contents below

| Activity                                                                 | Client | IBM | Relevant Information |
|--------------------------------------------------------------------------|--------|-----|----------------------|
| General maintenance of devices in customer infrastructure                | R, A    | C, I | The client (or their managed services provider) is responsible for ongoing maintenance and operation of their devices. The client team will provide all relevant details regarding initial troubleshooting that's been completed and may request additional assistance via a support ticket, live chat, or phone call to IBM Cloud technical support. |
| Disaster recovery & high availability testing                            | R, A    | C, I |                      |
| Regularly scheduled device backups                                      | R, A    | C, I |                      |
| Initial operating system set up and configuration (pre-provision & handoff to client) | C, I    | R, A |                      |
| Hardware maintenance & replacement                                       | C, I, O | R, A |                      |
| Break/Fix Support                                                        | C, I    | R, A |                      |

## Administration (Ongoing Device Management)
{: #ga-raci-admin}

Explain table contents below

| Activity                                                                 | Client | IBM | Relevant Information |
|--------------------------------------------------------------------------|--------|-----|----------------------|
| Configuration and management of services (post-provision)                 | R, A    | C, I | The client (or their managed services provider) is responsible for the ongoing administration of their environment, devices, user accounts, etc. IBM Cloud technical support is available to provide guidance, answer questions, and escalate to internal teams or vendors for complex issues that require additional assistance. IBM Cloud technical support does not perform migrations. Our technical staff is available 24x7 for assistance should an issue occur during a migration event/window, however we will not be able to join the entirety of a scheduled migration event call. |
| Configuration and management of firewalls, gateway devices, & underlying hosts (where applicable, post-provision) | R, A    | C, I |                      |
| Planning and preparation for change requests on firewall & gateway devices (configuration changes, operating system or firmware updates, etc.) | R, A    | C, I |                      |
| Perform change requests on firewall & gateway devices (configuration changes, operating system or firmware updates, etc.) | R, A    | C, I |                      |
| Manage IP address assignments (post provision)                           | R, A, O | C, I |                      |
| Manage VLAN Associations (post provision)                                | R, A, O | C, I |                      |
| Configuration and management of IPSEC/GRE Tunnel to remote client environment | R, A    | C, I |                      |
| Migrations - Planning, Preparation, Implementation - Moving from one solution to another | R, A    | C, I |                      |

## LCM (Life Cycle Management)
{: #ga-raci-lcm}

Explain table contents below

| Activity                                                                 | Client | IBM | Relevant Information |
|--------------------------------------------------------------------------|--------|-----|----------------------|
| Upgrade an operating system that has reached End of Life/Support         | R, A, O | C, I | When a device or operating system reaches its End of Support or End of Life, IBM Cloud will not be able to provide support. Once the device has been brought up to a supported firmware or operating system, support can resume on the device. |
| Upgrade the hardware of a device                                         | R, A, O | C, I |                      |
| Support of devices after End of Support or End of Life                   | R, A    |     |                      |

## Additional Notes & Scope of Support
{: #raci-notes}

With regard to Consulting and Informing (C, I), IBM Cloud technical support is generally done via support ticket, live chat, or phone call. It is expected that the client or their managed services provider provide technical resources with a firm understanding of the environment to aid with troubleshooting issues. IBM Cloud technical support is available to augment the client's own technical team and provide guidance & support as needed, bringing in any relevant internal team or vendor for additional assistance if warranted. Any break/fix support provided by IBM Cloud technical support beyond restoring a device to its original working configuration is best-effort.
