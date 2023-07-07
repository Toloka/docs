# Change pool priority

_Change the priority of the pool and offer it to Tolokers before other pools._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Change pool priority {#step-three}

[Find out](./get-pools.md) the ID of the pool for which you want to change the priority. Then call the `patch_pool()` method.

```python
patched_pool = toloka_client.[patch_pool](*patch_pool)(pool_id='1443815', priority=0)
```

### 4. Print pool ID and priority {#step-four}

The `patch_pool()` request will return the [Pool](../reference/toloka.client.pool.Pool.md) class object. You can use its attributes to print the information you need.

```python
print(patched_pool.id, patched_pool.priority)
```

You should get an output with the pool ID and the updated priority which looks like this.

```bash
1443815 0
```

## Complete code: Change pool priority {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

patched_pool = toloka_client.patch_pool(pool_id='1443815', priority=0)
print(patched_pool.id, patched_pool.priority)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[patch_pool()](../reference/toloka.client.TolokaClient.patch_pool.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [{#T}](./get-pools.md)
- [Toloka-Kit: Pool class](../reference/toloka.client.pool.Pool.md)
- [Toloka API: Change pool priority](https://toloka.ai/docs/api/api-reference/#patch-/pools/-id-)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*patch_pool]: [patch_pool()](../reference/toloka.client.TolokaClient.patch_pool.md) method