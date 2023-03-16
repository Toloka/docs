# Get list of all rewards issued

_Get all the rewards you issued in Toloka._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Print reward IDs, public titles, and amount {#step-three}

Iterate through all the rewards calling the `get_user_bonuses()` method.

```python
for bonus in toloka_client.[get_user_bonuses](*get_user_bonuses)():
    print(bonus.id, bonus.public_title.get('EN'), bonus.amount)
```

You should get an output with the reward IDs, public titles, and amount which looks like this.

```bash
3139 Perfect job! 0.500
3258 Completed much faster than others 1.000
```

## Complete code: Get list of all rewards issued {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

for bonus in toloka_client.get_user_bonuses():
    print(bonus.id, bonus.public_title.get('EN'), bonus.amount)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_user_bonuses()](../reference/toloka.client.TolokaClient.get_user_bonuses.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [Toloka API: Get list of rewards](https://toloka.ai/docs/api/api-reference/#get-/user-bonuses)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_user_bonuses]: [get_user_bonuses()](../reference/toloka.client.TolokaClient.get_user_bonuses.md) method