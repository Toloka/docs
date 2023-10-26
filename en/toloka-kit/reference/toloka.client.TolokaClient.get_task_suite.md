# get_task_suite
`toloka.client.TolokaClient.get_task_suite` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L2845)

```python
get_task_suite(self, task_suite_id: str)
```

Gets task suite data from Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_suite_id`|**str**|<p>The ID of the task suite.</p>

* **Returns:**

  The task suite.

* **Return type:**

  [TaskSuite](toloka.client.task_suite.TaskSuite.md)

**Examples:**


```python
task_suite = toloka_client.get_task_suite(task_suite_id='00001092da--61ef030400c684132d0da0dc')
print(len(task_suite.tasks))
```
