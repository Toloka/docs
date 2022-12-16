# Defaults
`toloka.client.pool.Pool.Defaults` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/pool/__init__.py#L154)

```python
Defaults(
    self,
    *,
    default_overlap_for_new_task_suites: Optional[int] = None,
    default_overlap_for_new_tasks: Optional[int] = None
)
```

Settings that are applied by default when uploading new task suites to a pool.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`default_overlap_for_new_task_suites`|**Optional\[int\]**|<p>The overlap for task suites that are uploaded to the pool (used if the allow_defaults=True parameter is set when uploading).</p>
`default_overlap_for_new_tasks`|**Optional\[int\]**|<p>The overlap for tasks that are uploaded to the pool (used if the allow_defaults=True parameter is set when uploading).</p>
