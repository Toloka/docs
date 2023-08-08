# Open pool

_Open a closed pool in Toloka._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Open pool {#step-three}

[Find out](get-pools.md) the ID of the pool you want to open. Then call the `open_pool()` method.

```python
opened_pool = toloka_client.[open_pool](*open_pool)('1442472')
```

### 4. Print pool ID and status {#step-four}

The `open_pool()` request will return the [Pool](../reference/toloka.client.pool.Pool.md) class object. You can use its attributes to print the information you need.

```python
print(opened_pool.id, opened_pool.status)
```

You should get an output with the pool ID and the updated status which looks like this.

```bash
1442472 Status.OPEN
```

## Complete code: Open pool {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealApiKey_Here', 'PRODUCTION')

opened_pool = toloka_client.open_pool('1442472')
print(opened_pool.id, opened_pool.status)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[open_pool()](../reference/toloka.client.TolokaClient.open_pool.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](get-pools.md)
- [Toloka-Kit: Pool class](../reference/toloka.client.pool.Pool.md)
- [Toloka API: Open pool](https://toloka.ai/docs/api/api-reference/#post-/pools/-id-/open)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*open_pool]: [open_pool()](../reference/toloka.client.TolokaClient.open_pool.md) method