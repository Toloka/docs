# SubmittedAssignmentsCountPoolAnalytics
`toloka.client.analytics_request.SubmittedAssignmentsCountPoolAnalytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/analytics_request.py#L86)

```python
SubmittedAssignmentsCountPoolAnalytics(self, *, subject_id: str)
```

Counts the total number of completed assignments in a pool.


It counts assignments with the `SUBMITTED`, `ACCEPTED`, or `REJECTED` status.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subject_id`|**str**|<p>The ID of a pool to get analytics about.</p>

**Examples:**


```python
operation = toloka_client.get_analytics(
    [toloka.client.analytics_request.SubmittedAssignmentsCountPoolAnalytics(subject_id='1084779')]
)
operation = toloka_client.wait_operation(operation)
count = operation.details['value'][0]['result']
print(count)
```
