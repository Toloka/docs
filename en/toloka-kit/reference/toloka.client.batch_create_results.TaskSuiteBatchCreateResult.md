# TaskSuiteBatchCreateResult
`toloka.client.batch_create_results.TaskSuiteBatchCreateResult`

```python
TaskSuiteBatchCreateResult(
    self,
    *,
    items: Optional[Dict[str, TaskSuite]] = None,
    validation_errors: Optional[Dict[str, Dict[str, FieldValidationError]]] = None
)
```

The results of the task suites creation operation.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[Dict\[str, [TaskSuite](toloka.client.task_suite.TaskSuite.md)\]\]**|<p>A list of created task suites.</p>
`validation_errors`|**Optional\[Dict\[str, Dict\[str, [FieldValidationError](toloka.client.batch_create_results.FieldValidationError.md)\]\]\]**|<p>A list with validation errors in input task suites. The list is filled if the request parameter `skip_invalid_items` is `True`.</p>
