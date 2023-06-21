# AssignmentsIssuingConfig
`toloka.client.pool.Pool.AssignmentsIssuingConfig` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/pool/__init__.py#L115)

```python
AssignmentsIssuingConfig(self, issue_task_suites_in_creation_order: Optional[bool] = None)
```

Settings for assigning task suites in the pool.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`issue_task_suites_in_creation_order`|**Optional\[bool\]**|<p>Task suites are assigned in the order in which they were created.</p> <p>This parameter is used when tasks are [grouped into suites](https://toloka.ai/docs/guide/distribute-tasks-by-pages) manually and the `assignments_issuing_type` project parameter is set to `AUTOMATED`.</p>
