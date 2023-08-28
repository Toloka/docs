# CompletionPercentagePoolAnalytics
`toloka.client.analytics_request.CompletionPercentagePoolAnalytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/analytics_request.py#L156)

```python
CompletionPercentagePoolAnalytics(self, *, subject_id: str)
```

Calculates the percentage of completed tasks in a pool.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subject_id`|**str**|<p>The ID of a pool to get analytics about.</p>

**Examples:**


```python
operation = toloka_client.get_analytics(
    [toloka.client.analytics_request.CompletionPercentagePoolAnalytics(subject_id='1084779')]
)
operation = toloka_client.wait_operation(operation)
percentage = operation.details['value'][0]['result']['value']
print(percentage)
```
