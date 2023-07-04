# Set overlap

_Set overlap for tasks at pool, task suite, and task levels._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Set overlap at pool level {#step-three}

Create a pool and set the default overlap value for all the tasks which will be uploaded without additionally specifying it. Use the `default_overlap_for_new_task_suites` value of the [Defaults](../reference/toloka.client.pool.Pool.Defaults.md) class for that.

Refer to the [{#T}](./create-pool.md) recipe for more information on how to create a pool and what parameters you can use.

```python
new_pool = toloka.pool.[Pool](*Pool)(
    project_id='133047',
    private_name='Pool with filters',
    will_expire=datetime(2030, 1, 1),
    reward_per_assignment=0.05,
    assignment_max_duration_seconds=60*5,
    defaults=toloka.pool.Pool.[Defaults](*Defaults)(default_overlap_for_new_task_suites=1)
)
new_pool = toloka_client.[create_pool](*create_pool)(new_pool)
```

### 4. Set overlap at task suite level {#step-four}

Another way to set overlap is specify it when creating a task suite. Use the `overlap` parameter of the [TaskSuite](../reference/toloka.client.task_suite.TaskSuite.md) class object to set a specific overlap value to the tasks inside a task suite.

Refer to the [{#T}](./create-task-suite.md) recipe for more information on how to create a task suite and what parameters you can use.

```python
tasks = [
    toloka.task.[Task](*Task)(input_values={'image': 'https://example.com/image_1.png'}),
    toloka.task.[Task](*Task)(input_values={'image': 'https://example.com/image_2.png'}),
    toloka.task.[Task](*Task)(input_values={'image': 'https://example.com/image_3.png'})
]
new_task_suite = toloka.task_suite.[TaskSuite](*TaskSuite)(pool_id=new_pool.id, tasks=tasks, overlap=3)
toloka_client.[create_task_suite](*create_task_suite)(new_task_suite)
```

### 5. Set overlap at task level {#step-five}

Now, create and upload two tasks: one without the `overlap` parameter (it will be equal to the default value, set at [step 3](#step-three)) and one with the `overlap` parameter set to `2`.

Refer to the [{#T}](./upload-tasks.md) recipe for more information on how to upload tasks.

```python
tasks = [
    # This task will have the default 'overlap' parameter value (1)
    toloka.task.[Task](*Task)(input_values={'image': 'https://example.com/image_4.png'}, pool_id=new_pool.id),
    # This task will have the 'overlap' parameter value set to 2
    toloka.task.[Task](*Task)(input_values={'image': 'https://example.com/image_5.png'}, pool_id=new_pool.id, overlap=2)
]
toloka_client.[create_tasks](*create_tasks)(tasks, allow_defaults=True, skip_invalid_items=False)
```

The task uploading progress will look like this.

```bash
100%|████████████████████████████████████████████| 100/100 [00:01<00:00, 52.35it/s]
```

### 6. Print tasks with different overlap {#step-six}

Use the `get_task_suites()` request to get the information about the tasks in the [task suite you created](#step-four). For information about [tasks uploaded without grouping](#step-five), use the `get_tasks()` method. Use the attributes of the returned objects ([TaskSuite](../reference/toloka.client.task_suite.TaskSuite.md) and [Task](../reference/toloka.client.task.Task.md) accordingly) to print the information you need.

```python
for task_suite in toloka_client.[get_task_suites](*get_task_suites)(pool_id=new_pool.id):
    for task in task_suite.tasks:
        print(task.id, task_suite.overlap)

for task in toloka_client.[get_tasks](*get_tasks)(pool_id=new_pool.id):
    print(task.id, task.overlap)
```

You should get an output with the IDs of the created tasks and their overlap values which looks like this.

```bash
7776f1f0-2a58-4a77-af32-d0043ae6df10 3
aaf9b554-cb3b-477e-ba48-d2581004a7ac 3
80ad8ffb-cf15-4c32-9190-93d994bc5110 3
0000160899--63c5414699e537000bb2113f 1
0000160899--63c5414799e537000bb21141 2
```

## Complete code: Set overlap {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

new_pool = toloka.pool.Pool(
    project_id='133047',
    private_name='Pool with filters',
    will_expire=datetime(2030, 1, 1),
    reward_per_assignment=0.05,
    assignment_max_duration_seconds=60*5,
    defaults=toloka.pool.Pool.Defaults(default_overlap_for_new_task_suites=1)
)
new_pool = toloka_client.create_pool(new_pool)

tasks = [
    toloka.task.Task(input_values={'image': 'https://example.com/image_1.png'}),
    toloka.task.Task(input_values={'image': 'https://example.com/image_2.png'}),
    toloka.task.Task(input_values={'image': 'https://example.com/image_3.png'})
]
new_task_suite = toloka.task_suite.TaskSuite(pool_id=new_pool.id, tasks=tasks, overlap=3)
toloka_client.create_task_suite(new_task_suite)

tasks = [
    toloka.task.Task(input_values={'image': 'https://example.com/image_4.png'}, pool_id=new_pool.id),
    toloka.task.Task(input_values={'image': 'https://example.com/image_5.png'}, pool_id=new_pool.id, overlap=2)
]
toloka_client.create_tasks(tasks, allow_defaults=True, skip_invalid_items=False)

for task_suite in toloka_client.get_task_suites(pool_id=new_pool.id):
    for task in task_suite.tasks:
        print(task.id, task_suite.overlap)

for task in toloka_client.get_tasks(pool_id=new_pool.id):
    print(task.id, task.overlap)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[Pool](../reference/toloka.client.pool.Pool.md) class_
- _[create_pool()](../reference/toloka.client.TolokaClient.create_pool.md) method_
- _[Task](../reference/toloka.client.task.Task.md) class_
- _[TaskSuite](../reference/toloka.client.task_suite.TaskSuite.md) class_
- _[create_task_suite()](../reference/toloka.client.TolokaClient.create_task_suite.md) method_
- _[create_tasks()](../reference/toloka.client.TolokaClient.create_tasks.md) method_
- _[get_task_suites()](../reference/toloka.client.TolokaClient.get_task_suites.md) method_
- _[get_tasks()](../reference/toloka.client.TolokaClient.get_tasks.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [Toloka API: Create pool](https://toloka.ai/docs/api/api-reference/#post-/pools)
- [Toloka API: Create single/multiple task suites](https://toloka.ai/docs/api/api-reference/#post-/task-suites)
- [Toloka API: Create single/multiple tasks](https://toloka.ai/docs/api/api-reference/#post-/tasks)
- [Toloka API: Get list of task suites](https://toloka.ai/docs/api/api-reference/#get-/task-suites)
- [Toloka API: Get list of tasks](https://toloka.ai/docs/api/api-reference/#get-/tasks)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*Pool]: [Pool](../reference/toloka.client.pool.Pool.md) class
[*Defaults]: [Defaults](../reference/toloka.client.pool.Pool.Defaults.md) class
[*create_pool]: [create_pool()](../reference/toloka.client.TolokaClient.create_pool.md) method
[*Task]: [Task](../reference/toloka.client.task.Task.md) class
[*TaskSuite]: [TaskSuite](../reference/toloka.client.task_suite.TaskSuite.md) class
[*create_task_suite]: [create_task_suite()](../reference/toloka.client.TolokaClient.create_task_suite.md) method
[*create_tasks]: [create_tasks()](../reference/toloka.client.TolokaClient.create_tasks.md) method
[*get_task_suites]: [get_task_suites()](../reference/toloka.client.TolokaClient.get_task_suites.md) method
[*get_tasks]: [get_tasks()](../reference/toloka.client.TolokaClient.get_tasks.md) method