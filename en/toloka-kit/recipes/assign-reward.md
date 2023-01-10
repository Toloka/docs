# Issue rewards to Tolokers

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

## Complete code: Issue rewards to Tolokers

```python
from decimal import Decimal
import toloka.client as toloka
from toloka.client.user_bonus import UserBonus

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

new_bonus = toloka_client.create_user_bonus(UserBonus(
    user_id='fac97860c7929add8048ed2ef63b66fd',
    amount=Decimal('0.50'),
    public_title={'EN': 'Perfect job!'},
    public_message={'EN': 'You are the best!'},
    assignment_id='00001092da--61ef030400c684132d0da0de'
))
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class