---

copyright:
  years: 2017, 2019
lastupdated: "2019-10-23"

keywords: view, appliances, portal

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

# Cancelling a Gateway Appliance
{: #cancel-gateway-appliance}

You can cancel your Gateway Appliance at any time. To do so, perform the following procedure:

1. From your browser, open the [IBM Cloud catalog ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://cloud.ibm.com){:new_window} and log into your account.
2. Select the Menu icon ![Menu icon](../../icons/icon_hamburger.svg) from the top left, then click **Classic Infrastructure**.
3. Choose **Network > Gateway Appliances**.
4. Click the Gateway Appliance name to open the Gateway Appliance Details page.
5. From the Hardware section, click the name of the hardware member to open the server details screen.

  <img src="images/cancel-gateway.png" alt="drawing" style="width: 400px;"/>

5. Select **Actions > Cancel device** and follow the prompts to cancel the Gateway Appliance.

For Highly Available server pairs, you must select and cancel both server members listed in the Hardware section on the Gateway Appliance Details page in order to cancel the Gateway.
{: note}

Once you cancel the Gateway Appliance, the server(s) will be reclaimed at the next billing cycle. For example, if you cancel the server(s) on September 8, the service will be available until it is reclaimed on October 1.

You can verify if your Gateway Appliance is in process of being cancelled by viewing the Gateway Appliance Details page. Gateways in the process of being cancelled will show as **Cancel pending**.

  <img src="images/cancel-pending.png" alt="drawing" style="width: 500px;"/>

If necessary, you can perform the process quicker by opening a ticket with IBM support and requesting the Gateway Appliance be reclaimed immediately. This process can take 24 to 48 hours.
{: tip}
