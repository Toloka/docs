# patch_task_suite_overlap_or_min
`toloka.client.TolokaClient.patch_task_suite_overlap_or_min` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L2917)

Stops assigning a task suite to Tolokers.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_suite_id`|**str**|<p>The ID of the task suite.</p>
`overlap`|**Optional\[int\]**|<p>The new overlap value.</p>

* **Returns:**

  Task suite with updated fields.

* **Return type:**

  [TaskSuite](toloka.client.task_suite.TaskSuite.md)

**Examples:**


```python
toloka_client.patch_task_suite_overlap_or_min(
    task_suite_id='00001092da--61ef030400c684132d0da0dc',
    overlap=0
)
```
