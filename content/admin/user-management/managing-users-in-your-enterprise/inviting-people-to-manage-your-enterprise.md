---
title: Inviting people to manage your enterprise
intro: 'You can {% ifversion ghec %}invite{% else %}add{% endif %} and remove enterprise owners{% ifversion ghec %} and billing managers{% endif %} for your enterprise account.'
permissions: 'Enterprise owners can {% ifversion ghec %}invite other people to become{% elsif ghes %}add{% endif %} additional enterprise administrators.'
redirect_from:
  - /github/setting-up-and-managing-your-enterprise/managing-users-in-your-enterprise/inviting-people-to-manage-your-enterprise
  - /github/setting-up-and-managing-your-enterprise-account/inviting-people-to-manage-your-enterprise-account
  - /articles/inviting-people-to-collaborate-in-your-business-account
  - /articles/inviting-people-to-manage-your-enterprise-account
  - /github/setting-up-and-managing-your-enterprise/inviting-people-to-manage-your-enterprise
versions:
  ghec: '*'
  ghes: '*'
type: how_to
topics:
  - Administrator
  - Enterprise
  - User account
shortTitle: Invite people to manage
---

## About users who can manage your enterprise account

{% data reusables.enterprise-accounts.enterprise-administrators %} For more information, see "[Roles in an enterprise](/admin/user-management/managing-users-in-your-enterprise/roles-in-an-enterprise)."

{% ifversion ghes %}

If you want to manage owners and billing managers for an enterprise account on {% data variables.product.prodname_dotcom_the_website %}, see "[Inviting people to manage your enterprise](/enterprise-cloud@latest/admin/user-management/managing-users-in-your-enterprise/inviting-people-to-manage-your-enterprise)" in the {% data variables.product.prodname_ghe_cloud %} documentation.

{% endif %}

{% ifversion ghec %}

If your enterprise uses {% data variables.product.prodname_emus %}, enterprise owners can only be added or removed through your identity provider. For more information, see "[About {% data variables.product.prodname_emus %}](/enterprise-cloud@latest/admin/authentication/managing-your-enterprise-users-with-your-identity-provider/about-enterprise-managed-users)."

{% endif %}

{% tip %}

**Tip:** For more information on managing users within an organization owned by your enterprise account, see "[Managing membership in your organization](/articles/managing-membership-in-your-organization)" and "[Managing people's access to your organization with roles](/articles/managing-peoples-access-to-your-organization-with-roles)."

{% endtip %}

## {% ifversion ghec %}Inviting{% elsif ghes %}Adding{% endif %} an enterprise administrator to your enterprise account

{% ifversion ghec %}After you invite someone to join the enterprise account, they must accept the emailed invitation before they can access the enterprise account. Pending invitations will expire after 7 days.{% endif %}

{% ifversion enterprise-membership-view-improvements %}
You can see all pending invitations to become an administrator of your enterprise account. For more information, see "[Viewing people in your enterprise](/admin/user-management/managing-users-in-your-enterprise/viewing-people-in-your-enterprise#viewing-pending-invitations)."
{% endif %}

{% data reusables.enterprise-accounts.access-enterprise %}
{% data reusables.enterprise-accounts.people-tab %}
{% data reusables.enterprise-accounts.administrators-tab %}
1. Above the list of administrators, click {% ifversion ghec %}**Invite admin**{% elsif ghes %}**Add owner**{% endif %}.
1. Type the username, full name, or email address of the person you want to invite to become an enterprise administrator, then select the appropriate person from the results.
{%- ifversion ghec %}
1. Select **Owner** or **Billing Manager**.
1. Click **Send Invitation**.
{%- endif %}
{%- ifversion ghes %}
1. Click **Add**.
{%- endif %}

## Removing an enterprise administrator from your enterprise account

Only enterprise owners can remove other enterprise administrators from the enterprise account.

{% ifversion ghec %}
If the administrator you want to remove is a member of any organizations owned by the enterprise, you can choose **Convert to member**, which will remove their administrative role but retain their organization memberships, or **Remove from enterprise**, which will remove both their administrative role and organization memberships.
{% endif %}

{% data reusables.enterprise-accounts.access-enterprise %}
{% data reusables.enterprise-accounts.people-tab %}
{% data reusables.enterprise-accounts.administrators-tab %}
{%- ifversion ghec or ghes > 3.6 %}
1. Next to the username of the person you'd like to remove, select the {% octicon "kebab-horizontal" aria-label="Administrator settings" %} dropdown menu, then click **Convert to member**{% ifversion ghec %} or **Remove from enterprise**{% endif %}.
  ![Screenshot of a user in the enterprise administrators list. A dropdown menu, labeled with a kebab icon, is highlighted with an orange outline.](/assets/images/help/business-accounts/administrator-settings.png)
1. Read the confirmation, then click **Yes, convert USERNAME to member**{% ifversion ghec %} or **Yes, remove USERNAME**{% endif %}.
{%- else %}
1. Next to the username of the person you'd like to remove, select the {% octicon "gear" aria-label="Administrator settings" %} dropdown menu, then click **Remove owner**.
1. Read the confirmation, then click **Remove owner**.
{%- endif %}
