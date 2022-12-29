# Group tasks in task suites

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

## Complete code: Group tasks in task suites

```python
import toloka.client as toloka
from toloka.client.task import Task
from toloka.client.task_suite import TaskSuite

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

tasks = [
  Task(input_values = {'image': 'http://example.com/image0.png'})
]
new_task_suite = TaskSuite(pool_id='1238218', tasks=tasks, overlap=3)
new_task_suite = toloka_client.create_task_suite(new_task_suite)
print(new_task_suite.id)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class