# Shared access to the account

You can give access to your account to the following user categories:

- **Toloka requesters with social authorization**

    Give access to your account to other clients who are [registered in Toloka](access.md) as requesters using social authorization.

- **SSO clients**

    Give access to other clients who use the same [SSO authentication](../sso/authentication.md) as you to access Toloka.

- **Toloka support**

    If you need help with setting up pools or projects, give [Toloka support](../troubleshooting/support.md) temporary view-only access to your account to get recommendations. Access will be automatically revoked in 7 days. If necessary, you can revoke access earlier.

## Access types

Toloka allows you to give two types of access to your account:

- **Full access**

    Use it if you want other people manage your projects and post tasks, and you will manage the finances.

- **View-only access**

    Use it if you don't want to give full access to your account, but want them to view the account information. You can also give view-only access to Toloka support to help you with your projects or troubleshoot the problems you have.

The main differences between the access types are listed in the table below.

Permissions | Full access | View-only access
----------- | :---------: | :--------------:
View projects, pools, tasks, finance information | + | +
[Manage projects](project.md) | + | -
[Manage pools](pool.md) | + | -
[Post tasks](task_upload.md) | + | -
[Get results](result-of-eval.md) | + | -
Manage access to account | + | -
Use [Toloka API](https://toloka.ai/docs/api/api-reference/) | + | -
Move tasks from [sandbox](sandbox.md) to Toloka production version | + | -
[Top up balance](refill.md) | - | -

You can view the list of accounts to which the permissions have been granted on the **Profile** page in the [Account access](https://platform.toloka.ai/requester/profile/access) tab.

## How to grant access to the account? {#multiple-access-grant}

{% list tabs %}

- Other requesters

  To give access to other clients, you must know their user IDs.

  {% cut "Where to get User ID" %}

  The client can get their **User ID** on their [Profile](https://platform.toloka.ai/requester/profile) page:

  ![Getting User ID](../_images/register/user-id.png =333x)

  {% endcut %}

  1. Go to the **Profile** → **Account access** tab (or click [this link]((https://platform.toloka.ai/requester/profile/access))).

  1. Click **Add user**.

  1. Enter the client **User ID**.

  1. In the drop-down list, select **Full access** or **View only**.

  1. Click **Grant access**.

- SSO clients

  {% note info %}

  Only the enterprise clients with SSO authentication enabled and set up can use this. Read the [Toloka SSO authentication](../sso/authentication.md) section which contains the detailed description of this method and its restrictions.

  {% endnote %}

  To give access to SSO clients, you must know their enterprise email addresses used to log in to Toloka with [SSO authentication](../sso/authentication.md).

  1. Go to the **Profile** → **Account access** tab (or click [this link]((https://platform.toloka.ai/requester/profile/access))).

  1. Click **Add user**.

  1. Enter the client enterprise email address.

  1. In the drop-down list, select **Full access** or **View only**.

  1. Click **Grant access**.

- Toloka support

  You can give Toloka support view-only access to your account.

  1. Go to the **Profile** → **Account access** tab (or click [this link]((https://platform.toloka.ai/requester/profile/access))).

  1. Click **Grant access to Toloka Support**.

  1. Click **Grant access**.

  Access to Toloka support will be automatically revoked in 7 days. If necessary, you can revoke access earlier.

{% endlist %}

## Restrictions {#restrictions}

You can't give access to your account:

- To the clients who **aren't registered in Toloka as requesters** using either social authorization or SSO authentication methods.

- To the Tolokers even if you know their ID.

## How to revoke access to the account? {#multiple-access-revoke}

1. Go to the **Profile** → **Account access** tab (or click [this link]((https://platform.toloka.ai/requester/profile/access))).

1. Click the ![Revoke access](../_images/register/revoke-access.svg) icon next to the client you want to revoke access from.

1. Click **Revoke** in the popup dialog.

## How to log in to your account {#multiple-access-auth}

{% note alert "Restriction" %}

Depending on the type of access, some functions are restricted.

{% endnote %}

To log in to the requester account you were given access to:

1. Log in to Toloka with the client for which access was granted.

1. In the upper-right corner, click your account's avatar.

1. Choose the requester account you want to log in to.

## See also {#see-also}

- [{#T}](access.md)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles-internal](../../../_includes/image-styles-internal.md) %}
