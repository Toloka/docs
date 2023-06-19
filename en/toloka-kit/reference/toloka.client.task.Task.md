# Task
`toloka.client.task.Task` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/task.py#L54)

```python
Task(
    self,
    *,
    input_values: Optional[Dict[str, Any]] = None,
    known_solutions: Optional[List[BaseTask.KnownSolution]] = None,
    message_on_unknown_solution: Optional[str] = None,
    id: Optional[str] = None,
    infinite_overlap=None,
    overlap=None,
    pool_id: Optional[str] = None,
    remaining_overlap: Optional[int] = None,
    reserved_for: Optional[List[str]] = None,
    unavailable_for: Optional[List[str]] = None,
    traits_all_of: Optional[List[str]] = None,
    traits_any_of: Optional[List[str]] = None,
    traits_none_of_any: Optional[List[str]] = None,
    origin_task_id: Optional[str] = None,
    created: Optional[datetime] = None,
    baseline_solutions: Optional[List[BaselineSolution]] = None
)
```

A task that is assigned to Tolokers.


Tasks are grouped into [TaskSuites](toloka.client.task_suite.TaskSuite.md).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`input_values`|**Optional\[Dict\[str, Any\]\]**|<p>A dictionary with input data for a task. Input field names are keys in the dictionary.</p>
`known_solutions`|**Optional\[List\[[BaseTask.KnownSolution](toloka.client.task.BaseTask.KnownSolution.md)\]\]**|<p>A list of all responses considered correct. It is used with control and training tasks. If there are several output fields, then you must specify all their correct combinations.</p>
`message_on_unknown_solution`|**Optional\[str\]**|<p>A hint used in training tasks.</p>
`id`|**Optional\[str\]**|<p>The ID of a task.</p>
`pool_id`|**Optional\[str\]**|<p>The ID of the pool that the task belongs to.</p>
`remaining_overlap`|**Optional\[int\]**|<p>The number of times left for this task to be assigned to Tolokers. Read-only field.</p>
`reserved_for`|**Optional\[List\[str\]\]**|<p>IDs of Tolokers who have access to the task.</p>
`unavailable_for`|**Optional\[List\[str\]\]**|<p>IDs of Tolokers who don&#x27;t have access to the task.</p>
`traits_all_of`|**Optional\[List\[str\]\]**|<p>The task can be assigned to Tolokers who have all of the specified traits.</p>
`traits_any_of`|**Optional\[List\[str\]\]**|<p>The task can be assigned to Tolokers who have any of the specified traits.</p>
`traits_none_of_any`|**Optional\[List\[str\]\]**|<p>The task can not be assigned to Tolokers who have any of the specified traits.</p>
`origin_task_id`|**Optional\[str\]**|<p>The ID of a parent task. This parameter is set if the task was created by copying.</p>
`created`|**Optional\[datetime\]**|<p>The UTC date and time when the task was created.</p>
`baseline_solutions`|**Optional\[List\[[BaselineSolution](toloka.client.task.Task.BaselineSolution.md)\]\]**|<p>Preliminary responses for dynamic overlap and aggregation of results by skill. They are used to calculate a confidence level of the first responses from Toloker.</p>

**Examples:**

Creating a simple task with one input field.

```python
task = toloka.client.Task(
    input_values={'image': 'https://some.url/img0.png'},
    pool_id='1'
)
```

See more complex example in the description of the [create_tasks](toloka.client.TolokaClient.create_tasks.md) method.
