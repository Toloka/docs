# AvgSubmitAssignmentMillisPoolAnalytics
`toloka.client.analytics_request.AvgSubmitAssignmentMillisPoolAnalytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/analytics_request.py#L172)

```python
AvgSubmitAssignmentMillisPoolAnalytics(self, *, subject_id: str)
```

Calculates the average time in milliseconds for completing one task suite.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subject_id`|**str**|<p>The ID of a pool to get analytics about.</p>

**Examples:**


```python
operation = toloka_client.get_analytics(
    [toloka.client.analytics_request.AvgSubmitAssignmentMillisPoolAnalytics(subject_id='1084779')]
)
operation = toloka_client.wait_operation(operation)
ms = operation.details['value'][0]['result']
print(ms)
```
