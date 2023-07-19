# Get list of tasks

_Get all the tasks in the pool with the ID specified in the request._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Print task IDs, creation date, and overlap {#step-three}

[Find out](get-pools.md) the ID of the pool you want to view the tasks in. Then, iterate through all the tasks in the pool calling the `get_tasks()` method.

```python
for task in toloka_client.[get_tasks](*get_tasks)(pool_id='1227652'):
    print(task.id, task.created.date(), task.overlap)
```

You should get an output with the skill IDs, names, and private comments which looks like this.

```bash
00022da5a7--6388b40547c84000494cdc58 2022-12-01 3
00022da5a7--6388b40547c84000494cdc59 2022-12-01 3
00022da5a7--6388b40547c84000494cdc5a 2022-12-01 5
00022da5a7--6388b40547c84000494cdc5b 2022-12-01 3
00022da5a7--6388b40547c84000494cdc60 2022-12-01 3
00022da5a7--6388b40547c84000494cdc6b 2022-12-01 3
```

## Complete code: Get list of tasks {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

for task in toloka_client.get_tasks(pool_id='1227652'):
    print(task.id, task.created.date(), task.overlap)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_tasks()](../reference/toloka.client.TolokaClient.get_tasks.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](get-pools.md)
- [Toloka API: Get list of tasks](https://toloka.ai/docs/api/api-reference/#get-/tasks)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_tasks]: [get_tasks()](../reference/toloka.client.TolokaClient.get_tasks.md) method