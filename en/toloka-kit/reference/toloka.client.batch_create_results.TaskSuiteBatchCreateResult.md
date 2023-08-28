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

The result of a task suite creation.


`TaskSuiteBatchCreateResult` is returned by the [create_task_suites](toloka.client.TolokaClient.create_task_suites.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[Dict\[str, [TaskSuite](toloka.client.task_suite.TaskSuite.md)\]\]**|<p>A dictionary with created task suites. The indexes of a `create_task_suites` input list are used as keys in the dictionary.</p>
`validation_errors`|**Optional\[Dict\[str, Dict\[str, [FieldValidationError](toloka.client.batch_create_results.FieldValidationError.md)\]\]\]**|<p>A dictionary with validation errors in input task suites. It is filled if the request parameter `skip_invalid_items` is `True`.</p>

**Examples:**


```python
task_suites = [
    toloka.client.TaskSuite(
        pool_id=1240045,
        overlap=1,
        tasks=[ toloka.client.Task(input_values={'question': 'Choose a random number'}) ]
    )
]
result = toloka_client.create_task_suites(task_suites=task_suites, skip_invalid_items=True)
for k, error in result.validation_errors.items():
    print(k, error.message)
```
