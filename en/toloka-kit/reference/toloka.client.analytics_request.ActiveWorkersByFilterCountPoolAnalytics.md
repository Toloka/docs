# ActiveWorkersByFilterCountPoolAnalytics
`toloka.client.analytics_request.ActiveWorkersByFilterCountPoolAnalytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/analytics_request.py#L236)

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

**Examples:**


```python
operation = toloka_client.get_analytics(
    [toloka.client.analytics_request.ActiveWorkersByFilterCountPoolAnalytics(subject_id='1084779', interval_hours=3)]
)
operation = toloka_client.wait_operation(operation)
count = operation.details['value'][0]['result']
print(count)
```
