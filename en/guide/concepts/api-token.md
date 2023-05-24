# Generating API tokens

After you login to the platform using [social authorization](access.md#social-auth) or [single sign-on](../sso/authentication.md) (SSO) authentication method, you can generate new tokens. You can use them for API requests or for the integration applications. The previously generated tokens will continue to work, but will be deprecated with time.

{% note info %}

If your company uses SSO authentication method, each SSO user can generate their own tokens.

{% endnote %}

## Generating tokens

1. Go to **Profile → Integrations** (or click [this link](https://platform.toloka.ai/requester/profile/integration)). Click **![Plus sign](../_images/plus-sign.svg) Generate token**:

    ![Generate token](../_images/sso/add-token.png =700x)

1. Enter a unique name or description for the token. Uniqueness is not required, but it will allow you to distinguish this token in case you have several ones. Click **Generate**:

    ![Enter token name](../_images/sso/token-name.png =700x)

1. A new token will be generated. Click **Copy and close** to copy the token into the clipboard and close the dialog window:

    ![Copy and close](../_images/sso/copy-token.png =700x)

    {% note warning %}

    You will not be able to view or copy the token after you close this window. This is done for security reasons. If you lose it, you will need to delete it and generate a new one.

    {% endnote %}

1. Your newly generated token will be added to the list of the tokens associated with your account:

    ![List of tokens](../_images/sso/token-list.png =700x)

    Here you can view the details about your generated tokens: their names, first characters, creation date, and usage information.

    Click ![Delete button](../_images/delete-token.svg) in the token upper-right corner to delete it.

{% note info %}

You can generate up to **50** tokens.

{% endnote %}

## Testing tokens

To test the created token, use the following shell command:

```bash
curl -X GET 'https://toloka.dev/api/v1/requester' -H 'Authorization: ApiKey YOUR_TOKEN'
```

Replace the `YOUR_TOKEN` substring with the API token that you received and copied at the previous steps.

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

Now you can use the created API token to send other API requests: get the list of the existing [projects](https://toloka.ai/docs/api/api-reference/#get-/projects), [pools](https://toloka.ai/docs/api/api-reference/#get-/pools), [upload tasks](https://toloka.ai/docs/api/api-reference/#post-/tasks), and other requests.

## Further reading

- [Toloka API](https://toloka.ai/docs/api/api-reference/)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles-internal](../../../_includes/image-styles-internal.md) %}