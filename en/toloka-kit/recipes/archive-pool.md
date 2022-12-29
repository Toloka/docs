# Archive pool

_Move the pool which isn't in use into archive._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Archive pool

[Find out](./get-pools.md) the ID of the pool you want to archive. Then call the `archive_pool()` method.

```python
toloka_client.[archive_pool](*archive_pool)('32267581')
```

If everything goes well, the request will return an empty response.

## Complete code: Archive pool

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

toloka_client.archive_pool('32267581')
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[archive_pool](../reference/toloka.client.TolokaClient.archive_pool.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [{#T}](../../guide/concepts/pool-archive.md)
- [Toloka-Kit recipe: Get list of pools](./get-pools.md)
- [Toloka API: Archive pool](https://toloka.ai/docs/api/api-reference/#post-/pools/-id-/archive)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*archive_pool]: [archive_pool](../reference/toloka.client.TolokaClient.archive_pool.md) method