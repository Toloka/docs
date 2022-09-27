# Accessing the API

To send an authorization request to the API, you need an OAuth token.

**Query example**

```http
GET /api/app/v0/apps
Host: https://toloka.yandex.ru
Authorization: OAuth <OAuth token>
```

## Getting an OAuth token

- [Register](https://toloka.ai/docs/guide/concepts/access.html) in Toloka.

- Get an OAuth token in the [requester interface](https://platform.toloka.ai/requester/profile/integration).

<a target="_blank" href="https://yastatic.net/s3/doc-binary/src/support/toloka/en/api/get-oauth-token.png"><img src="https://yastatic.net/s3/doc-binary/src/support/toloka/en/api/get-oauth-token.png" alt="Accessing the API" style="border:1px solid #ccc;border-radius:6px;cursor:zoom-in;width:700px;" /></a>

{% include [contact-support](../../_includes/contact-support.md) %}