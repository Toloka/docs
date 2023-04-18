# Issue bonuses

{% include [announce](../_includes/announce.md) %}

Issues bonuses to Tolokers.

The size of the bonus can range between $0.005 and $100 per Toloker at a time.

{% note alert "Restriction" %}

You can send a maximum of 10,000 requests of this kind per day. Refer to the [Rate limiting](rate-limiting.md) section for the complete list of the request limitations in Toloka API.

{% endnote %}

You can't use one request to pass multiple bonuses with the same price, name, and message to the same annotator. A response with the status `409` will be returned.

{% cut "Sample error with HTTP status code 409" %}

```json
{
  "user_id": {
    "code": "ENTITY_CONFLICT",
    "message": "It is not allowed to apply multiple bonuses with the same amount, title, message and comment to same user in single operation"
  }
}
```

{% endcut %}

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/user-bonuses
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/user-bonuses
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix. ||
**Content-Type** | Specifies the data format in the request body.

## Query parameters {#query-params}

Specified in the link after the question mark; separated by `&`.

#|
|| Parameter | Overview ||
|| **async_mode** | **boolean**

Mode for request processing:

- `true` — Asynchronous. Creates an asynchronous operation that runs in the background. The response contains information about the operation (start and completion time, status, number of bonuses).
- `false` — Synchronous. The response contains information about bonuses issued. Maximum of 100 bonuses per request.

The default value is `false`. ||
|| **assignment_id** | **string**

ID of the Toloker's response to the task a bonus is issued for. ||
|| **skip_invalid_items** | **boolean**

Validation parameters for JSON objects:

- `true` — Issue a bonus if the JSON object with bonus information passed validation. Otherwise, skip the bonus.
- `false` — Stop the operation and don't issue bonuses if at least one JSON object didn't pass validation.

The default value is `false`. ||
|| **operation_id** | **string**

Operation ID. Can be used for any method of request processing. ||
|#

## Request body {#body}

```json
{
  "user_id": "21c4f092ebad180cf56b9babe0ef9f19",
  "amount": 1.5,
  "assignment_id": "6946cefa-32af-4f62-b530-8d2c71fa2966",
  "private_comment": "Good job!",
  "public_title": {
    "EN": "Completed tasks"
  },
  "public_message": {
    "EN": "10 tasks successfully completed"
  },
  "without_message": false
}
```

#|
|| Parameter | Overview ||
|| **user_id** | **string**

Required parameter. Toloker ID. ||
|| **amount** | **float**

Required parameter. The dollar amount of the bonus. ||
|| **assignment_id** | **string**

ID of the Toloker's response to the task a bonus is issued for. ||
|| **private_comment** | **string**

Comments that are only visible to the requester. ||
|| **public_title** | **object**

The subject of the message for the Toloker. You can enter it in multiple languages (the message will be sent in the Toloker's language). Format: `"<language RU/EN/TR/ID/FR>": "<title text>"`. ||
|| **public_message** | **object**

The text of message for the Toloker. You can enter it in multiple languages (the message will be sent in the Toloker's language). Format: `"<language RU/EN/TR/ID/FR>": "<message text>"`. ||
|| **without_message** | **boolean**

Allows you not to send a bonus message to the Toloker. The default value is `false`.

To issue a bonus without a message, specify `null` for `public_title` and `public_message` and `true` for `without_message`. ||
|#

## Response {#response}

The response format depends on the value of `async_mode`.

{% list tabs %}

- Information about bonuses (async_mode=false)

    ```json
    {
      "items": {
        "0": {details of a bonus #0},
        "2": {details of a bonus #2},
        "<N>": {details of a bonus #N}
      },
      "validation_errors": {
        "1": {validation errors for a bonus #1},
        "3": {validation errors for a bonus #3},
        "<N>": {validation errors for a bonus #N}
      }
    }
    ```

    #|
    || Parameter | Overview ||
    || **items** | **string**

    Object with information about bonuses issued. ||
    || **validation_errors** | **string**

    An object with validation errors. Returned if the request has the parameter `skip_invalid_items=true`. ||
    |#

- Information about the operation (async_mode=true)

    ```json
    {
      "id": "26e130ad3652443a3dc5094791e48ef9",
      "type": "USER_BONUS.BATCH_CREATE",
      "status": "SUCCESS",
      "submitted": "2020-12-13T23:32:01",
      "started": "2020-12-13T23:33:00",
      "finished": "2020-12-13T23:34:12",
      "parameters": {
        "skip_invalid_items": true
      },
      "details": {
        "total_count": 2,
        "valid_count": 2,
        "not_valid_count": 0,
        "success_count": 2,
        "failed_count": 0
      }
    }
    ```

    #|
    || Parameter | Overview ||
    || **id** | **string**

    Operation ID. ||
    || **type** | **string**

    Type of operation: `USER_BONUS.BATCH_CREATE` — Issuing a bonus to multiple Tolokers. ||
    || **status** | **string**

    The status of the operation:

    - `PENDING` — Not started yet.
    - `RUNNING` — In progress.
    - `SUCCESS` — Completed successfully.
    - `FAIL` — Not completed. ||
    || **submitted** | **string**

    The UTC date and time the request was sent, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
    || **started** | **string**

    The UTC date and time the operation started, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
    || **finished** | **string**

    The UTC date and time the operation was completed, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
    || **parameters** | **object**

    Parameters of the operation in the request. ||
    || **skip_invalid_items** | **boolean**

    Validation parameters for JSON objects:

    - `true` — Issue a bonus if the JSON object with bonus information passed validation. Otherwise, skip the bonus.
    - `false` — Stop the operation and don't issue bonuses if at least one JSON object didn't pass validation.

    The default value is `false`. ||
    || **details** | **object**

    Information about the completed operation. ||
    || **details.total_count** | **integer**

    The number of bonuses in the request. ||
    || **details.valid_count** | **integer**

    The number of JSON objects with bonus information that passed validation. ||
    || **details.not_valid_count** | **integer**

    The number of invalid JSON objects with bonus information. ||
    || **details.success_count** | **integer**

    The number of bonuses issued. ||
    || **details.failed_count** | **integer**

    The number of bonuses that weren't issued. ||
    |#

{% endlist %}

{% include [contact-support](../../guide/_includes/contact-support.md) %}