# Archive pool

_Move the pool which you no longer use into archive._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Archive pool {#step-three}

[Find out](get-pools.md) the ID of the pool you want to archive. Then call the `archive_pool()` method.

```python
archived_pool = toloka_client.[archive_pool](*archive_pool)('1443992')
```

### 4. Print pool ID and status {#step-four}

The `archive_pool()` request will return the [Pool](../reference/toloka.client.pool.Pool.md) class object. You can use its attributes to print the information you need.

```python
print(archived_pool.id, archived_pool.status)
```

You should get an output with the pool ID and the updated status which looks like this.

```bash
1443992 Status.ARCHIVED
```

## Complete code: Archive pool {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealApiKey_Here', 'PRODUCTION')

archived_pool = toloka_client.archive_pool('1443992')
print(archived_pool.id, archived_pool.status)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[archive_pool()](../reference/toloka.client.TolokaClient.archive_pool.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](../../guide/concepts/pool-archive.md)
- [{#T}](get-pools.md)
- [Toloka-Kit: Pool class](../reference/toloka.client.pool.Pool.md)
- [Toloka API: Archive pool](https://toloka.ai/docs/api/api-reference/#post-/pools/-id-/archive)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*archive_pool]: [archive_pool()](../reference/toloka.client.TolokaClient.archive_pool.md) method