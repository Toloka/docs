# SpentBudgetPoolAnalytics
`toloka.client.analytics_request.SpentBudgetPoolAnalytics` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/analytics_request.py#L188)

```python
SpentBudgetPoolAnalytics(self, *, subject_id: str)
```

Shows money spent on a pool, excluding fees.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subject_id`|**str**|<p>The ID of a pool to get analytics about.</p>

**Examples:**


```python
operation = toloka_client.get_analytics(
    [toloka.client.analytics_request.SpentBudgetPoolAnalytics(subject_id='1084779')]
)
operation = toloka_client.wait_operation(operation)
spent = operation.details['value'][0]['result']
print(spent)
```
