# Get file metadata

{% include [announce](../_includes/announce.md) %}

Gets the properties of a file attached to a task response.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/attachments/<file_id>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/attachments/<file_id>
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

Information about a file.

```json
{
  "id" : "0983459b-e26f-42f3-a5fd-6e3feee913e7",
  "attachment_type" : "ASSIGNMENT_ATTACHMENT",
  "name" : "ExampleAttachment.txt",
  "details" : {
    "user_id" : "ae1d5431cfc59e25b4abbbe75666d59b",
    "assignment_id" : "5241f238-6640-43e4-80bb-3283893cd221",
    "pool_id" : "154"
  },
  "created" : "2016-05-25T16:14:27.748",
  "media_type" : "application/octet-stream"
}
```

#|
|| Parameter | Overview ||
|| **id** | **string**

File ID. ||
|| **attachment_type** | **string**

Attachment type. Currently the key can have only one value — `ASSIGNMENT_ATTACHMENT`. ||
|| **name** | **string**

File name. ||
|| **details** | **object**

Infomation about the pool, the task, and the Toloker who uploaded the file. ||
|| **details.user_id** | **string**

ID of the Toloker who uploaded the file. ||
|| **details.assignment_id** | **string**

ID of the task suite assignment to a Toloker. ||
|| **details.pool_id** | **string**

Pool ID. ||
|| **created** | **string**

The date when the file was uploaded to Toloka. ||
|| **media_type** | **string**

MIME type of the data. ||
|#