# Get task details

_Get the detailed information about the task with the ID specified in the request._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Get task information {#step-three}

[Find out](./get-tasks.md) the ID of the task for which you want to get the detailed information. Then get this info calling the `get_task()` method.

```python
task = toloka_client.[get_task](*get_task)('000012bb84--62d80429f20bf20e50f36a27')
```

### 4. Print task ID, overlap, and creation date {#step-four}

The `get_task()` request will return the [Task](../reference/toloka.client.task.Task.md) class object. You can use its attributes to print the information you need.

```python
print(task.id, task.overlap, task.created.date())
```

You should get an output with the task ID, overlap, and creation date which looks like this.

```bash
00022da5a7--6388b40547c84000494cdc58 3 2022-12-01
```

## Complete code: Get task details {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

task = toloka_client.get_task('000012bb84--62d80429f20bf20e50f36a27')
print(task.id, task.overlap, task.created.date())
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_task()](../reference/toloka.client.TolokaClient.get_task.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [Toloka-Kit: Task class](../reference/toloka.client.task.Task.md)
- [Toloka API: Get task by ID](https://toloka.ai/docs/api/api-reference/#get-/tasks/-id-)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_task]: [get_task()](../reference/toloka.client.TolokaClient.get_task.md) method