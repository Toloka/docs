# Upload tasks

_Create and upload control and general tasks to the pool._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Create control task {#step-three}

In this recipe we create a control task first. The main difference between a control and general task in Toloka is that a control task has a known answer to it. For this answer, the `known_solutions` parameter of the [Task](../reference/toloka.client.task.Task.md) class object is used.

[Find out](get-pools.md) the ID of the pool where you want to upload the created tasks. For control tasks, set `infinite_overlap` to `True`.

```python
control_task = toloka.task.[Task](*Task)(
    input_values={'image': 'https://example.com/image_example.png'},
    known_solutions=[
        toloka.task.[BaseTask](*BaseTask).[KnownSolution](*KnownSolution)(output_values={'result': 'cat'})
    ],
    infinite_overlap=True,
    pool_id='1238218'
)
```

{% note info %}

You need to know what values are allowed for the output data (`output_values`). You set the output data when you [create a project](create-project.md#step-three).

{% endnote %}

In the platform, we create the control task using the `create_task()` method.

```python
toloka_client.[create_task](*create_task)(control_task)
```

### 4. Specify image URLs and form tasks {#step-four}

Now, let's enumerate the URLs of the images in an array. We are going to use these images for our general tasks.

```python
image_urls = [
    'https://example.com/image_1.png',
    'https://example.com/image_2.png',
    'https://example.com/image_3.png'
]
```

Populate tasks with images, use the same `pool_id` as at [step 3](#step-three).

```python
tasks = [toloka.task.[Task](*Task)(input_values={'image': url}, pool_id='1238218')
            for url in image_urls]
```

### 5. Upload tasks to Toloka {#step-five}

This actually uploads tasks to Toloka.

```python
result = toloka_client.[create_tasks](*create_tasks)(tasks,
            allow_defaults=True, skip_invalid_items=False)
```

The task uploading progress will look like this.

```bash
100%|████████████████████████████████████████████| 100/100 [00:01<00:00, 52.35it/s]
```

### 6. Print number of created tasks {#step-six}

The `create_tasks()` request will return the [TaskBatchCreateResult](../reference/toloka.client.batch_create_results.TaskBatchCreateResult.md) class object. You can use its attributes to print the information you need.

```python
print(len(result.items))
```

You should get an output with the number of the created tasks which looks like this.

```bash
3
```

## Complete code: Upload tasks {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

control_task = toloka.task.Task(
    input_values={'image': 'https://example.com/image_example.png'},
    known_solutions=[
        toloka.task.BaseTask.KnownSolution(output_values={'result': 'cat'})
    ],
    infinite_overlap=True,
    pool_id='1238218'
)
toloka_client.create_task(control_task)

image_urls = [
    'https://example.com/image_1.png',
    'https://example.com/image_2.png',
    'https://example.com/image_3.png'
]
tasks = [toloka.task.Task(input_values={'image': url}, pool_id='1238218')
            for url in image_urls]
result = toloka_client.create_tasks(tasks,
            allow_defaults=True, skip_invalid_items=False)
print(len(result.items))
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[Task](../reference/toloka.client.task.Task.md) class_
- _[BaseTask](../reference/toloka.client.task.BaseTask.md) class_
- _[KnownSolution](../reference/toloka.client.task.BaseTask.KnownSolution.md) class_
- _[create_task()](../reference/toloka.client.TolokaClient.create_task.md) method_
- _[create_tasks()](../reference/toloka.client.TolokaClient.create_tasks.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](../../guide/concepts/goldenset.md)
- [{#T}](get-pools.md)
- [Toloka-Kit: TaskBatchCreateResult class](../reference/toloka.client.batch_create_results.TaskBatchCreateResult.md)
- [Toloka API: Create single/multiple tasks](https://toloka.ai/docs/api/api-reference/#post-/tasks)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*Task]: [Task](../reference/toloka.client.task.Task.md) class
[*BaseTask]: [BaseTask](../reference/toloka.client.task.BaseTask.md) class
[*KnownSolution]: [KnownSolution](../reference/toloka.client.task.BaseTask.KnownSolution.md) class
[*create_task]: [create_task()](../reference/toloka.client.TolokaClient.create_task.md) method
[*create_tasks]: [create_tasks()](../reference/toloka.client.TolokaClient.create_tasks.md) method