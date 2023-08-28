# Parameters
`toloka.client.operations.TaskSuiteCreateBatchOperation.Parameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/operations.py#L346)

```python
Parameters(
    self,
    *,
    skip_invalid_items: Optional[bool] = None,
    allow_defaults: Optional[bool] = None,
    open_pool: Optional[bool] = None
)
```

Parameters passed to the [create_task_suites_async](toloka.client.TolokaClient.create_task_suites_async.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`skip_invalid_items`|**Optional\[bool\]**|<p>Task validation parameter.</p>
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap parameter.</p>
`open_pool`|**Optional\[bool\]**|<p>Opening the pool immediately.</p>
