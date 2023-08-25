# EstimatedAssignmentsCountPoolAnalytics
`toloka.client.analytics_request.EstimatedAssignmentsCountPoolAnalytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/analytics_request.py#L257)

```python
EstimatedAssignmentsCountPoolAnalytics(self, *, subject_id: str)
```

The approximate number of responses to task pages.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subject_id`|**str**|<p>The ID of a pool to get analytics about.</p>

**Examples:**


```python
operation = toloka_client.get_analytics(
    [toloka.client.analytics_request.EstimatedAssignmentsCountPoolAnalytics(subject_id='1084779')]
)
operation = toloka_client.wait_operation(operation)
count = operation.details['value'][0]['result']['value']
print(count)
```
