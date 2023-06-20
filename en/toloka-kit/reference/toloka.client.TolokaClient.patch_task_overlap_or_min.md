# patch_task_overlap_or_min
`toloka.client.TolokaClient.patch_task_overlap_or_min` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L2531)

Stops assigning a task to Tolokers.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_id`|**str**|<p>The ID of the task.</p>
`overlap`|**Optional\[int\]**|<p>The new overlap value.</p>
`infinite_overlap`|**Optional\[bool\]**|<ul> <li>`True` — The task is assigned to all Tolokers. It is usually set for training and control tasks.</li> <li>`False` — An overlap value specified for the task or for the pool is used.</li> </ul> <p></p><p>Default value: `False`.</p>

* **Returns:**

  The task with updated fields.

* **Return type:**

  [Task](toloka.client.task.Task.md)

**Examples:**

Setting an infinite overlap for a training task.

```python
toloka_client.patch_task_overlap_or_min(task_id='1', infinite_overlap=True)
```

{% note info %}

You can't set infinite overlap in a regular pool.

{% endnote %}
