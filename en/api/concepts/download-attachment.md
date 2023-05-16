# Download file

{% include [announce](../_includes/announce.md) %}

Downloads a file attached to a task response.

## Request {#request}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#get-/attachments/-id-/download):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

    ```no-highlight
    GET https://toloka.dev/api/v1/attachments/<file_id>/download
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```no-highlight
    GET https://sandbox.toloka.dev/api/v1/attachments/<file_id>/download
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**file_id** | File ID.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

## Response {#response}

The file is saved to your computer.

{% include [contact-support](../../guide/_includes/contact-support.md) %}