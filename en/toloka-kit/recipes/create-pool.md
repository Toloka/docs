# Create pool

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

## Complete code: Create pool

```python
import toloka.client as toloka
from toloka.client.pool import Pool
from datetime import datetime

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

new_pool = Pool(
  project_id='83859',
  private_name='First pool',
  may_contain_adult_content=False,
  will_expire=datetime(2030, 1, 1),
  reward_per_assignment=0.05,
  assignment_max_duration_seconds=60*5,
  auto_accept_solutions=False,
  defaults=Pool.Defaults(default_overlap_for_new_task_suites=1)
)
new_pool = toloka_client.create_pool(new_pool)
print(new_pool.id)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [Toloka API: Create pool](https://toloka.ai/docs/api/api-reference/#post-/pools)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class