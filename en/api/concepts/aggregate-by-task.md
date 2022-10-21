# Aggregate responses to a single task

{% include [announce](../_includes/announce.md) %}

Starts aggregating responses to a single task.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/aggregated-solutions/aggregate-by-task
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/aggregated-solutions/aggregate-by-task
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.
**Content-Type** | Specifies the data format in the request body.

## Request body {#body}

```json
{
  "task_id": "afd1234d-12314a-cfd1424d-31214b",
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
|| **task_id** | **string**

Task ID. ||
|| **pool_id** | **string**
Pool ID. ||
|| **type** | **string**

Aggregation type.

- `WEIGHTED_DYNAMIC_OVERLAP` — Aggregation of responses in a pool with dynamic overlap (also known as incremental relabeling or IRL).
- `DAWID_SKENE` — Aggregation of responses in a pool without dynamic overlap. The `answer_weight_skill_id` key for this aggregation type is ignored. ||
|| **answer_weight_skill_id** | **string**

A skill that determines the weight of the Toloker's response. ||
|| **fields** | **object**

[Output data fields](../../guide/concepts/result-aggregation.md) to use for aggregating responses. For best results, each of these fields must have a limited number of response options. ||
|| **fields.name** | **string**

The output data field name. ||
|#

## Response {#response}

Contains the aggregated task response.

```json
{
  "confidence": 0.937152,
  "output_values": {
    "result": "OK"
  },
  "pool_id": "283",
  "task_id": "afd1234d-12314a-cfd1424d-31214b"
}
```

#|
|| Parameter | Overview ||
|| **confidence** | **integer**

Confidence in the aggregate response. ||
|| **output_values** | **object**

Output data fields and aggregate response. ||
|| **pool_id** | **string**
Pool ID. ||
|| **task_id** | **string**

Task ID. ||
|#