---

copyright:
  years: 2017, 2024
lastupdated: "2024-11-08"

keywords: manage, associate, disassociate, route, bypass, vlan

subcollection: gateway-appliance

---

{{site.data.keyword.attribute-definition-list}}

# Managing VLANs with a gateway appliance
{: #managing-vlans-and-gateway-appliances}

By using a gateway appliance and the IBM Cloud console, you can manage your [VLANs](/networking/vlans){: external} with the "associate", "disassociate", "route through", and "route around" actions.
{: shortdesc}

While the "associate" and "disassociate" actions are administrative in nature and do not change the way traffic flows (unless you are disassociating a VLAN while it is in the "route through" state), the "route through" and "route around" actions do change the way traffic flows. The "Route through" action essentially means that you manage your own VLANs on your own gateway appliance, while "route around" means that the IBM Cloud network team manages your VLANs on your Front-end Customer Routers (FCR) and Back-end Customer Routers (BCR).

You can perform these actions from the [Gateway Appliance Details page](/docs/gateway-appliance?topic=gateway-appliance-viewing-gateway-appliance-details) by selecting the **VLANs** tab.

Before you set a VLAN to "route through" on a gateway appliance, make sure that the VLAN and subnet gateways of the subnets that are assigned to the VLAN are configured properly on the gateway appliance itself. Also make sure to allow proper traffic flow using firewall rules or security policies. If you don't configure the VLANs, subnet gateways, and firewall rules or security policies properly before you set the VLAN to "route through", the traffic is routed to your gateway appliance and might cause outages to your servers or services on that VLAN. For Juniper vSRX, refer to [Creating the new interface, zone, and address book subnet](/docs/vsrx?topic=vsrx-creating-the-new-interface-zone-and-address-book-subnet), and for Vyatta Virtual Router Appliance, refer to [Configuring your VLANs](/docs/virtual-router-appliance?topic=virtual-router-appliance-routing-your-vlans).
{: tip}

## Associating a VLAN to a gateway appliance
{: #associate-a-vlan-to-a-gateway-appliance}

VLAN association is the administrative linking of an eligible VLAN to a gateway appliance so that it can be set to "route through". You must associate a VLAN to a gateway appliance before it can be set to "route through", and this process does not automatically set it to "route through". The VLAN remains managed by the FCRs or BCRs until it is set to "route through" on the Gateway Appliance Details page.

VLANs can be associated to only one gateway appliance at a time and must not have a [hardware firewall](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-about-hardware-firewall-shared) already applied. If there is, traffic on all servers on that VLAN is routed to the hardware firewall. VLANs must also be in the same pod as the gateway appliance. A pod is defined by the specific FCR and BCR that the gateway appliance, servers, and VLANs are behind.

To associate a VLAN to a gateway appliance, follow these steps:

1. From your browser, open the [IBM Cloud console](/login){: external} and log in to your account.
1. Select the Menu icon from the upper left, then click **Infrastructure > Classic Infrastructure**.
1. Choose **Network > Gateway Appliances**.
1. Click the name of the network gateway that you want to view to access the Gateway Appliance Details page.
2. Select the VLANs tab, then click the blue **Associate VLAN** button. Select the VLAN that you want to associate with your gateway appliance from the **Associate VLAN** menu.
3. Click the **Associate** button to associate the VLAN.

After you associate a VLAN to the gateway appliance, the VLAN appears in the list of associated VLANs in the VLANs tab of the Gateway Appliance Details page. From this section, you can set the VLAN to "route through" or be disassociated from the gateway appliance. You can associate additional VLANs to a gateway appliance by repeating these steps.

## Setting an associated VLAN to "route through"
{: #route-an-associated-vlan}

Associated VLANs are linked to a gateway appliance, but traffic to or from servers in the VLAN does not traverse the gateway appliance until the VLAN is set to "route through". After you set a VLAN to "route through", all of the subnets on that VLAN are statically routed to the gateway appliance from the FCRs or BCRs. This process also adds the VLAN's `allow` or `trunk` configuration lines for the switchports between the gateway appliance and the servers on the VLAN, which makes the gateway appliance act as the next-hop router and firewall for servers on that VLAN.

To set an associated VLAN to "route through", follow these steps:

1. From your browser, open the [IBM Cloud console](/login){: external} and log in to your account.
1. Select the Menu icon from the upper left, then click **Infrastructure > Classic Infrastructure**.
1. Choose **Network > Gateway Appliances**.
1. Click the name of the network gateway that you want to view to access the Gateway Appliance Details page.
2. Click the **VLANs** tab on the left.
3. Select the checkbox next to the VLANs that you want to set to "route through", then click the **Route Through** button.
4. Click **OK** to confirm.

This action causes a brief outage with services on that VLAN, as traffic is routed away from the gateway appliance.
{: note}

All traffic to and from servers on your VLAN now use the gateway appliance as the next-hop router. You can configure and control the VLAN and its traffic by accessing the gateway appliance through SSH or its native GUI.

Servers within the same subnet and VLAN do not traverse the gateway appliance when connecting to each other, but servers on the same VLAN in different subnets will traverse the gateway appliance when connecting to each other.
{: tip}

## Bypassing gateway appliance routing for a VLAN
{: #bypass-gateway-appliance-routing-for-a-vlan}

You can bypass the gateway appliance so that traffic uses only the FCR or BCR.

Bypassing a VLAN does not disassociate the VLAN from the gateway appliance. If the VLAN is no longer associated with the gateway appliance, refer to the procedure on disassociating a VLAN from a gateway appliance in this topic.
{: note}

To bypass gateway routing for a VLAN, follow these steps:

1. From your browser, open the [IBM Cloud console](/login){: external} and log in to your account.
1. Select the Menu icon from the upper left, then click **Infrastructure > Classic Infrastructure**.
1. Choose **Network > Gateway Appliances**.
1. Click the name of the network gateway that you want to view to access the Gateway Appliance Details page.
2. Click the **VLANs** tab on the left.
3. Select the checkbox next to the VLANs that you want to set to "route around", then click the **Route Around** button.
4. Click **OK** to confirm.

This action causes a brief outage with services on that VLAN, as traffic is routed away from the gateway appliance.
{: note}

After bypassing the network gateway, all server traffic egressing and ingressing the VLAN uses the FCR or BCR (instead of the gateway appliance) as the next-hop router. The VLAN remains associated with the gateway appliance and can be routed back at any time.

## Disassociating a VLAN from a gateway appliance
{: #disassociate-a-vlan-from-a-gateway-appliance}

If you need to associate a VLAN to another gateway appliance, or if you don't want the VLAN associated to its current gateway appliance, you can disassociate it. Disassociation removes the reservation that the gateway appliance has on the VLAN, allowing it to be associated to another gateway appliance or firewall. If the VLAN is set to "route through", then the VLAN will also be functionally set to "route around" while being disassociated.

To disassociate a VLAN from a gateway appliance, follow these steps:

1. From your browser, open the [IBM Cloud console](/login){: external} and log in to your account.
1. Select the Menu icon from the upper left, then click **Infrastructure >  Classic Infrastructure**.
1. Choose **Network > Gateway Appliances**.
1. Click the name of the network gateway that you want to view to access the Gateway Appliance Details page.
2. Click the **VLANs** tab on the left.
3. Select the checkbox next to the VLANs that you want to set to disassociate and then click the blue **Disassociate** button on the right.
4. Click **OK** to confirm.

If the VLAN is set to "route through", a brief outage occurs with services on that VLAN as it reconfigures. If the VLAN is set to "route around", then there is no outage.
{: note}

The VLAN can now be associated to another gateway appliance.
