# get_analytics
`toloka.client.TolokaClient.get_analytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L2279)

```python
get_analytics(self, stats: List[AnalyticsRequest])
```

Sends analytics requests to Toloka.


You can request up to 10 metrics at a time.

The values of different analytical metrics are returned in the `details` field of the operation when it is completed.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`stats`|**List\[[AnalyticsRequest](toloka.client.analytics_request.AnalyticsRequest.md)\]**|<p>A list of analytics requests.</p>

* **Returns:**

  An object to track the progress of the operation.

* **Return type:**

  [AnalyticsOperation](toloka.client.operations.AnalyticsOperation.md)

**Examples:**

The example shows how get the percentage of completed tasks in the pool.

```python
from toloka.client.analytics_request import CompletionPercentagePoolAnalytics
operation = toloka_client.get_analytics([CompletionPercentagePoolAnalytics(subject_id='1080020')])
operation = toloka_client.wait_operation(operation)
print(operation.details['value'][0])
completed_task_percentage = operation.details['value'][0]['result']['value']
```
