# Open a pool

Opens a pool.

Training tasks will be available to Tolokers only if a training pool is open.

An operation is created when you send a request. To track the progress of the operation, send a request to the `/operations` resource.

## Request {#request}

{% list tabs %}

- Production version

  ```json
  POST https://toloka.yandex.com/api/v1/pools/<pool_id>/open
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```json
  POST https://sandbox.toloka.yandex.com/api/v1/pools/<pool_id>/open
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | ----- 
**pool_id** | Pool ID.


## Headers {#headers}

Title | Overview
----- | ----- 
**Authorization** | A token for account authorization. Add OAuth as a prefix.


## Response {#response}

{% note info %}

If the pool is already open, an empty response with status 204 is returned.

If the pool cannot be opened, a response is returned with an error description and the status 409.

{% endnote %}


```json
{
  "id": "fadfe3jk-fdafue2-fda32890-fdafdi23",
  "type": "POOL.OPEN",
  "status": "PENDING",
  "submitted": "2015-22-12T14:18:35",
  "started" : "2016-04-07T16:06:15.902",
  "finished" : "2016-04-07T16:06:15.902",
  "progress" : 100,
  "parameters": {
    "pool_id": "21"
  }
}
```

#|
|| Parameter | Overview ||
|| **id** | **string**

User ID. ||
|| **type** | **string**

Type of operation: `POOL.OPEN` — Opening a pool. ||
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
|| **progress** | **integer**
The percentage of the operation completed. ||
|| **parameters.pool_id** | **string**
Pool ID. ||
|#

