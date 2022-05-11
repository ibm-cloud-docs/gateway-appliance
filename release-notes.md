---

copyright:
  years: 2017, 2022
lastupdated: "2022-05-05"

keywords: updates, changes, additions

subcollection: gateway-appliance

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Release notes for IBM Cloud Gateway Appliances
{: #gateway-appliance-release-notes}

Find out about new and updated features in gateway appliances.
{: shortdesc}

## 21 May 2021
{: #gateway-appliance-may2121}
{: release-note}

Renewing a vSRX license
:    The vSRX standard and CSB licenses for both 1G and 10G that were included with deployments before mid-May 2021 have an expiration date in 2021. After this license expires, updates for some new vSRX features might not take effect. A newer license with an expiration date in 2024 is now available, and you can renew your gateway license to obtain it. If you are using a High Availability vSRX, renewing your license automatically modifies the license on both vSRX nodes. You can find the current expiration date on the gateway appliance details page. 

: For more information, refer to [Renewing a vSRX license](/docs/vsrx?topic=vsrx-license-renewal).

## 20 April 2020
{: #gateway-appliance-apr2020}
{: release-note}

Checking vSRX readiness
:    You can now run readiness checks to verify the ability of your {{site.data.keyword.vsrx_full}} to perform certain gateway actions. They include:
    * OS reloads
    * License upgrades
    * Version upgrades

:    After you run a readiness check, errors alert you to any necessary actions that you should take before beginning one of these actions, or inform you that you're ready to proceed.

: For more information, refer to [Checking vSRX readiness](/docs/vsrx?topic=vsrx-vsrx-readiness#vsrx-readiness).

## 21 August 2018
{: #gateway-appliance-aug2118}
{: release-note}

Brocade operating system version 18.x
:    Version 18.x of the Brocade OS is now available for the {{site.data.keyword.vra_full}}. Among other new features, this version provides remediation for the Spectre security breach.

:    New features of the 18.x VRA are discussed in the following topics:
    * [Setting up an IPsec tunnel that works with zone firewalls](/docs/virtual-router-appliance?topic=virtual-router-appliance-setting-up-an-ipsec-tunnel-that-works-with-zone-firewalls)
    * [Configuring a VFP interface with IPsec and zone firewalls](/docs/virtual-router-appliance?topic=virtual-router-appliance-configuring-a-vfp-interface-with-ipsec-and-zone-firewalls)
    * [Using NAT with prefix based IPsec](/docs/virtual-router-appliance?topic=virtual-router-appliance-using-nat-with-prefix-based-ipsec)
    * [Troubleshooting your VFP Interface](/docs/virtual-router-appliance?topic=virtual-router-appliance-troubleshooting-your-vfp-interface)

:    If you are migrating from Vyatta 5400, the best way to upgrade to 18.x is through a full OS reload. For more information, see  [Upgrading the OS](/docs/virtual-router-appliance?topic=virtual-router-appliance-upgrading-the-os).

:    Because there is no simple one-to-one mapping of functionality between Vyatta 5400 and the {{site.data.keyword.vra_full}}, creating a baseline configuration for the VRA is helpful. An IBM Partner, WanClouds, can help you with this process, and provide guidance on creating functionality similar to the Vyatta 5400 on your VRA.

:    For more information about common issues encountered during this upgrade process, see [Vyatta 5400 common migration issues](/docs/virtual-router-appliance?topic=virtual-router-appliance-vyatta-5400-common-migration-issues).
