# Generating API keys

After you login to the platform using [social authorization](access.md#social-auth) or [single sign-on](../sso/authentication.md) (SSO) authentication method, you can generate new keys.

{% note info %}

We recommend that you generate new keys as the previously generated tokens will be deprecated with time.

{% endnote %}

You can use the generated keys for API requests or for the integration applications.

{% note info %}

If your company uses SSO authentication method, each SSO user can generate their own keys.

{% endnote %}

## Generating keys

1. Go to [Profile → Integrations](https://platform.toloka.ai/requester/profile/integration). Click **![Plus sign](../_images/plus-sign.svg) Generate token**:

    ![Generate key](../_images/sso/add-token.png =700x)

1. Enter a unique name or description for the key. Uniqueness is not required, but it will allow you to distinguish this key in case you have several ones. Click **Generate**:

    ![Enter key name](../_images/sso/token-name.png =700x)

1. A new key will be generated. Click **Copy and close** to copy the key into the clipboard and close the dialog window:

    ![Copy and close](../_images/sso/copy-token.png =700x)

    {% note warning %}

    You will not be able to view or copy the key after you close this window. This is done for security reasons. If you lose it, you will need to delete it and generate a new one.

    {% endnote %}

1. Your newly generated key will be added to the list of the keys associated with your account:

    ![List of keys](../_images/sso/token-list.png =700x)

    Here you can view the details about your generated keys: their names, first characters, creation date, and usage information.

    Click ![Delete button](../_images/delete-token.svg) in the key upper-right corner to delete it.

{% note info %}

You can generate up to **50** keys.

{% endnote %}

## Testing keys

To test the created key, use the following shell command:

```bash
curl -X GET 'https://toloka.dev/api/v1/requester' -H 'Authorization: ApiKey PlaceYourRealApiKey_Here'
```

Replace the `PlaceYourRealApiKey_Here` substring with the API key that you received and copied at the previous steps.

If you entered a correct value, you will receive a response like this with the `200` status code and basic information about your account:

```json
{
  "balance": 100,
  "company": {
    "id": "123",
    "superintendent_id": "eaf25678e128e14dea651d8c32471f21"
  },
  "id": "eaf25678e128e14dea651d8c32471f21",
  "public_name": {
    "EN": "John Smith"
  }
}
```

Now you can use the created API key to send other API requests: get the list of the existing [projects](https://toloka.ai/docs/api/api-reference/#get-/projects), [pools](https://toloka.ai/docs/api/api-reference/#get-/pools), [upload tasks](https://toloka.ai/docs/api/api-reference/#post-/tasks), and other requests.

{% note info %}

The new API keys work when you send requests to the `toloka.dev` domain and require [Toloka Java SDK](https://github.com/Toloka/toloka-java-sdk/releases) version 0.0.6 or later and [Toloka-Kit](https://github.com/Toloka/toloka-kit/releases) version 1.2.0 or later.

{% endnote %}

## Troubleshooting

{% include [faq-toloka-kit-new-token](../_includes/faq/api/toloka-kit-new-token.md) %}

{% include [faq-java-sdk-new-token](../_includes/faq/api/java-sdk-new-token.md) %}

{% include [faq-reissue-token](../_includes/faq/api/reissue-token.md) %}

## Further reading

- [Toloka API](https://toloka.ai/docs/api/api-reference/)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles-internal](../../../_includes/image-styles-internal.md) %}