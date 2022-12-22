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

The results of the tasks creation operation.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[Dict\[str, [Task](toloka.client.task.Task.md)\]\]**|<p>A list of created tasks.</p>
`validation_errors`|**Optional\[Dict\[str, Dict\[str, [FieldValidationError](toloka.client.batch_create_results.FieldValidationError.md)\]\]\]**|<p>A list with validation errors in input tasks. The list is filled if the request parameter `skip_invalid_items` is `True`.</p>
