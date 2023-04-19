# Checking completed tasks

{% include [announce](../_includes/announce.md) %}

You can manually check tasks and reject responses of poor quality. To accept or reject received responses, change the status of the task suite using a PATCH request to the `/assignments/<task_suite_assignment_ID>` resource:

- Accept responses: change `SUBMITTED` to `ACCEPTED`.
- Reject responses: change `SUBMITTED` to `REJECTED`.
- Change a rejection decision: change `REJECTED` to `ACCEPTED`.

To resend rejected tasks to be completed by other Tolokers, add a quality control rule to the pool (see [Recompletion of assignments](restore-task-overlap.md)).

## Request {#request}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#get-/assignments/-id-):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

    ```bash
    PATCH https://toloka.dev/api/v1/assignments/<task_suite_assignment_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    PATCH https://sandbox.toloka.dev/api/v1/assignments/<task_suite_assignment_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**task_suite_assignment_id** | ID of the task suite assignment.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.
**Content-Type** | Specifies the data format in the request body.

## Request body {#body}

```json
{
  "status": "ACCEPTED",
  "public_comment": "Well done!"
}
```

#|
|| Parameter | Overview ||
|| **status** | **string**

Status of an assigned task suite. If you need to list multiple statuses, separate them with commas:

- `ACTIVE` — Being completed by a Toloker.
- `SUBMITTED` — Completed but not checked.
- `ACCEPTED` — Accepted by the requester.
- `REJECTED` — Rejected by the requester.
- `SKIPPED` — Skipped by the Toloker.
- `EXPIRED` — The time for completing the tasks expired.
||
|| **public_comment** | **string**

A comment for the Toloker.

Maximum length: 2048 characters. ||
|#

## Response {#response}

The response contains the changed values of fields:

```json
{
  "status": "ACCEPTED",
  "public_comment": "Well done!",
  "bonus_ids": [10]
}
```

#|
|| Parameter | Overview ||
|| **status** | **string**

Status of an assigned task suite. If you need to list multiple statuses, separate them with commas:

- `ACTIVE` — Being completed by a Toloker.
- `SUBMITTED` — Completed but not checked.
- `ACCEPTED` — Accepted by the requester.
- `REJECTED` — Rejected by the requester.
- `SKIPPED` — Skipped by the Toloker.
- `EXPIRED` — The time for completing the tasks expired.
||
|| **public_comment** | **string**

A comment for the Toloker.

Maximum length: 2048 characters. ||
|| **bonus_ids[]** | **array of strings**

IDs of bonuses issued. ||
|#

## See also {#see-also}

- [{#T}](../../guide/concepts/accept.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}