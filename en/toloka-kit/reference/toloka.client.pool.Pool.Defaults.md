# Defaults
`toloka.client.pool.Pool.Defaults` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/pool/__init__.py#L150)

```python
Defaults(
    self,
    *,
    default_overlap_for_new_task_suites: Optional[int] = None,
    default_overlap_for_new_tasks: Optional[int] = None
)
```

Default settings that are applied to new tasks and task suites in a pool.


These settings are used when tasks or task suites are created with `allow_defaults=True`.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`default_overlap_for_new_task_suites`|**Optional\[int\]**|<p>The default overlap of a task suite.</p>
`default_overlap_for_new_tasks`|**Optional\[int\]**|<p>The default overlap of a task.</p>
