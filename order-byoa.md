---

copyright:
  years: 2017, 2026
lastupdated: "2026-01-29"

keywords: order, byoa

subcollection: gateway-appliance

---

{{site.data.keyword.attribute-definition-list}}

# Ordering a Bring Your Own gateway appliance
{: #order-byoa}

{{site.data.keyword.cloud}} Gateway 1G and 10G offerings include the Virtual Router Appliance and Juniper vSRX. You can also deploy a third gateway solution with no operating system installed. This solution provides the same 1G and 10G hardware, as well as the same networking, but provides you with the flexibility to install a custom operating system and gateway software stack. You would need a custom installation of the operating system, including hypervisor, and the virtual machine from the IPMI of the bare metal device. Examples of gateway appliances that have been created and installed by clients on the BYOGWA platform include pfSense directly to hard disk, Palo Alto VM-Series Firewall on a hypervisor, FortiGate-VM on a hypervisor, and Juniper vSRX on a hypervisor.
{: shortdesc}

Use the information in this topic to order a gateway appliance with the Bring Your Own Appliance (BYOA) option.

You must have the software licenses and images for your chosen operating system and gateway software solution.
{: note}

## Ordering with a linked account
{: #order-linked-account}

To order a gateway appliance with the BYOA option, perform the following procedure:

1. From your browser, open the [IBM Cloud console](https://cloud.ibm.com){: external} and log in to your account.

2. Select the Menu icon ![Menu icon](../../icons/icon_hamburger.svg) from the upper left, then click **Classic Infrastructure**.

3. Choose **Network > Gateway Appliances**.

4. Choose **Other** from the **Gateway Vendor** section.

    If you do not see the **Other** option, contact IBM Support for details on enabling it for your account.
    {: note}

5. Enter your Hostname and Domain Name information in the **Gateway Appliance** section. Ensure the default information that populates the fields is accurate, and make any necessary corrections.

6. Select a data center location and the specific pod that you want from the menu.

    Only pods that already have an associated VLAN show. If you want to provision your gateway appliance in a pod that isn't listed, you must create a VLAN in that pod.
    {: note}

    The High Availability option is selected by default.
    {: note}

7. From the **Configuration** section, choose your processor. Single processors are 1G and dual processors are 10G.

8. Select your RAM settings.

9. Select your SSH keys, if you want to use them to authenticate access to your new gateway.

10. From the **Storage Disks** section, choose the options that meet your storage requirements.

11. From the **Network Interface** section, select your uplink port speeds. The default selection is a single interface, but there are redundant and private options as well. Choose the one that best fits your needs.

    The **Network Interface Add Ons** section allows you to select an IPv6 address if required, and shows you any additional included default options.
    {: note}

12. Review your selections, read and check the Third-Party Service Agreements, then click **Create**. The form verifies the order automatically.

After your order is approved, the provisioning of your IBM Cloud Gateway starts automatically. When the provisioning process completes, the new gateway appears in the Gateway Appliances list page. Click the gateway name to open the Gateway Details page that shows the IP addresses, login username, and password for the device.

## Installing an operating system on the gateway
{: #install-os}

To install an operating system on the Gateway, perform the following procedure:

This procedure uses the IPMI interface to mount and boot to an OS image. Make sure that you have the ISO image of the operating system you want to install, as well as the Gateway software image, and any required licenses.
{: important}

1. [Access the Gateway Appliances page](/docs/gateway-appliance?topic=gateway-appliance-viewing-all-gateway-appliances#viewing-all-gateway-appliances) in the IBM Cloud console.

2. Click the Gateway Appliance name for BYOG appliance to access the Gateway Appliance Details page.

3. Click the **Remote Management** tab on the left side of the page, then make note of the IPMI private IP address and root credentials that are listed in the **Management Details** section.

4. Mount and boot your operating system image, then install it using one of the methods explained in [Mounting an ISO on a bare metal server](/docs/bare-metal?topic=bare-metal-bm-mount-iso).

    Use the IPMI private IP address and root credentials from step 2 here.
    {: note}

    The server should, by default, boot to the mounted image without the need for a password. Ensure that no other media is mounted to the server before you proceed with this step.
    {: important}

    For more information on setting up a VPN connection, see [Getting started with {{site.data.keyword.cloud_notm}} Virtual Private Networking](/docs/iaas-vpn?topic=iaas-vpn-getting-started#getting-started).
    {: tip}
