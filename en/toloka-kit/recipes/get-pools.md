# Get list of pools

_Get the list of the pools with the `CLOSED` status in your project._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. List pools

[Find out](./get-projects.md) the ID of the project for which you want to get all the pools with the `CLOSED` status. Then iterate through all the pools calling the `get_pools()` method.

```python
for pool in toloka_client.[get_pools](*get_pools)(project_id='118252', status='CLOSED'):
  print(pool.id, pool.status, pool.private_name)
```

You should get an output that contains the IDs of the pools, their statuses, and private names. It will look like this.

```bash
36502086 Status.CLOSED Pool 1
36756115 Status.CLOSED Pool 2
```

## Complete code: Get list of pools

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

for pool in toloka_client.get_pools(project_id='118252', status='CLOSED'):
  print(pool.id, pool.status, pool.private_name)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_pools](../reference/toloka.client.TolokaClient.get_pools.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [Toloka-Kit recipe: Get list of projects](./get-projects.md)
- [Toloka API: Get list of pools](https://toloka.ai/docs/api/api-reference/#get-/pools)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_pools]: [get_pools](../reference/toloka.client.TolokaClient.get_pools.md) method