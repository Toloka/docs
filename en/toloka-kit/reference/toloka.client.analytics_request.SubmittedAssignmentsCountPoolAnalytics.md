# SubmittedAssignmentsCountPoolAnalytics
`toloka.client.analytics_request.SubmittedAssignmentsCountPoolAnalytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/analytics_request.py#L77)

```python
SubmittedAssignmentsCountPoolAnalytics(self, *, subject_id: str)
```

Counts the total number of completed assignments in a pool.


It counts assignments with the `SUBMITTED`, `ACCEPTED`, or `REJECTED` status.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subject_id`|**str**|<p>The ID of a pool to get analytics about.</p>
