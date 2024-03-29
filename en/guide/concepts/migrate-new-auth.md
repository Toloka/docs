# Migrating to new social authorization

If you have previously registered using an email address, you need to confirm it or connect another social account to continue using Toloka. You can connect a single social account or choose to connect them all to your Toloka profile and use any of them to sign in to Toloka.

## Connecting social accounts {#connect-account}

Log in using the **[Use Toloka legacy account](https://passport.toloka.ai/auth?origin=toloka_requesters&retpath=https%3A%2F%2Fplatform.toloka.ai%2Fauth%2Fsignup%3Frole%3DREQUESTER)** link at the new login page. Then follow the steps below to connect a new social account to your Toloka profile.

{% list tabs %}

- In the popup window

  1. Click the notification banner in the upper part of the Toloka platform. The popup window will appear:

      ![Update your authorization method](../_images/register/migration-1.png =320x)

  1. Choose **Connect** next to one of the social services to connect them.

  1. Follow the authorization steps for the selected service. Once you sign in to the selected service, you will be redirected back to Toloka.

- In the settings

  {% include [connect-social-account](../_includes/connect-social-account.md) %}

{% endlist %}

{% cut "For former Yandex ID clients" %}

{% list tabs %}

- In the popup window

  1. Click the notification banner in the upper part of the Toloka platform. The popup window will appear:

      ![Update your authorization method](../_images/register/migration.png =320x)

  1. Choose **Confirm** to connect your Yandex social account or **Connect** next to one of the other social services to connect them.

  1. Follow the authorization steps for the selected service. Once you sign in to the selected service, you will be redirected back to Toloka.

- In the settings

  {% include [connect-social-account-ru](../_includes/connect-social-account-ru.md) %}

{% endlist %}

{% endcut %}

Next time you [log in](https://platform.sandbox.toloka.ai/auth?role=REQUESTER), use the connected social account to do that.

{% include [register-social-account-issues](../_includes/register/social-account-issues.md) %}

## Logging in to existing account using social authorization {#login-old-auth}

You can log in to your existing Toloka account which you registered with Yandex ID using the new social authorization. For this, choose one of the following options when logging in:

- Choose Yandex social authorization and select the same account which you used when registered.

- Choose Google social authorization if you registered in Yandex ID using it.

- Choose Facebook social authorization if you registered in Yandex ID using it.

You can switch to the old authorization page using the **Use legacy Toloka account** link and [migrate](#connect-account) to the new authorization after that.

## Removing social accounts {#remove-auth}

{% include [remove-social-account](../_includes/remove-social-account.md) %}

## Updating API keys {#update-token}

After you migrate to the new authorization scheme, the existing OAuth tokens will continue to work until they expire. After that, you can issue new authentication keys.

New keys have no TTL and don't expire, you don't need to reissue them. One account can have up to 50 new API keys.

[Toloka API](https://toloka.ai/docs/api/api-reference/), [Toloka-Kit](../../toloka-kit/index.md), and [Toloka Java SDK](https://github.com/toloka/toloka-java-sdk/) support both old and new API keys.

Refer to the [Generating API keys](api-token.md) section to learn how to issue API keys.

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles-internal](../../../_includes/image-styles-internal.md) %}