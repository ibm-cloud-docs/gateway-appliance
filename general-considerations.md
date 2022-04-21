---

copyright:
  years: 2018, 2022
lastupdated: "2022-04-19"

keywords: vsrx, vra, gateway, appliance, considerations

subcollection: gateway-appliance

---

{{site.data.keyword.attribute-definition-list}}

# General gateway appliance considerations
{: #general-considerations}

The following considerations help provide additional information for using your gateway appliances.
{: shortdesc}

## Bandwidth allotment
{: #bandwidth-allotment}

Bandwidth allotment is the allowed public bandwidth during a monthly billing cycle. For a gateway appliance, this is determined by the allotment assigned to each node or server. You can view this allotment by performing the following procedure:

1. From your browser, open the [IBM Cloud catalog](https://cloud.ibm.com){: external} and log in to your account.
2. Select the Menu icon ![Menu icon](../../icons/icon_hamburger.svg) from the top left, then click **Classic Infrastructure**.
3. Choose **Network > Gateway Appliances**.
4. Click on the gateway whose details you want to view. 

The bandwidth allotment is in the **Network details** section, under **Public bandwidth allotment**. To view the current usage, click on the bandwidth value for the current billing cycle. 

For standalone configurations, bandwidth allotment is defined for the individual server. For example, if the server has a 10 GB monthly allotment, then that is what is allowed for the gateway. 

For High Availability (HA) configurations, the gateway has two servers, each with the same bandwidth allotment. The allotment for each server is available for use by the gateway but is not automatically pooled. HA gateways operate with a primary (active) and secondary (passive) nodes. The primary node manages all traffic, while the secondary node provides failover protection. The bandwidth of a server is used if that server is the primary node. For example, if a primary node server runs out of bandwidth during a cycle, the bandwidth of the secondary node is not automatically used. The unused secondary node server bandwidth is only used if the primary node has failed over to the secondary node.
