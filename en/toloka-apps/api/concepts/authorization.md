{% include [image-styles](../../../../_includes/image-styles.md) %}

# Accessing the API

To send an authorization request to the API, you need an OAuth token.

**Query example**

```http
GET /api/app/v0/apps
Host: https://toloka.dev
Authorization: OAuth <OAuth token>
```

## Getting an OAuth token

- [Register](../../../guide/concepts/access.md) in Toloka.

- Get an OAuth token in the [requester interface](https://platform.toloka.ai/requester/profile/integration).

[![Accessing the API](https://yastatic.net/s3/doc-binary/src/support/toloka/en/api/get-oauth-token.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/api/get-oauth-token.png)

{% include [contact-support](../../_includes/contact-support.md) %}