# Clone pool

_Create a copy of an existing pool preserving the main parameters._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Clone pool {#step-three}

[Find out](get-pools.md) the ID of the pool which you want to clone. Then clone this pool calling the `clone_pool()` method.

```python
cloned_pool = toloka_client.[clone_pool](*clone_pool)('32267581')
```

### 4. Print created pool ID {#step-four}

The `clone_pool()` request will return the [Pool](../reference/toloka.client.pool.Pool.md) class object. You can use its attributes to print the information you need.

```python
print(new_pool.id)
```

You should get an output with the created pool ID which looks like this.

```bash
1440972
```

## Complete code: Clone pool {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealApiKey_Here', 'PRODUCTION')

cloned_pool = toloka_client.clone_pool('32267581')
print(cloned_pool.id)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[clone_pool()](../reference/toloka.client.TolokaClient.clone_pool.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](get-pools.md)
- [Toloka-Kit: Pool class](../reference/toloka.client.pool.Pool.md)
- [Toloka API: Clone pool](https://toloka.ai/docs/api/api-reference/#post-/pools/-id-/clone)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*clone_pool]: [clone_pool()](../reference/toloka.client.TolokaClient.clone_pool.md) method