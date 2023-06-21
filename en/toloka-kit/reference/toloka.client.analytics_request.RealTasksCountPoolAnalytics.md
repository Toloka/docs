# RealTasksCountPoolAnalytics
`toloka.client.analytics_request.RealTasksCountPoolAnalytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/analytics_request.py#L68)

```python
RealTasksCountPoolAnalytics(self, *, subject_id: str)
```

Counts the number of general tasks in a pool.


Note, that `RealTasksCountPoolAnalytics` doesn't take into account control and training tasks, and task overlap.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subject_id`|**str**|<p>The ID of a pool to get analytics about.</p>
