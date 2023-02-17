# Accessing the API

{% include [announce](../_includes/announce.md) %}

All requests to the Toloka API must specify the resource URL and the OAuth token.

#### Query example

```bash
GET https://sandbox.toloka.dev/api/v1/assignments?pool_id=12345
Authorization: OAuth <OAuth token>
```

## Resource URL {#urls}

- For requests to the sandbox: `https://sandbox.toloka.dev/api/v1/<the path to the resource>`.

- For requests to the production version: `https://toloka.dev/api/v1/<the path to the resource>`.

## Getting an OAuth token {#token}

Working with the Toloka API requires an OAuth access token. [Register](../../guide/concepts/access.md) in Toloka and get an OAuth token in the requester interface:

- In the sandbox for debugging tasks: [https://sandbox.toloka.yandex.com/requester/profile/integration](https://sandbox.toloka.yandex.com/requester/profile/integration).

- In the production version of Toloka: [https://platform.toloka.ai/requester/profile/integration](https://platform.toloka.ai/requester/profile/integration).

[![Accessing the API](https://yastatic.net/s3/doc-binary/src/support/toloka/en/api/get-oauth-token.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/api/get-oauth-token.png)

{% include [image-styles](../../../_includes/image-styles.md) %}

## Troubleshooting {#troubleshooting}

{% include [troubleshooting-token-expired](../../guide/_includes/troubleshooting/api/token-expired.md) %}

{% include [troubleshooting-access-denied](../../guide/_includes/troubleshooting/api/access-denied.md) %}

{% include [contact-support](../../guide/_includes/contact-support.md) %}