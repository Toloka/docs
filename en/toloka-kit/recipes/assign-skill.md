# Assign skill to Toloker

_Assign an existing skill to Tolokers an set its level._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Assign skill to Toloker {#step-three}

```python
from decimal import Decimal

user_skill = toloka_client.[set_user_skill](*set_user_skill)(
                user_id='1ad097faba0eff85a04fe30bc04d53db',
                skill_id='11051', value=Decimal(50)
)
```

### 4. Print created skill information {#step-four}

The `set_user_skill()` request will return the [UserSkill](../reference/toloka.client.user_skill.UserSkill.md) class object. You can use its attributes to print the information you need.

```python
print(user_skill.id, user_skill.skill_id, user_skill.user_id, user_skill.value)
```

You should get an output with the ID of the skill-Toloker pair (this allows [removing skills from Tolokers](./delete-user-skill.md) later), assigned skill ID, Toloker ID, and the skill level the Toloker received which looks like this.

```bash
54132692 12648 1ad097faba0eff85a04fe30bc04d53db 50
```

## Complete code: Create skill {#complete-code}

```python
import toloka.client as toloka
from decimal import Decimal

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

user_skill = toloka_client.set_user_skill(
                user_id='1ad097faba0eff85a04fe30bc04d53db',
                skill_id='12648', value=Decimal(50)
)
print(user_skill.id, user_skill.skill_id, user_skill.user_id, user_skill.value)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[set_user_skill()](../reference/toloka.client.TolokaClient.set_user_skill.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [Toloka-Kit: UserSkill class](../reference/toloka.client.user_skill.UserSkill.md)
- [Toloka API: Set skill](https://toloka.ai/docs/api/api-reference/#put-/user-skills)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*set_user_skill]: [set_user_skill()](../reference/toloka.client.TolokaClient.set_user_skill.md) method