# Create pool

_Create a pool in a project in Toloka._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Specify pool parameters {#step-three}

First, specify the parameters you want your pool to have. In this example, we use the following pool settings:

- the ID of the project in which the pool is created, [find it out](./get-projects.md) before creating the pool
- the pool name you will see in the list and use to distinguish the pool from other ones
- whether or not the pool can contain adult content
- the date when the pool is going to expire and will be closed
- the reward for the task suite specified in U.S. dollars
- the maximum duration of the task suite completion available to Tolokers
- whether or not the responses must be accepted automatically rather than reviewed manually
- the overlap used for the pool

You can choose your own values or have your own set of the pool parameters. Refer to the [Pool](../reference/toloka.client.pool.Pool.md) class page for more details.

```python
from datetime import datetime

new_pool = toloka.pool.[Pool](*Pool)(
    project_id='83859',
    private_name='First pool',
    may_contain_adult_content=False,
    will_expire=datetime(2030, 1, 1),
    reward_per_assignment=0.05,
    assignment_max_duration_seconds=60*5,
    auto_accept_solutions=False,
    defaults=toloka.pool.Pool.Defaults(default_overlap_for_new_task_suites=1)
)
```

{% note alert "Important" %}

All the code manipulations at step 3 occur in your device memory. The data will only be sent to the server after calling the `create_pool()` method at [step 4](#step-four).

{% endnote %}

### 4. Create pool on platform {#step-four}

This actually creates a pool in Toloka.

```python
new_pool = toloka_client.[create_pool](*create_pool)(new_pool)
```

### 5. Print created pool ID {#step-five}

The `create_pool()` request will return the [Pool](../reference/toloka.client.pool.Pool.md) class object. You can use its attributes to print the information you need.

```python
print(new_pool.id)
```

You should get an output with the created pool ID which looks like this.

```bash
1440972
```

## Complete code: Create pool {#complete-code}

```python
import toloka.client as toloka
from datetime import datetime

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

new_pool = toloka.pool.Pool(
    project_id='83859',
    private_name='First pool',
    may_contain_adult_content=False,
    will_expire=datetime(2030, 1, 1),
    reward_per_assignment=0.05,
    assignment_max_duration_seconds=60*5,
    auto_accept_solutions=False,
    defaults=toloka.pool.Pool.Defaults(default_overlap_for_new_task_suites=1)
)
new_pool = toloka_client.create_pool(new_pool)
print(new_pool.id)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[Pool](../reference/toloka.client.pool.Pool.md) class_
- _[create_pool()](../reference/toloka.client.TolokaClient.create_pool.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [{#T}](./get-projects.md)
- [Toloka API: Create pool](https://toloka.ai/docs/api/api-reference/#post-/pools)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*Pool]: [Pool](../reference/toloka.client.pool.Pool.md) class
[*create_pool]: [create_pool()](../reference/toloka.client.TolokaClient.create_pool.md) method