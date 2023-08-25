# UniqueSubmittersCountPoolAnalytics
`toloka.client.analytics_request.UniqueSubmittersCountPoolAnalytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/analytics_request.py#L220)

```python
UniqueSubmittersCountPoolAnalytics(self, *, subject_id: str)
```

Counts the number of Tolokers who completed at least one task suite in a pool.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subject_id`|**str**|<p>The ID of a pool to get analytics about.</p>

**Examples:**


```python
operation = toloka_client.get_analytics(
    [toloka.client.analytics_request.UniqueSubmittersCountPoolAnalytics(subject_id='1084779')]
)
operation = toloka_client.wait_operation(operation)
count = operation.details['value'][0]['result']
print(count)
```
