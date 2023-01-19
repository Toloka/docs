# Generating API tokens

After you login to the platform with [single sign-on](./microsoft-authentication.md) (SSO) authentication method, you can generate new tokens. You can use them for API requests or for the integration applications. The previously generated tokens will continue to work, but will be deprecated with time.

{% note tip %}

You can generate up to **50** tokens. We recommend that you generate and use a separate token for each of the integrations you have.

{% endnote %}

## Generating tokens

1. Go to **Profile → Integrations** or follow [this link](https://platform.toloka.ai/requester/profile/integration). Click **![Plus sign](../_images/plus-sign.svg) Add token**:

    [![Add token](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/sso/add-token.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/sso/add-token.png)

1. Enter a unique name or description for the token. Uniqueness is not required, but it will allow you to distinguish this token in case you have several ones. Click **Generate**:

    [![Enter token name](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/sso/token-name.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/sso/token-name.png)

1. A new token will be generated. Click **Copy and close** to copy the token into the clipboard and close the dialog window:

    [![Copy and close](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/sso/copy-token.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/sso/copy-token.png)

    {% note warning %}

    You will not be able to view or copy the token after you close this window. This is done for security reasons. If you lose it, you will need to delete it and generate a new one.

    {% endnote %}

1. Your newly generated token will be added to the list of the tokens associated with your account:

    [![List of tokens](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/sso/token-list.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/sso/token-list.png)

    Here you can view the details about your generated tokens: their names, first characters, creation date, and usage information.

    Click ![Delete button](../_images/delete-token.svg) in the token upper-right area to delete it.

## Testing tokens

To test the created token, use the following shell command:

```bash
curl -X GET 'https://toloka.dev/api/v1/requester' -H 'Authorization: OAuth YOUR_TOKEN'
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

Now you can use the created API token to send other API requests: get the list of the existing [projects](../../api/concepts/get-prj-list.md), [pools](../../api/concepts/get-pool-list.md), [upload tasks](../../api/concepts/upload-tasks.md), and other requests.

## Further reading

- [Toloka API](../../api/index.md)

{% include [image-styles](../../../_includes/image-styles.md) %}