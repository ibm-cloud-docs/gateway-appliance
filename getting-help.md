---

copyright:
  years: 2017, 2025
lastupdated: "2025-06-02"

keywords: contact, troubleshooting

subcollection: gateway-appliance

---

{{site.data.keyword.attribute-definition-list}}

# Getting help and support
{: #getting-help}

If you experience an issue or have questions when using {{site.data.keyword.cloud_notm}} Gateway Appliances (vFSA, VRA or vSRX), you can use the following resources before you open a support case.
{: shortdesc}

* Ask a question in the [AI assistant](/docs/overview?topic=overview-ask-ai-assistant) from the console or the {{site.data.keyword.cloud_notm}} CLI.
* Review [vFSA known limitations](/docs/vfsa?topic=vfsa-known-limitations-for-ibm-cloud-vfsa)
* Review the FAQs for [VRA](/docs/gateway-appliance?topic=gateway-appliance-faqs-for-ibm-virtual-router-appliance) in the product documentation.
* Review [vSRX known limitations](/docs/gateway-appliance?topic=gateway-appliance-known-limitations-for-ibm-cloud-juniper-vsrx).
* Check the status of the {{site.data.keyword.Bluemix_notm}} platform and resources by going to the [Status page](https://cloud.ibm.com/status){: external}.
* Review [Stack Overflow](https://stackoverflow.com/questions/tagged/ibm-cloud){: external} to see whether other users experienced the same problem. When you ask a question, tag the question with `ibm-cloud` and `Gateway appliences`, so that it's seen by the {{site.data.keyword.Bluemix_notm}} development teams.

If you still can't resolve the problem, you can open a support case. For more information, see [Creating support cases](/docs/account?topic=account-open-case). And if you're looking to provide feedback, see [Submitting feedback](/docs/overview?topic=overview-feedback).

## Providing support case details for vFSA
{: #support-case-details-vfsa}

To ensure a timely resolution to your issue, include the following information in your support case for issues with your vFSA:

1. The IP address (10 network or public network) or hostname of your Fortinet vFSA as well as its version.
1. To track down where issues are occurring across a network connection, provide the source IP address, destination IP address, the destination port and protocol, as well as any relevant output from network tools, such as `ping`, `traceroute`, `mtr`, or `nmap/netcat`.
1. For more complicated issues, a basic explanation of the expected network path of the connection or a network topology diagram is necessary.
1. Other useful information includes the security policy name that contains the expected allow or block.

## Providing support case details for Virtual Router Appliance
{: #support-case-details-vra}

To ensure a timely resolution to your issue, include the following information in your support case for issues with Vyatta:

1. The IP address (10 network or public network) or hostname of your VRA, as well as its NOS version.
1. To track down where issues are occuring across a network connection, provide the source IP address, destination IP address, the destination port and protocol, as well as any relevant output from network tools, such as `ping`, `traceroute`, `mtr`, or `nmap/netcat`.
1. For more complicated issues, a basic explanation of the expected network path of the connection or a network topology diagram is necessary.
1. Other useful troubleshooting information includes the firewall ruleset name and rule number of the expected rule for allowing or blocking traffic, including the output of `show firewall`. You can also enable logging to illustrate whether traffic is being allowed or not. In addition, you can use the `monitor`, `tshark`, and `tcpdump` (packet capturing) commands to show traffic on the ingress and egress interfaces. You can also use these commands to illustrate if traffice shows on one expected interface and not another. This can help prove a blocking or routing issue.
1. Gather any logs that are relevant to the issue. To do so, use `journlctl -a`, view the syslog entries, or use the `show log` commands.

## Providing support case details for vSRX
{: #support-case-details-vsrx}

To ensure a timely resolution to your issue, include the following information in your support case for issues with your vSRX:

1. The IP address (10 network or public network) or hostname of your Juniper vSRX as well as its version. As a reminder, versions `19.4R2-S3` and older have consistent cluster and crashing issues. If you are on any of those versions, please reboot to temporarily fix any clustering issues. You should also update to the latest version as soon as possible.
1. To track down where issues are occurring across a network connection, provide the source IP address, destination IP address, the destination port and protocol, as well as any relevant output from network tools, such as `ping`, `traceroute`, `mtr`, or `nmap/netcat`.
1. For more complicated issues, a basic explanation of the expected network path of the connection or a network topology diagram is necessary.
1. Other useful information includes the security policy name that contains the expected allow or block. You can also illustrate that traffic is being allowed or not using `show security match-policies` (tab-complete to finish the rest of the command). In addition, the `show security flow session` command shows the forward and response traffic on the ingress interfaces, as well as if packets are incrementing in one expected direction or not. You can also use `traceoptions` to receive Debug level output for the specified traffic.
1. For local sourced and destined traffic, please determine if the `PROTECT-IN` policy contains the proper allow settings, as this is used for control plane policing.
1. You should also generate RSI and log files. The RSI contains information on the state of the system, and the logs capture historical information that might be present.

   For a standalone device, you would do this ony once per node. For an HA pair, you should capture the RSI and logs for both. To do so, SSH to the gateway IP and login. The following example assumes you are logged into node 1:

   ```ssh
   cli
   request support information | save /var/log/rsi-node1
   file archive compress source /var/log/* destination /var/tmp/node1.tgz
   ```
   {: pre}

   This generates the RSI and logs for node 1. Next, move to the other node:

   ```ssh
   request routing-engine login node 0
   cli
   request support information | save /var/log/rsi-node0
   file archive compress source /var/log/* destination /var/tmp/node0.tgz
   file copy /var/tmp/node0.tgz node1:/var/tmp/
   ```
   {: pre}

   The same files are generated on node 0, and the resulting zip file is copied to node 1. You can use SCP or other tools to download thse files from the `/var/tmp` directory.
