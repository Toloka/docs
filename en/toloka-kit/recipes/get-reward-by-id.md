# Get bonus details

_Get the detailed information about the bonus with the ID specified in the request._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Get bonus information {#step-three}

[Find out](./get-rewards.md) the ID of the bonus for which you want to get the detailed information. Then get this info calling the `get_user_bonus()` method.

```python
bonus = toloka_client.[get_user_bonus](*get_user_bonus)('3139')
```

### 4. Print bonus title and amount {#step-four}

The `get_user_bonus()` request will return the [UserBonus](../reference/toloka.client.user_bonus.UserBonus.md) class object. You can use its attributes to print the information you need.

```python
print(bonus.public_title['EN'], bonus.amount)
```

You should get an output with the bonus title and amount which looks like this.

```bash
Perfect job! 0.500
```

## Complete code: Get bonus details {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

bonus = toloka_client.get_user_bonus('3139')
print(bonus.public_title['EN'], bonus.amount)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_user_bonus()](../reference/toloka.client.TolokaClient.get_user_bonus.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [Toloka-Kit: UserBonus class](../reference/toloka.client.user_bonus.UserBonus.md)
- [Toloka API: Get bonus by ID](https://toloka.ai/docs/api/api-reference/#get-/user-bonuses/-userBonusId-)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_user_bonus]: [get_user_bonus()](../reference/toloka.client.TolokaClient.get_user_bonus.md) method
