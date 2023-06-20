# TaskSuite
`toloka.client.task_suite.TaskSuite` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/task_suite.py#L20)

```python
TaskSuite(
    self,
    *,
    infinite_overlap=None,
    overlap=None,
    pool_id: Optional[str] = None,
    tasks: Optional[List[BaseTask]] = ...,
    reserved_for: Optional[List[str]] = None,
    unavailable_for: Optional[List[str]] = None,
    issuing_order_override: Optional[float] = None,
    mixed: Optional[bool] = None,
    traits_all_of: Optional[List[str]] = None,
    traits_any_of: Optional[List[str]] = None,
    traits_none_of_any: Optional[List[str]] = None,
    longitude: Optional[float] = None,
    latitude: Optional[float] = None,
    id: Optional[str] = None,
    remaining_overlap: Optional[int] = None,
    automerged: Optional[bool] = None,
    created: Optional[datetime] = None
)
```

A set of tasks assigned to a Toloker at once.


A task suite contains one or more tasks. Tolokers are paid after completing all tasks in a task suite.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**Optional\[str\]**|<p>The ID of a pool that the task suite belongs to.</p>
`tasks`|**Optional\[List\[[BaseTask](toloka.client.task.BaseTask.md)\]\]**|<p>The tasks.</p>
`reserved_for`|**Optional\[List\[str\]\]**|<p>IDs of Tolokers who have access to the task suite.</p>
`unavailable_for`|**Optional\[List\[str\]\]**|<p>IDs of Tolokers who don&#x27;t have access to the task suite.</p>
`issuing_order_override`|**Optional\[float\]**|<p>The priority of a task suite. It influences the order of assigning task suites to Tolokers in pools with the `issue_task_suites_in_creation_order` parameter set to `True`. Allowed range: from -99999.99999 to 99999.99999.</p>
`mixed`|**Optional\[bool\]**|<p>[The way of grouping tasks](https://toloka.ai/en/docs/guide/concepts/distribute-tasks-by-pages) to create the task suite.</p> <ul> <li>`True` — The tasks are mixed automatically using the smart mixing approach.</li> <li>`False` — The tasks are grouped manually.</li> </ul> <p></p><p>Default value: `False`.</p>
`traits_all_of`|**Optional\[List\[str\]\]**|<p>The task suite can be assigned to Tolokers who have all of the specified traits.</p>
`traits_any_of`|**Optional\[List\[str\]\]**|<p>The task suite can be assigned to Tolokers who have any of the specified traits.</p>
`traits_none_of_any`|**Optional\[List\[str\]\]**|<p>The task suite can not be assigned to Tolokers who have any of the specified traits.</p>
`longitude`|**Optional\[float\]**|<p>The longitude of the point on the map for the task suite.</p>
`latitude`|**Optional\[float\]**|<p>The latitude of the point on the map for the task suite.</p>
`id`|**Optional\[str\]**|<p>The ID of the task suite. Read-only field.</p>
`remaining_overlap`|**Optional\[int\]**|<p>The number of times left for this task suite to be assigned to Tolokers. Read-only field.</p>
`automerged`|**Optional\[bool\]**|<ul> <li>`True` — The task suite was created after [merging tasks](https://toloka.ai/en/docs/api/concepts/tasks#task-merge).</li> <li>`False` — There are no merged tasks in the task suite.</li> </ul>
`created`|**Optional\[datetime\]**|<p>The UTC date and time when the task suite was created. Read-only field.</p>
## Methods Summary

| Method | Description |
| :------| :-----------|
[add_base_task](toloka.client.task_suite.TaskSuite.add_base_task.md)| None
