# API migration

The Toloka API is migrating to the `toloka.dev` domain. Access to the Toloka API is about to change. The current API domain (`toloka.yandex.com`) works in deprecated mode and will be disabled **since August 1, 2023**. You need to update your applications to use the new domain.

{% note alert %}

If you do not change the domain, your requests to the Toloka API will end up with errors starting August 1, 2023.

{% endnote %}

{% cut "I'm currently using the Toloka API directly. How do I change the requests?" %}

You need to change the URL to which you send the requests. Replace the `toloka.yandex.com` domain part in the URL with `toloka.dev`. All the other request parameters remain unchanged.

For example, a cURL request to the Toloka API which gets the requester information should look like this:

```bash
curl -X GET 'https://toloka.dev/api/v1/requester' \
     -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here'
```

{% endcut %}

{% include [faq-toloka-kit-new-domain](../guide/_includes/faq/api/toloka-kit-new-domain.md) %}

{% include [faq-java-sdk-new-domain](../guide/_includes/faq/api/java-sdk-new-domain.md) %}

{% include [faq-reissue-token](../guide/_includes/faq/api/reissue-token.md) %}

{% cut "I have a question not answered here. Where can I ask it?" %}

If you can't find an answer to your question here, feel free to [contact Toloka Customer Care team](../guide/troubleshooting/support.md).

{% endcut %}