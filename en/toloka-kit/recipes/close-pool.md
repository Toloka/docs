# Close pool

_Close an opened pool in Toloka._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Close pool {#step-three}

[Find out](get-pools.md) the ID of the pool you want to close. Then call the `close_pool()` method.

```python
closed_pool = toloka_client.[close_pool](*close_pool)('1443858')
```

### 4. Print pool ID and status {#step-four}

The `close_pool()` request will return the [Pool](../reference/toloka.client.pool.Pool.md) class object. You can use its attributes to print the information you need.

```python
print(closed_pool.id, closed_pool.status)
```

You should get an output with the pool ID and the updated status which looks like this.

```bash
1443858 Status.CLOSED
```

## Complete code: Close pool {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

closed_pool = toloka_client.close_pool('1443858')
print(closed_pool.id, closed_pool.status)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[close_pool()](../reference/toloka.client.TolokaClient.close_pool.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](get-pools.md)
- [Toloka-Kit: Pool class](../reference/toloka.client.pool.Pool.md)
- [Toloka API: Close pool](https://toloka.ai/docs/api/api-reference/#post-/pools/-id-/close)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*close_pool]: [close_pool()](../reference/toloka.client.TolokaClient.close_pool.md) method