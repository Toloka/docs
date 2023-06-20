# ApprovedAssignmentsCountPoolAnalytics
`toloka.client.analytics_request.ApprovedAssignmentsCountPoolAnalytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/analytics_request.py#L100)

```python
ApprovedAssignmentsCountPoolAnalytics(self, *, subject_id: str)
```

Counts the number of assignments with the `ACCEPTED` status in a pool.


Do not confuse these task statuses:
    * `SUBMITTED` tasks are completed by Tolokers and sent for a review.
    * `ACCEPTED` tasks have passed the review and have been paid for.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subject_id`|**str**|<p>The ID of a pool to get analytics about.</p>
