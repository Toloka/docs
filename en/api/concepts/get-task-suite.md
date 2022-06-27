# Get a task suite

Gets a task suite.

## Request {#request}

{% list tabs %}

- Production version

	```json
	GET https://toloka.yandex.com/api/v1/task-suites/<task_suite_id>
	Authorization: OAuth <OAuth token>
	```

- Sandbox

	```json
	GET https://sandbox.toloka.yandex.com/api/v1/task-suites/<task_suite_id>
	Authorization: OAuth <OAuth token>
	```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**task_suite_id** | ID of a task suite.


## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.


## Response {#response}

Contains a [task suite in JSON format](create-task-suite.md#body).

