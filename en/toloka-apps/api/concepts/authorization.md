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

- Go to [Profile → Integrations](https://platform.toloka.ai/requester/profile/integration):

![List of tokens](../../../guide/_images/sso/token-list.png =700x)

Refer to the [Generating API tokens](../../../guide/concepts/api-token.md) section to learn how to issue OAuth tokens.

{% include [contact-support](../../_includes/contact-support.md) %}

{% include [image-styles-internal](../../../../_includes/image-styles-internal.md) %}