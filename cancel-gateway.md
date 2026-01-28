---

copyright:
  years: 2017, 2026
lastupdated: "2026-01-28"

keywords: cancel, appliances

subcollection: gateway-appliance

---

{{site.data.keyword.attribute-definition-list}}

# Canceling a gateway appliance
{: #cancel-gateway-appliance}
{: help}
{: support}

You can cancel your gateway appliance at any time by following these instructions.
{: shortdesc}

1. From your browser, open the [IBM Cloud console](/login){: external} and log in to your account.
2. Select the Menu icon ![Menu icon](../icons/icon_hamburger.svg) from the upper left, then click **Infrastructure > Classic Infrastructure**.
3. Choose **Network > Gateway Appliances**.
4. Click the Gateway Appliance name to open the Gateway Appliance Details page.
5. From the Hardware section, click the name of the hardware member to open the server details page.
6. Select **Actions > Cancel device** and follow the prompts to cancel the gateway appliance.

For Highly Available server pairs, you must select and cancel both server members that are listed in the Hardware section on the Gateway Appliance Details page to cancel the gateway.
{: note}

After you cancel the gateway appliance, the servers are reclaimed at the next billing cycle. For example, if you cancel the servers on 8 September, the service is available until it is reclaimed on 1 October.

You can verify whether your gateway appliance is in the process of being canceled by viewing the Gateway Appliance Details page. Gateways in the process of being canceled show as **Cancel pending**.

If necessary, you can expedite the process by opening a case with IBM Support and requesting that the gateway appliance be reclaimed immediately. This process can take 24 to 48 hours.
{: tip}
