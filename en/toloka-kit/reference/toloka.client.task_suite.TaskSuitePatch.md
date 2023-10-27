# TaskSuitePatch
`toloka.client.task_suite.TaskSuitePatch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/task_suite.py#L118)

```python
TaskSuitePatch(
    self,
    *,
    infinite_overlap=None,
    overlap=None,
    issuing_order_override: Optional[float] = None,
    open_pool: Optional[bool] = None
)
```

Parameters for changing a task suite.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`issuing_order_override`|**Optional\[float\]**|<p>The priority of a task suite. It influences the order of assigning task suites to Tolokers in pools with the `issue_task_suites_in_creation_order` parameter set to `True`. Allowed range: from -99999.99999 to 99999.99999. </p><p>Default value: 0.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after changing a task suite, if the pool is closed. </p><p>Default value: `False`.</p>
