# Change task overlap

_Increase the overlap of a task when you need more Tolokers to complete it._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Change task overlap {#step-three}

[Find out](./get-tasks.md) the ID of the task which you want to modify. Then change the task overlap calling the `patch_task()` method.

```python
task = toloka_client.[patch_task](*patch_task)('00022da5a7--6388b40547c84000494cdc5a', overlap=5)
```

### 4. Display resulting task overlap {#step-four}

The `patch_task()` request will return the [Task](../reference/toloka.client.task.Task.md) class object. You can use its attributes to print the information you need.

```python
print(task.id, task.overlap)
```

You should get an output with the task ID and modified overlap which looks like this.

```bash
00022da5a7--6388b40547c84000494cdc5a 5
```

## Complete code: Change task overlap {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

task = toloka_client.patch_task('00022da5a7--6388b40547c84000494cdc5a', overlap=5)
print(task.id, task.overlap)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[patch_task()](../reference/toloka.client.TolokaClient.patch_task.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [{#T}](./get-tasks.md)
- [Toloka-Kit: Task class](../reference/toloka.client.task.Task.md)
- [Toloka API: Edit task](https://toloka.ai/docs/api/api-reference/#patch-/tasks/-id-)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*patch_task]: [patch_task()](../reference/toloka.client.TolokaClient.patch_task.md) method