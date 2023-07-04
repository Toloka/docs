# Group tasks in task suites

_Create tasks and group them into task suites._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Create tasks {#step-three}

First, create one or several tasks. In this example, we create three simple tasks with the following settings:

- specify `input_values` as links to images

You can choose your own values for tasks. Refer to the [Task](../reference/toloka.client.task.Task.md) class page for more details.

```python
tasks = [
    toloka.task.[Task](*Task)(input_values={'image': 'https://example.com/image_1.png'}),
    toloka.task.[Task](*Task)(input_values={'image': 'https://example.com/image_2.png'}),
    toloka.task.[Task](*Task)(input_values={'image': 'https://example.com/image_3.png'})
]
```

{% note alert "Important" %}

All the code manipulations at steps 3–4 occur in your device memory. The data will only be sent to the server after calling the `create_task_suite()` method at [step 5](#step-five).

{% endnote %}

### 4. Create task suite object {#step-four}

Specify the ID of the pool where the task suite will be created, tasks included into the task suite, and overlap.

```python
new_task_suite = toloka.task_suite.[TaskSuite](*TaskSuite)(pool_id='1442472', tasks=tasks, overlap=3)
```

### 5. Create task suite on platform {#step-five}

This actually creates a task suite in Toloka.

```python
new_task_suite = toloka_client.[create_task_suite](*create_task_suite)(new_task_suite)
```

### 6. Print created task suite ID {#step-six}

The `create_task_suite()` request will return the [TaskSuite](../reference/toloka.client.task_suite.TaskSuite.md) class object. You can use its attributes to print the information you need.

```python
print(new_task_suite.id)
```

You should get an output with the created task suite ID which looks like this.

```bash
00001602a8--63c18a66ed43982367a7acc8
```

## Complete code: Group tasks in task suites {#complete-code}

```python
import toloka.client as toloka
from toloka.client.task import Task
from toloka.client.task_suite import TaskSuite

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

tasks = [
    toloka.task.Task(input_values={'image': 'https://example.com/image_1.png'}),
    toloka.task.Task(input_values={'image': 'https://example.com/image_2.png'}),
    toloka.task.Task(input_values={'image': 'https://example.com/image_3.png'})
]
new_task_suite = toloka.task_suite.TaskSuite(pool_id='1442472', tasks=tasks, overlap=3)
new_task_suite = toloka_client.create_task_suite(new_task_suite)
print(new_task_suite.id)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[Task](../reference/toloka.client.task.Task.md) class_
- _[TaskSuite](../reference/toloka.client.task_suite.TaskSuite.md) class_
- _[create_task_suite()](../reference/toloka.client.TolokaClient.create_task_suite.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [Toloka API: Create single/multiple task suites](https://toloka.ai/docs/api/api-reference/#post-/task-suites)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*Task]: [Task](../reference/toloka.client.task.Task.md) class
[*TaskSuite]: [TaskSuite](../reference/toloka.client.task_suite.TaskSuite.md) class
[*create_task_suite]: [create_task_suite()](../reference/toloka.client.TolokaClient.create_task_suite.md) method