# SkippedAssignmentsCountPoolAnalytics
`toloka.client.analytics_request.SkippedAssignmentsCountPoolAnalytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/analytics_request.py#L104)

```python
SkippedAssignmentsCountPoolAnalytics(self, *, subject_id: str)
```

Counts the number of assignments with the `SKIPPED` status in a pool.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subject_id`|**str**|<p>The ID of a pool to get analytics about.</p>

**Examples:**


```python
operation = toloka_client.get_analytics(
    [toloka.client.analytics_request.SkippedAssignmentsCountPoolAnalytics(subject_id='1084779')]
)
operation = toloka_client.wait_operation(operation)
count = operation.details['value'][0]['result']
print(count)
```
