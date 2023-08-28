# TaskBatchCreateResult
`toloka.client.batch_create_results.TaskBatchCreateResult`

```python
TaskBatchCreateResult(
    self,
    *,
    items: Optional[Dict[str, Task]] = None,
    validation_errors: Optional[Dict[str, Dict[str, FieldValidationError]]] = None
)
```

The result of a task creation.


`TaskBatchCreateResult` is returned by the [create_tasks](toloka.client.TolokaClient.create_tasks.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[Dict\[str, [Task](toloka.client.task.Task.md)\]\]**|<p>A dictionary with created tasks. The indexes of a `create_tasks` input list are used as keys in the dictionary.</p>
`validation_errors`|**Optional\[Dict\[str, Dict\[str, [FieldValidationError](toloka.client.batch_create_results.FieldValidationError.md)\]\]\]**|<p>A dictionary with validation errors in input tasks. It is filled if the request parameter `skip_invalid_items` is `True`.</p>

**Examples:**


```python
tasks = [ toloka.client.task.Task(input_values = {'image': 'https://example.com/image0.png'}, pool_id='1240045') ]
result = toloka_client.create_tasks(tasks, allow_defaults=True, skip_invalid_items=True)
print(result.items['0'].created)
```
