---

copyright:
  years: 2017, 2026
lastupdated: "2026-01-28"

keywords: about, gateway, appliance, firewall, vpn, nat, routing, vlan

subcollection: gateway-appliance

---

{{site.data.keyword.attribute-definition-list}}

# About {{site.data.keyword.cloud_notm}} Gateway Appliance
{: #about}

{{site.data.keyword.cloud}} Gateway Appliances allow you to selectively route private and public network traffic through a full-featured enterprise-level firewall that is powered by the software features of Ciena Vyatta NOS, Juniper's Junos OS or any self-installed operating system (BYOGWA) of your choice. These features include network protection by using customized firewall policies, IPSec VPN tunnels, and remote access, SSL VPN, dynamic routing (BGP/OSPF), GRE tunnels, customizable source and destination NAT, general network troubleshooting capabilities, and extended capabilities to integrate a customizable Cloud hosted firewall, router, and VPN gateway into your existing network infrastructure. Certain appliances also offer even more advanced security-focused features, such as Intrusion Prevention System, WAF, Deep Packet Inspection, and Antivirus.
{: shortdesc}

The appliances provide performance, ease of configuration, and maintenance advantages with the simplicity of running on a bare metal server. The hardware is sized to handle the routing/security load for multiple VLANs and can be ordered with redundant network links and redundant RAID arrays. All appliance features are customer-managed.

Both Juniper vSRX Standard and Virtual Router Appliance (VRA) are offered in two different modes: standalone or High Availability (HA) cluster.

## Firewall
{: #firewall}

{{site.data.keyword.cloud_notm}} Gateway Appliances deploy to protect your environment from external and internal threats by filtering both private and public facing traffic. Customers can manage the appliances themselves by defining policies and rules to allow or deny (among other actions) inbound or outbound network traffic, protecting their applications from internal and external users. Both IPv4 and IPv6 stacks are supported in a stateful manner.

## Virtual Private Network (VPN) gateway
{: #virtual-private-network-vpn-gateway}

Connect your onsite data center or office to the {{site.data.keyword.cloud_notm}} using VPN tunneling by provisioning your vSRX or VRA as a network gateway device. You can use an IPsec site-to-site VPN tunnel for secure communication from your enterprise data center or office to your {{site.data.keyword.cloud_notm}} network. Remote access IPsec VPN is also supported.

## Network Address Translation (NAT)
{: #network-address-translation-nat-}

With {{site.data.keyword.cloud_notm}} Gateway Appliances, you can provision application and database servers without public network interfaces while still allowing your servers to access the internet by using source NAT. You can also hide your servers behind the gateway device with destination NAT for enhanced security.

## Enterprise-grade routing
{: #enterprise-grade-routing}

For multi-tiered applications on different isolated networks, the appliances enable you to build connectivity between these networks with greater flexibility. You can set up dynamic routing by using Border Gateway Protocol (BGP), which allows you to announce your own public IP space to the {{site.data.keyword.cloud_notm}} routers. BGP also offers more flexibility for custom private network configurations when you use a mix of tunnels and direct link solutions.

## VLANs and the gateway appliance's role
{: #vlans-and-the-gateway-appliances-role}

A VLAN (virtual LAN) is a mechanism that segregates a physical network into many virtual segments. For convenience, traffic from multiple selected VLANs can be delivered through a single network cable, a process commonly called "trunking."

{{site.data.keyword.cloud_notm}} Gateway Appliances are managed in two different interfaces: one or more gateway appliance servers and fixture. The gateway appliance server provides an interface (GUI and API) for selecting the VLANs that you want to associate with your vSRX or VRA. Associating a VLAN with a gateway appliance reroutes (or "trunks") that VLAN and all of its subnets to your appliance, giving you control over filtering, forwarding, and protection. Servers in an associated VLAN can be reached only from other VLANs by going through your appliance; it is not possible to circumvent the appliance unless you bypass or disassociate the VLAN.

By default, a new gateway appliance is associated with two non-removable "transit" VLANs, one each for your _public_ and _private_ networks. These networks are typically used for administration, and they can be secured by gateway appliance commands separately.

The vSRX or VRA can manage VLANs that are associated with it only through the gateway appliance.

For information on how to manage VLANs from the **Gateway Appliances Details** screen, refer to the [Manage VLANs](/docs/gateway-appliance?topic=gateway-appliance-managing-vlans-and-gateway-appliances) topic.
{: note}
