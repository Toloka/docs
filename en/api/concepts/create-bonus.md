# Issue rewards

Issues rewards to Tolokers.

The reward amount can be from $0.001 to $100 per Toloker per time.

{% note alert %}

You can send a maximum of 10,000 requests of this kind per day.

{% endnote %}


## Request {#request}

{% list tabs %}

- Production version

  ```bash
  POST https://toloka.yandex.com/api/v1/user-bonuses
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```

- Sandbox

  ```bash
  POST https://sandbox.toloka.yandex.com/api/v1/user-bonuses
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

- `true` — Asynchronous. Creates an asynchronous operation that runs in the background. The response contains information about the operation (start and completion time, status, number of rewards).
- `false` — Synchronous. The response contains information about rewards issued. Maximum of 100 rewards per request.

The default value is `false`. ||
|| **assignment_id** | **string**

ID of the Toloker's response to the task a reward is issued for. ||
|| **skip_invalid_items** | **boolean**

Validation parameters for JSON objects:

- `true` — Issue a reward if the JSON object with reward information passed validation. Otherwise, skip the reward.
- `false` — Stop the operation and don't issue rewards if at least one JSON object didn't pass validation.

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

Required parameter. The dollar amount of the reward. ||
|| **assignment_id** | **string**

ID of the Toloker's response to the task a reward is issued for. ||
|| **private_comment** | **string**

Comments that are only visible to the requester. ||
|| **public_title** | **object**

The subject of the message for the Toloker. You can enter it in multiple languages (the message will be sent in the Toloker's language). Format: "`"<language RU/EN/TR/ID/FR>": "<title text>"`. ||
|| **public_message** | **object**

Message text for the Toloker. You can enter it in multiple languages (the message will be sent in the Toloker's language). Format: `"<language RU/EN/TR/ID/FR>": "<message text>"`. ||
|| **without_message** | **boolean**

Allows you not to send a reward message to the Toloker. The default value is `false`.

To issue a reward without a message, specify `null` for `public_title` and `public_message` and `true` for `without_message`. ||
|#

## Response {#response}

The response format depends on the value of `async_mode`.

{% list tabs %}

- Information about rewards (async_mode=false)

  ```json
  {
    "items": {
      "0": {details of a reward #0},
      "2": {details of a reward #2},
      "<N>": {details of a reward #N}
     },
    "validation_errors": {
      "1": {validation errors for a reward #1},
      "3": {validation errors for a reward #3},
      "<N>": {validation errors for a reward #N}
     }
  }
  ```

  #|
  || Parameter | Overview ||
  || **items** | **string**

  Object with information about rewards issued. ||
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

  Type of operation: `USER_BONUS.BATCH_CREATE` — Issuing a reward to multiple Tolokers. ||
  || **status** | **string**

  The status of the operation:

  - `PENDING` — Not started yet.
  - `RUNNING` — In progress.
  - `SUCCESS` — Completed successfully.
  - `FAIL` — Not completed. ||
  || **submitted** | **string**

  The UTC date and time the request was sent, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
  || **started** | **string**

  The UTC date and time the operation started, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
  || **finished** | **string**

  The UTC date and time the operation was completed, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
  || **parameters** | **object**

  Parameters of the operation in the request. ||
  || **skip_invalid_items** | **boolean**

  Validation parameters for JSON objects:

  - `true` — Issue a reward if the JSON object with reward information passed validation. Otherwise, skip the reward.
  - `false` — Stop the operation and don't issue rewards if at least one JSON object didn't pass validation.

  The default value is `false`. ||
  || **details** | **object**

  Information about the completed operation. ||
  || **details.total_count** | **integer**

  The number of rewards in the request. ||
  || **details.valid_count** | **integer**

  The number of JSON objects with reward information that passed validation. ||
  || **details.not_valid_count** | **integer**

  The number of invalid JSON objects with reward information. ||
  || **details.success_count** | **integer**

  The number of rewards issued. ||
  || **details.failed_count** | **integer**

  The number of rewards that weren't issued. ||
  |#

{% endlist %}