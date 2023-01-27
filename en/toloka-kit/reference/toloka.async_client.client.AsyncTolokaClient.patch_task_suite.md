# patch_task_suite
`toloka.async_client.client.AsyncTolokaClient.patch_task_suite` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/__init__.py#L0)

Changes task suite parameter values in Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_suite_id`|**str**|<p>The ID of the task suite.</p>
`issuing_order_override`|**Optional\[float\]**|<p>The priority of a task suite. It influences the order of assigning task suites to Tolokers in pools with the `issue_task_suites_in_creation_order` parameter set to `True`. Allowed range: from -99999.99999 to 99999.99999. </p><p>Default value: 0.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after changing a task suite, if the pool is closed. </p><p>Default value: `False`.</p>

* **Returns:**

  The task suite with updated fields.

* **Return type:**

  [TaskSuite](toloka.client.task_suite.TaskSuite.md)

**Examples:**

Change the task suite's priority.

```python
toloka_client.patch_task_suite(task_suite_id='1', issuing_order_override=100)
```
