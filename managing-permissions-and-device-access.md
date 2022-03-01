---

copyright:
  years: 2021
lastupdated: "2021-09-09"

subcollection: gateway-appliance

---

{{site.data.keyword.attribute-definition-list}}

# Managing permissions and device access
{: #managing-permissions-and-device-access}

To view and manage your gateway appliances, you need the correct permissions and access to devices. After your account administrator grants your user account permissions and access, you can view your gateway appliance details by using the {{site.data.keyword.cloud}} console, or by using the {{site.data.keyword.slapi_short}}. The information or actions that you see depend on your account's permissions and device access.
{: shortdesc}

You can assign device access to any user on your account, but not to yourself. Only an account's administrator has access to all devices on their customer account and can set access for all other users on their account.

The following permissions are required for viewing and managing various parts of your gateway appliances:

* **Manage Network Gateways** - Allows you to view your list of gateway appliances. It also allows you to view and manage the details of a specific gateway appliance.
* **View Hardware Details** - Allows you to view the hardware for a specific gateway appliance. If you do not have this permission, you might have trouble viewing and managing a gateway appliance's details.
* **OS Reloads and Rescue Kernel** - Allows you to perform OS reloads.

## Adding permissions for your users
{: #adding-permissions-for-your-users}

If you are the account administrator and you want to grant a user permission to view and manage gateway appliance details, complete the following steps.

1. Log in to the [Access (IAM)](https://cloud.ibm.com/iam/users){: external} page in the {{site.data.keyword.cloud}} console.
2. Select **View: My classic infrastructure users**.
3. Select a user, click the **Classic infrastructure** tab, then click the **Permissions** tab.
4. Expand the **Network** category and select **Manage Network Gateways**.
5. Expand the **Devices** category and select **View Hardware Details** and **OS Reloads and Rescue Kernel**.
6. Click **Apply**.

### Adding specific device-level permissions
{: #adding-specific-device-level-permissions}

If you want to provide a user access to a specific device, complete the following steps.

1. Log in to the [Access (IAM)](https://cloud.ibm.com/iam/users){: external} page in the {{site.data.keyword.cloud}} console.
2. Select **View: My classic infrastructure users**.
3. Select a user, then click the **Classic infrastructure** tab and the **Devices** tab.
4. In the **Select type** section, select **All bare metal servers** to allow users to access all the bare metal devices.
5. In the **Enable future access** section, select **Auto bare metal server access** to grant the user permanent access to any newly added bare metal device.
6. Use the devices table to grant a user access to specific, individual devices.
7. Click **Set**.

In order to see specific devices, you must already have the correct permissions enabled on the permissions tab. If you do not, no devices will be listed.
{: tip}

## Next steps
{: #next-steps-device-access}

User permissions are updated immediately after the changes are submitted. If permissions are granted, the user can view or interact with the selected features. If permissions are removed, the user can no longer view or interact with the selected features. Permissions can be updated again at any time.
