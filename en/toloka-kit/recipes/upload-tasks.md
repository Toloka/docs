# Upload tasks

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

## Complete code: Upload tasks

```python
import toloka.client as toloka
from toloka.client.task import Task, BaseTask

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

control_task = Task(
            input_values = {'image': 'http://example.com/image_example.png'},
            known_solutions = [
              BaseTask.KnownSolution(output_values = {'result': 'pink'})
            ],
            infinite_overlap = True,
            pool_id = '1238218'
          )
toloka_client.create_task(control_task)

image_urls = [
  'http://example.com/image0.png',
  'http://example.com/image1.png',
  'http://example.com/image2.png',
]

tasks = [ Task(input_values = {'image': url}, pool_id='1238218')
          for url in image_urls ]
result = toloka_client.create_tasks(tasks,
          allow_defaults=True, skip_invalid_items=False)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class