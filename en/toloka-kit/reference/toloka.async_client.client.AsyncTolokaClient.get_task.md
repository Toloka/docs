# get_task
`toloka.async_client.client.AsyncTolokaClient.get_task` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/async_client/client.py#L0)

```python
async get_task(self, task_id: str)
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
toloka_client.get_task(task_id='1')
```
