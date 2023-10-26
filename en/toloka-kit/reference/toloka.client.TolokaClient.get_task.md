# get_task
`toloka.client.TolokaClient.get_task` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L2579)

```python
get_task(self, task_id: str)
```

Gets a task with specified ID from Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_id`|**str**|<p>The ID of the task.</p>

* **Returns:**

  The task with the ID specified in the request.

* **Return type:**

  [Task](toloka.client.task.Task.md)

**Examples:**


```python
task = toloka_client.get_task(task_id='00001092da--61ef01d5825234636bb088eb')
print(task.input_values)
```
