# Archive a project

{% include [announce](../_includes/announce.md) %}

Sends the project to the archive.

If a project isn't being used, you can send it to the archive. To do this, all the pools in the project must be [archived](archive-pool.md). You can get the project ID from the [list of projects](get-prj-list.md).

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/projects/<project_id>/archive
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/projects/<project_id>/archive
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**project_id** | Project ID.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

## Response {#response}

The response contains information about the results of the operation.

```json
{
  "id" : "57068577e4b0bf7b07a0256f",
  "type" : "PROJECT.ARCHIVE",
  "status" : "SUCCESS",
  "submitted" : "2016-04-07T16:06:15.902",
  "started" : "2016-04-07T16:06:15.902",
  "finished" : "2016-04-07T16:06:15.902",
  "progress" : 100,
  "parameters" : {
    "project_id" : "1"
  }
}
```

#|
|| Parameter | Overview ||
|| **id** | **string**

Operation ID. ||
|| **type** | **string**

Operation type:

- `PROJECT.ARCHIVE` — Archiving a project. ||
|| **status** | **string**

The status of the operation:

- `PENDING` — Not started yet.
- `RUNNING` — In progress.
- `SUCCESS` — Completed successfully.
- `FAIL` — Not completed. ||
|| **submitted** | **string**

The UTC date and time the request was sent, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **started** | **string**

The UTC date and time the operation started, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **finished** | **string**

The UTC date and time the operation was completed, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **progress** | **float**

The percentage of the operation completed. ||
|| **parameters.project_id** | **string**

Project ID. ||
|#

You can check the operation status by sending requests to the `/operations` resource. For more information, see [Overview](operations.md).