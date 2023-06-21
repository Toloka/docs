# ActiveWorkersByFilterCountPoolAnalytics
`toloka.client.analytics_request.ActiveWorkersByFilterCountPoolAnalytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/analytics_request.py#L146)

```python
ActiveWorkersByFilterCountPoolAnalytics(
    self,
    *,
    subject_id: str,
    interval_hours: int
)
```

Counts the number of active Tolokers that match pool filters.


Active Tolokers are Tolokers who viewed and completed tasks recently.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subject_id`|**str**|<p>The ID of a pool to get analytics about.</p>
`interval_hours`|**int**|<p>The interval in hours to take into account.</p>
