---

copyright:
  years: 2017, 2020
lastupdated: "2020-08-13"

keywords: manage, associate, disassociate, route, bypass

subcollection: gateway-appliance

---

{{site.data.keyword.attribute-definition-list}}

# Managing VLANs with a gateway appliance
{: #managing-vlans-and-gateway-appliances}

You can manage, associate, disassociate, route, and bypass VLANs with a gateway appliance. You can perform these actions from the [Gateway Appliance Details page](/docs/gateway-appliance?topic=gateway-appliance-viewing-gateway-appliance-details). Before routing a VLAN to a gateway appliance, please make sure that the VLAN and subnet gateways of subnets assigned to the VLAN are configured properly on the gateway appliance itself.
{: shortdesc}

## Associating a VLAN to a gateway appliance
{: #associate-a-vlan-to-a-gateway-appliance}

A VLAN must be associated to a gateway appliance before it can be routed. VLAN association is the linking of an eligible VLAN to a network gateway so that it can be routed to a gateway appliance in the future. The process of association does not automatically route a VLAN to a gateway appliance; the VLAN continues to use front-end and back-end customer routers until it is routed to the gateway.

VLANs can be associated to only one gateway at a time and must not have a firewall. Perform the following procedure to associate a VLAN to a network gateway.

1. [Access the Gateway Appliance Details page](/docs/gateway-appliance?topic=gateway-appliance-viewing-gateway-appliance-details) in the IBM Cloud console.
2. Select the VLAN you want from the **Associate a VLAN** list.
3. Click the **Associate** button to associate the VLAN.

After associating a VLAN to the gateway appliance, it appears in the Associated VLANs section of the Gateway Appliance Details page. From this section, the VLAN can be routed to the gateway, or be disassociated from the gateway. Additional eligible VLANs can be associated to a gateway appliance at any time by repeating these steps.

## Routing an associated VLAN
{: #route-an-associated-vlan}

Associated VLANs are linked to a gateway appliance, but traffic in and out of the VLAN does not hit the gateway until the VLAN is routed. After an associated VLAN is routed, all front-end and back-end traffic is routed through the gateway appliance as opposed to customer routers.

Perform the following procedure to route an associated VLAN:

1. [Access the Gateway Appliance Details page](/docs/gateway-appliance?topic=gateway-appliance-viewing-gateway-appliance-details) in the IBM Cloud console.
2. Locate the VLAN you want in the Associated VLANs section.
3. Select **Route VLAN** from the Actions menu.
4. Click **Yes** to route the VLAN.

After routing a VLAN, all front-end and back-end traffic moves from the customer routers to the network gateway. Additional controls related to traffic and the gateway appliance itself can be taken by accessing the gateway's management tool. Routing through the network gateway can be discontinued at any time by [bypassing the gateway appliance](#bypass-gateway-appliance-routing-for-a-vlan).

## Bypassing gateway appliance routing for a VLAN
{: #bypass-gateway-appliance-routing-for-a-vlan}

After a VLAN is routed, all front-end and back-end traffic travels through the network gateway. At any time, the gateway appliance can be bypassed so that traffic returns to the front-end and back-end customer routers (FCR and BCR).

Bypassing a VLAN allows the VLAN to remain associated to the network gateway. If the VLAN should no longer be associated with the gateway appliance, see [Disassociating a VLAN from a gateway appliance](#disassociate-a-vlan-from-a-gateway-appliance).

Perform the following procedure to bypass gateway routing for a VLAN:

1. [Access the Gateway Appliance Details page](/docs/gateway-appliance?topic=gateway-appliance-viewing-gateway-appliance-details) in the IBM Cloud console.
2. Locate the VLAN you want in the Associated VLANs section.
3. Select **Bypass VLAN** from the Actions menu.
4. Click **Yes** to bypass the gateway.

After bypassing the network gateway, all front-end and back-end traffic routes through the FCR and BCR associated with the VLAN. The VLAN remains associated with the gateway appliance and can be routed back to the gateway appliance at any time.

## Disassociating a VLAN from a gateway appliance
{: #disassociate-a-vlan-from-a-gateway-appliance}

VLANs can be linked to one gateway appliance at a time through [association](#associate-a-vlan-to-a-gateway-appliance). Association allows the VLAN to be routed to the gateway appliance at any time. If a VLAN should be associated to another gateway appliance, or if the VLAN should no longer be associated to its gateway, disassociation is required. Disassociation removes the "link" from the VLAN to the gateway appliance, allowing it to be associated to another gateway, if necessary.

Perform the following procedure to disassociate a VLAN from a gateway appliance:

1. [Access the Gateway Appliance Details page](/docs/gateway-appliance?topic=gateway-appliance-viewing-gateway-appliance-details) in the IBM Cloud console.
2. Locate the VLAN you want in the Associated VLANs section.
3. Select **Disassociate** from the **Actions** menu.
4. Click **Yes** to disassociate the VLAN.

After disassociating a VLAN from a gateway appliance, the VLAN can be associated to another gateway. The VLAN can also be associated back to the gateway appliance at any time. After disassociating a VLAN from a gateway appliance, the VLAN's traffic cannot be routed through the gateway. VLANs must be associated to a gateway appliance before they can be routed.
