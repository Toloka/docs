# Get list of bans

_Get the list of all the Toloker bans._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Print ban IDs, Toloker IDs, and creation dates {#step-three}

Iterate through all the bans calling the `get_user_restrictions()` method. Specify the scope which was used to restrict the Toloker access:

- `ALL_PROJECTS` includes the Tolokers which have been banned from accessing all your projects.
- `PROJECT` includes the Tolokers which have been banned from accessing a single project. Specify the project ID as an argument: `project_id='120798'`.
- `POOL` includes the Tolokers which have been banned from accessing a single project. Specify the pool ID as an argument: `pool_id='38955320'`.

```python
for restriction in toloka_client.[get_user_restrictions](*get_user_restrictions)(scope='PROJECT', project_id='120798'):
    print(restriction.id, restriction.user_id, restriction.created)
```

You should get an output with the ban IDs, Toloker IDs, and ban creation dates which looks like this.

```bash
163294518 19025b33f844331a1c2c7ff57ec520b0 2023-07-18 15:31:28.459000+00:00
163295269 240d5b7897f98c119cd892e34295587e 2023-07-18 15:41:02.992000+00:00
```

## Complete code: Get list of bans {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealApiKey_Here', 'PRODUCTION')

for restriction in toloka_client.get_user_restrictions(scope='PROJECT', project_id='120798'):
    print(restriction.id, restriction.user_id, restriction.created)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_user_restrictions()](../reference/toloka.client.TolokaClient.get_user_restrictions.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](../../guide/concepts/ban.md)
- [Toloka API: Get list of bans](https://toloka.ai/docs/api/api-reference/#get-/user-restrictions)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_user_restrictions]: [get_user_restrictions()](../reference/toloka.client.TolokaClient.get_user_restrictions.md) method