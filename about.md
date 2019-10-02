---

copyright:
  years: 2018
lastupdated: "2018-10-22"

keywords: about, gateway, appliance, firewall, vpn, nat, routing, vlan

subcollection: gateway-appliance

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:note: .note}
{:important: .important}

# About IBM Cloud Gateway Appliance
{: #about}

{{site.data.keyword.cloud}} Gateway Appliances allow you to selectively route private and public network traffic through a full-featured enterprise level firewall powered by the software features of VyOS, JunOS or any other operating system (BYOA) you choose, such as full routing stacks, QoS and traffic sharing, policy-based routing, and VPN. The appliances provide performance, ease of configuration and maintenance advantages with the simplicity of running on a bare metal server. The hardware is sized to handle the routing/security load for multiple VLANs and can be ordered with redundant network links and redundant RAID arrays. All appliance features are customer-managed.

Both Juniper vSRX Standard and Virtual Router Appliance (VRA) are offered in two different modes: standalone or High Availability (HA) cluster.

## Firewall
{: #firewall}
IBM Gateway Appliances deploy to protect your environment from external and internal threats by filtering both private and public facing traffic. Customers can manage the appliances themselves by defining policies and rules to allow or deny (among other actions) inbound or outbound network traffic, protecting their applications from internal and external users. Both IPv4 and IPv6 stacks are supported in a stateful manner.

## Virtual Private Network (VPN) Gateway
{: #virtual-private-network-vpn-gateway}
Connect your on-site data center or office to the IBM Cloud using VPN tunneling by provisioning your vSRX or VRA as a network gateway device. You can use an IPsec site-to-site VPN tunnel for secure communication from your enterprise data center or office to your IBM Cloud network. Remote access IPSEC VPN is also supported.

## Network Address Translation (NAT)
{: #network-address-translation-nat-}
With IBM Gateway Appliances, you can provision application and database servers without public network interfaces while still allowing your servers to access the Internet using Source NAT. You can also hide your servers behind the gateway device with Destination NAT for enhanced security.

## Enterprise-grade Routing
{: #enterprise-grade-routing}
For multi-tiered applications on different isolated networks, the appliances enable you to build connectivity between these networks with greater flexibility. You can set up dynamic routing using BGP, which allows you to announce your own public IP space to the IBM Cloud routers. BGP will also offer more flexibility for custom private network configurations when using a mix of tunnels and direct link solutions.

## VLANs and the gateway appliance's role
{: #vlans-and-the-gateway-appliance-s-role}
A VLAN (virtual LAN) is a mechanism that segregates a physical network into many virtual segments. For convenience, traffic from multiple selected VLANs can be delivered through a single network cable, a process commonly called "trunking."

Gateway Appliances managed in two different interfaces: The Gateway Appliance server(s) and fixture. The Gateway Appliance provides an interface (GUI and API) for selecting the VLANs you want to associate with your vSRX or VRA. Associating a VLAN with a Gateway Appliance reroutes (or "trunks") that VLAN and all of its subnets to your appliance, giving you control over filtering, forwarding, and protection. Servers in an associated VLAN can only be reached from other VLANs by going through your appliance; it is not possible to circumvent the appliance unless you bypass or disassociate the VLAN.

By default, a new Gateway Appliance is associated with two non-removable "transit" VLANs, one each for your _public_ and _private_ networks. These networks typically are used for administration, and they can be secured by Gateway Appliance commands separately.

The vSRX or VRA can only manage VLANs that are associated with it through the Gateway Appliance.

For information on how to manage VLANs from the **Gateway Appliances Details** screen, refer to the [Manage VLANs](/docs/infrastructure/gateway-appliance?topic=gateway-appliance-managing-vlans-and-gateway-appliances) topic.
