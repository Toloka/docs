# SubmittedAssignmentsCountPoolAnalytics
`toloka.client.analytics_request.SubmittedAssignmentsCountPoolAnalytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/analytics_request.py#L76)

```python
SubmittedAssignmentsCountPoolAnalytics(self, *, subject_id: str)
```

Number of assignments in the "submitted" status in the pool


Do not confuse it with the approved status.
"Submitted" status means that the task was completed by a Toloker and sent for review.
"Approved" status means that the task has passed review and money has been paid for it.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subject_id`|**str**|<p>ID of the object you want to get analytics about.</p>
