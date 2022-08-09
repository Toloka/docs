# Download file

{% include [announce](../_includes/announce.md) %}

Downloads a file attached to a task response.

## Request {#request}

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