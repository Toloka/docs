# RejectedAssignmentsCountPoolAnalytics
`toloka.client.analytics_request.RejectedAssignmentsCountPoolAnalytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/analytics_request.py#L120)

```python
RejectedAssignmentsCountPoolAnalytics(self, *, subject_id: str)
```

Counts the number of assignments with the `REJECTED` status in a pool.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subject_id`|**str**|<p>The ID of a pool to get analytics about.</p>

**Examples:**


```python
operation = toloka_client.get_analytics(
    [toloka.client.analytics_request.RejectedAssignmentsCountPoolAnalytics(subject_id='1084779')]
)
operation = toloka_client.wait_operation(operation)
count = operation.details['value'][0]['result']
print(count)
```
