# Migrating to new social authorization

If you have previously registered using Yandex ID, you need to confirm it or connect another social account to continue using Toloka. You can connect a single social account or choose to connect them all to your Toloka profile and use any of them to sign in to Toloka.

## Connecting social accounts {#connect-account}

Follow the steps below to connect a new social account to your Toloka profile.

{% list tabs %}

- In the popup window

  1. Click the notification banner in the upper part of the Toloka platform. The popup window will appear:

      ![Update your authorization method](../_images/register/migration.png =320x)

  1. Choose **Confirm** to connect your Yandex social account or **Connect** next to one of the other social services to connect them.

  1. Follow the authorization steps for the selected service. Once you sign in to the selected service, you will be redirected back to Toloka.

- In the settings

  1. Go to the **Profile** tab (or click [this link](https://platform.toloka.ai/requester/profile)). Scroll down to the **Authorization methods** section:

      ![Update your authorization method](../_images/register/migration-settings.png =433x)

  1. Choose **Confirm** to connect your Yandex social account or **Connect** next to one of the other social services to connect them.

  1. Follow the authorization steps for the selected service. Once you sign in to the selected service, you will be redirected back to Toloka.

{% endlist %}

Next time you log in, use the connected social account to do that.

{% note info %}

Please [contact our support team](../troubleshooting/support.md) if you have any issues with social accounts connection.

{% endnote %}

## Logging in to existing account using social authorization {#login-old-auth}

You can log in to your existing Toloka account which you registered with Yandex ID using the new social authorization. For this, choose one of the following options when logging in:

- Choose Yandex social authorization and select the same account which you used when registered.

- Choose Google social authorization if you registered in Yandex ID using it.

- Choose Facebook social authorization if you registered in Yandex ID using it.

You can switch to the old authorization page using the **Use legacy Toloka account** link and [migrate](#connect-account) to the new authorization after that.

## Removing social accounts {#remove-auth}

To remove a social account from the list of the ones associated with your Toloka profile:

1. Go to the **Profile** tab (or click [this link](https://platform.toloka.ai/requester/profile)). Scroll down to the **Authorization methods** section:

    ![Remove social account](../_images/register/remove-social-account.png =433x)

1. Choose **Disconnect** next to the social service you want to remove.

The social service will be no longer associated with your Toloka account and you won't be able to use it to sign in.

{% note info %}

You must have at least one social account connected to your Toloka profile. For example, if you want to use Google account instead of GitHub, first connect the new account (GitHub) before you can remove the old one (Google).

{% endnote %}

## Updating OAuth tokens {#update-token}

After you migrate to the new authorization scheme, the existing OAuth tokens will continue to work until they expire. After that, you can issue new authentication tokens.

New tokens have no TTL and don't expire, you don't need to reissue them. One account can have up to 50 new OAuth tokens.

[Toloka API](../../api/index.md), [Toloka-Kit](../../toloka-kit/index.md), and [Toloka Java SDK](https://github.com/toloka/toloka-java-sdk/) support both old and new OAuth tokens.

Refer to the [Generating API tokens](api-token.md) section to learn how to issue OAuth tokens.

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles-internal](../../../_includes/image-styles-internal.md) %}
