# patch_task_suite_overlap_or_min
`toloka.async_client.client.AsyncTolokaClient.patch_task_suite_overlap_or_min` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/__init__.py#L0)

Stops issuing the task suites

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_suite_id`|**str**|<p>ID of the task suite.</p>
`overlap`|**Optional\[int\]**|<p>The new overlap value.</p>

* **Returns:**

  Task suite with updated fields.

* **Return type:**

  [TaskSuite](toloka.client.task_suite.TaskSuite.md)

**Examples:**


```python
toloka_client.patch_task_suite_overlap_or_min(task_suite_id='1', overlap=100)
```
