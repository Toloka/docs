# Shared access to the requester's account

You can give access to your account:

{% list tabs %}

- Other requesters

  ### Full access

  {% note alert "Restriction" %}

  Requesters who are granted full access won't be able to use the Toloka API, connect to Yandex.Disk, top up the balance, or move tasks from the [sandbox](../../glossary.md#sandbox) to the main version of Toloka.

  {% endnote %}

  - If you need other people in your company to post tasks, give them full access to the main account. They don't need to be registered in Toloka. They can log in with [Yandex ID]({{ yandex-id }}). They will be able to manage your projects and check tasks, and you will manage the finances.

  - If you already have a Toloker account, you can quickly switch from it to the requester account. In this case, set up full access to the requester account for your Toloker account.

  ### View only

  If you don't want to give full access to your account, you can limit it to view only.

- Toloka support

  If you need help setting up pools or projects, give Toloka support temporary view-only access to your account to get recommendations. Access will be automatically revoked in 7 days. If necessary, you can revoke access earlier.
  
{% endlist %}

You can view the list of granted permissions on the **Profile** page in the **Account access** tab.

## How do I grant access to my account? {#multiple-access-grant}

{% list tabs %}

- Other requesters

  1. Open the [Profile]({{ profile }}) page.

  1. In the **Account access** tab, click **Add user**.

  1. Enter the case-sensitive [Yandex ID]({{ yandex-id }}).

  1. In the drop-down list, select **Full access** or **View only**.

  1. Click **Grant access**.

- Toloka support

  1. Open the [Profile]({{ profile }}) page.

  1. In the **Account access** tab, click **Grant access to Toloka Support**.

  1. Click **Grant access**.

{% endlist %}

## How to log in {#multiple-access-auth}

{% note alert "Restriction" %}

Depending on the type of access, some functions are restricted.

{% endnote %}

To log in to the requester account you were given access to:

1. Log in [Yandex ID]({{ yandex-id }}) with the username for which access was granted.

1. Open [**Toloka**]({{ toloka-index }}).

1. In the upper-right corner, click your account's avatar.

1. Choose the requester account you want to log in to.

## See also {#see-also}

- [{#T}](access.md)

{% include [contact-support](../_includes/contact-support.md) %}