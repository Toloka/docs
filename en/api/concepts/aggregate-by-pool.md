# Aggregate responses in a pool

{% include [announce](../_includes/announce.md) %}

Starts aggregating responses to all completed tasks in the pool.

{% note alert "Restriction" %}

You can send a maximum of 5 requests of this kind per minute, 30 requests per hour, and 200 requests per day. Refer to the [Rate limiting](rate-limiting.md) section for the complete list of the request limitations in Toloka API.

{% endnote %}

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/aggregated-solutions/aggregate-by-pool
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/aggregated-solutions/aggregate-by-pool
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix. ||
**Content-Type** | Specifies the data format in the request body.

## Request body {#body}

```json
{
  "pool_id": "283",
  "type": "WEIGHTED_DYNAMIC_OVERLAP",
  "answer_weight_skill_id": "1289",
  "fields": [
    {
      "name": "result"
    }
  ]
}
```

#|
|| Parameter | Overview ||
|| **pool_id** | **string**

Pool ID. ||
|| **type** | **string**

Result aggregation method:

- `WEIGHTED_DYNAMIC_OVERLAP` — Aggregation of responses in a pool based on the Toloker's skill.
- `DAWID_SKENE` — Aggregation of responses in a pool without dynamic overlap. The `answer_weight_skill_id` key for this aggregation type is ignored. ||
|| **answer_weight_skill_id** | **string**

A skill that determines the weight of the Toloker's response.

Required if the `WEIGHTED_DYNAMIC_OVERLAP` aggregation type is selected. ||
|| **fields** | **object**

[Output data fields](../../guide/concepts/result-aggregation.md) to use for aggregating responses. For best results, each of these fields must have a limited number of response options.

If the `DAWID_SKENE` aggregation type is selected, you can only specify one value. ||
|| **fields.name** | **string**

The output data field name. ||
|#

## Response {#response}

Contains operation details: Check the [operation status](operations.md). When it is completed [get the aggregation results](get-aggregated-result.md).

```json
{
  "id": "fadfe3jk-fdafue2-fda32890-fdafdi23",
  "type": "SOLUTION.AGGREGATE",
  "status": "PEDNDING",
  "submitted": "2018-22-10T14:18:35",
  "progress" : 0,
  "parameters": {
    "pool_id": "283"
  }
}
```

#|
|| Parameter | Overview ||
|| **id** | **string**

Operation ID. ||
|| **type** | **string**

Operation type:

- `POOL.OPEN` — Opening a pool.
- `POOL.CLOSE` — Closing a pool.
- `PROJECT.ARCHIVE` — Archiving a project.
- `POOL.ARCHIVE` — Archiving a pool.
- `SOLUTION.AGGREGATE` — Aggregating responses.
- `TASK_SUITE.BATCH_CREATE` — Creating multiple task suites. ||
|| **status** | **string**

The status of the operation:

- `PENDING` — Not started yet.
- `RUNNING` — In progress.
- `SUCCESS` — Completed successfully.
- `FAIL` — Not completed. ||
|| **submitted** | **string**

The UTC date and time the request was sent, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **progress** | **integer**

The percentage of the operation completed. ||
|| **parameters** | **object**

Parameters of the operation in the request. ||
|#

{% include [contact-support](../../guide/_includes/contact-support.md) %}