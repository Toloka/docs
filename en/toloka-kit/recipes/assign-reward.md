# Issue bonuses to Tolokers

_Additionally reward Tolokers who completed their tasks better than others._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Issue bonus to Toloker {#step-three}

Now create the bonus for the Toloker. For this, you need the following information:

- the ID of the Toloker you want to give the bonus to
- the bonus amount in U.S. dollars
- a public title and a message the Toloker will receive together with the bonus
- the ID of the Toloker response for which you assign the bonus

```python
from decimal import Decimal

new_bonus = toloka_client.[create_user_bonus](*create_user_bonus)(toloka.user_bonus.[UserBonus](*UserBonus)(
    user_id='a1b0b42923c429daa2c764d7ccfc364d',
    amount=Decimal('0.50'),
    public_title={'EN': 'Perfect job!'},
    public_message={'EN': 'You are the best!'},
    assignment_id='000015fccc--63bfc4c358d7a46c32a7b233'
))
```

### 4. Display issued bonus info {#step-four}

The `create_user_bonus()` request will return the [UserBonus](../reference/toloka.client.user_bonus.UserBonus.md) class object. You can use its attributes to print the information you need.

```python
print(new_bonus.created)
```

You should get an output with the date and time when you issued the bonus which looks like this.

```bash
2023-01-12 13:45:36.767000+00:00
```

## Complete code: Issue bonuses to Tolokers {#complete-code}

```python
from decimal import Decimal
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

new_bonus = toloka_client.create_user_bonus(toloka.user_bonus.UserBonus(
    user_id='a1b0b42923c429daa2c764d7ccfc364d',
    amount=Decimal('0.50'),
    public_title={'EN': 'Perfect job!'},
    public_message={'EN': 'You are the best!'},
    assignment_id='000015fccc--63bfc4c358d7a46c32a7b233'
))
print(new_bonus.created)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[create_user_bonus()](../reference/toloka.client.TolokaClient.create_user_bonus.md) method_
- _[UserBonus](../reference/toloka.client.user_bonus.UserBonus.md) class_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [Toloka API: Issue bonuses](https://toloka.ai/docs/api/api-reference/#post-/user-bonuses)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*create_user_bonus]: [create_user_bonus()](../reference/toloka.client.TolokaClient.create_user_bonus.md) method
[*UserBonus]: [UserBonus](../reference/toloka.client.user_bonus.UserBonus.md) class