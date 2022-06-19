# Get responses

Gets responses for all the pool's task suites.

## Request {#request}

{% list tabs %}

- Production version

	```json
	GET https://toloka.yandex.com/api/v1/assignments
	Authorization: OAuth <OAuth token>
	```

- Sandbox

	```json
	GET https://sandbox.toloka.yandex.com/api/v1/assignments
	Authorization: OAuth <OAuth token>
	```

{% endlist %}

## Headers {#headers}

#|
|| Title | Overview ||
|| **Authorization** | A token for account authorization. Add OAuth as a prefix. ||
|#

## Query parameters {#query-params}

Specified in the link after the question mark; separated by `&`.

#|
|| Parameter | Overview ||
|| **status** | **string**

Status of an assigned task suite. If you need to list multiple statuses, separate them with commas:

- `ACTIVE` — Being completed by a Toloker.
    
- `SUBMITTED` — Completed but not checked.
    
- `ACCEPTED` — Accepted by the requester.
    
- `REJECTED` — Rejected by the requester.
    
- `SKIPPED` — Skipped by the Toloker.
    
- `EXPIRED` — The time for completing the tasks expired. ||
|| **task_id** | **string**

You must specify either `task_id`,`pool_id`, or `task_suite_id`.

The task ID in the suites that were generated automatically using "smart mixing". You will get responses for task suites that contain the specified task. ||
|| **task_suite_id** | **string**

You must specify either `task_id`,`pool_id`, or `task_suite_id`.

ID of a task suite. ||
|| **pool_id** | **string**

You must specify either `task_id`,`pool_id`, or `task_suite_id`.

Pool ID. ||
|| **user_id** | **string**

Toloker ID. ||
|| **sort** | **string**

Parameters to sort by:

- `id` — ID of the task suite assignment.
    
- `created` — The date the task suite was assigned.
    
- `submitted` — The date the task suite was completed.
    
- `skipped` — The date the task suite was skipped.
    
- `expired` — The date the task suite expired.
    
- `accepted` — The date the task suite was accepted by the requester.
    
- `rejected` — The date the task suite was rejected by the requester.
    

{% note info %}

All dates use the ISO 8601 format YYYY-MM-DDThh:mm:ss[.sss].

{% endnote %}


To learn how to configure sorting, see [Sorting the list of objects](sorting.md). ||
|| **Standard query parameters** | 
* [limit](./standard-query-parameters.md#limit).
* [id_gt](./standard-query-parameters.md#id_gt), [id_gte](./standard-query-parameters.md#id_gte), [id_lt](./standard-query-parameters.md#id_lt), [id_lte](./standard-query-parameters.md#id_lte).
* [created_gt](./standard-query-parameters.md#created_gt), [created_gte](./standard-query-parameters.md#created_gte), [created_lt](./standard-query-parameters.md#created_lt), [created_lte](./standard-query-parameters.md#created_lte).
* [submit_gt](./standard-query-parameters.md#submit_gt), [submit_gte](./standard-query-parameters.md#submit_gte), [submit_lt](./standard-query-parameters.md#submit_lt), [submit_lte](./standard-query-parameters.md#submit_lte).
* [acceptedt_gt](./standard-query-parameters.md#accepted_gt), [accepted_gte](./standard-query-parameters.md#accepted_gte), [accepted_lt](./standard-query-parameters.md#accepted_lt), [accepted_lte](./standard-query-parameters.md#accepted_lte).
* [rejected_gt](./standard-query-parameters.md#rejected_gt), [rejected_gte](./standard-query-parameters.md#rejected_gte), [rejected_lt](./standard-query-parameters.md#rejected_lt), [rejected_lte](./standard-query-parameters.md#rejected_lte). 
* [skipped_gt](./standard-query-parameters.md#skipped_gt), [skipped_gte](./standard-query-parameters.md#skipped_gte), [skipped_lt](./standard-query-parameters.md#skipped_lt), [skipped_lte](./standard-query-parameters.md#skipped_lte).
* [expired_gt](./standard-query-parameters.md#expired_gt), [expired_gte](./standard-query-parameters.md#expired_gte), [expired_lt](./standard-query-parameters.md#expired_lt), [expired_lte](./standard-query-parameters.md#expired_lte). ||
|#

## Query example {#request-example}

You can set up the display of the list of responses in parts (for example, 10 responses at a time):

1. Show the first 10 responses, starting with the one with the lowest ID.
1. Show the remaining responses (10 at a time) in ascending order.

**Show the first 10 responses**

{% list tabs %}

- Production version

	```json
	GET https://toloka.yandex.com/api/v1/assignments?sort=id&limit=10
	Authorization: OAuth <OAuth token>
	```

- Sandbox

	```json
	GET https://sandbox.toloka.yandex.com/api/v1/assignments?sort=id&limit=10
	Authorization: OAuth <OAuth token>
	```

{% endlist %}

**Show the remaining tasks sorted by ascending ID**

{% list tabs %}

- Production version

	```json
	GET >https://toloka.yandex.com/api/v1/assignments?sort=id&limit=10&id_gt=<ID of the last task suite from the previous response>
	Authorization: OAuth <OAuth token>
	```

- Sandbox

	```json
	GET https://sandbox.toloka.yandex.com/api/v1/assignments?sort=id&limit=10&id_gt=<ID of the last task suite from the previous response>
	Authorization: OAuth <OAuth token>
	```

{% endlist %}

## Response {#response}

[Information about responses](get-assignment-id.md) in the `items` array:

```json
{"items" : [{task suite #1}, {task suite #2}, ... {task suite #n}], "has_more": true}
```

