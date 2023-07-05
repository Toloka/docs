# Get pool details

_Get the detailed information about the pool with the ID specified in the request._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Get pool information {#step-three}

[Find out](get-pools.md) the ID of the pool for which you want to get the detailed information. Then get this info calling the `get_pool()` method.

```python
pool = toloka_client.[get_pool](*get_pool)('36545959')
```

### 4. Print pool private name, status, and last close reason {#step-four}

The `get_pool()` request will return the [Pool](../reference/toloka.client.pool.Pool.md) class object. You can use its attributes to print the information you need.

```python
print(pool.private_name, pool.status, pool.last_close_reason)
```

You should get an output with the pool private name, status, and last close reason which looks like this.

```bash
Image classification Status.CLOSED CloseReason.NOT_ENOUGH_BALANCE
```

## Complete code: Get pool details {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealApiKey_Here', 'PRODUCTION')

pool = toloka_client.get_pool('36545959')
print(pool.private_name, pool.status, pool.last_close_reason)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_pool()](../reference/toloka.client.TolokaClient.get_pool.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](get-pools.md)
- [Toloka-Kit: Pool class](../reference/toloka.client.pool.Pool.md)
- [Toloka API: Get pool by ID](https://toloka.ai/docs/api/api-reference/#get-/pools/-id-)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_pool]: [get_pool()](../reference/toloka.client.TolokaClient.get_pool.md) method