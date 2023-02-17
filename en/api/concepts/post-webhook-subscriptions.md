# Send a test notification

{% include [announce](../_includes/announce.md) %}

Sends a test notification to the URL specified in the subscription.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/webhook-subscriptions/<subscription_id>/test
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/webhook-subscriptions/<subscription_id>/test
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**subscription_id** | ID of the subscription.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

## Example of the notification body {#body}

```json
{
  "uuid": "uuid",
  "event_time": "2020-02-14T12:22:58",
  "project_id": "projectId",
  "pool_id": "poolId",
  "type": "TEST_EVENT"
}
```

#|
|| Parameter | Overview ||
|| **uuid** | **string \| required**

Unique event number generated for each new request. ||
|| **event_time** | **string \| required**

Time when the event occurs. ||
|| **project_id** | **string \| required**

ID of the project that the pool was created for. ||
|| **pool_id** | **string \| required**

ID of the pool that the subscription was created for. ||
|| **type** | **string \| required**

Notification type.

Takes the `TEST_EVENT` value indicating a test notification. ||
|#

## Response {#response}

If the request is successful, the server returns the "200 Ok" or "404 Not Found" HTTP operation status.

```json
{
  "success": true,
  "responseReceivedAt": "2020-02-14T12:22:58",
  "errorType": "WRONG_STATUS_CODE",
  "originalStatusCode": 1,
  "uuids": ["uuid1", ..."uuid5"]
}
```

#|
|| Parameter | Overview ||
|| **success** | **boolean**

Request execution status.

`True` or `False`. ||
|| **responseReceivedAt** | **string**

The UTC date and time when the subscription was created, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **errorType** | **string**

Error type.

Acceptable values:

- `WRONG_STATUS_CODE` — Invalid status code.
- `TOO_MANY_CONNECTIONS` — Connection limit exceeded.
- `REQUEST_TIMEOUT` — Request timeout.
- `CONNECTION_ERROR` — Connection error.
- `INTERNAL_ERROR` — Internal error.
- `UNKNOWN` — Unknown error. ||
|| **originalStatusCode** | **int**

Status code of the response from the subscription URL. ||
|| **uuids** | **array of strings**

Array of unique event numbers. ||
|#

{% include [contact-support](../../guide/_includes/contact-support.md) %}