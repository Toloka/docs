# List Tolokers with skills

_Get all the skills assigned to the Toloker with the ID specified in the request._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Print skill names, "skill-Toloker" pair IDs, and values {#step-three}

Get all the skills assigned to the selected Toloker using the `get_user_skills()` method. Then, iterate through all these found skills calling the `get_skill()` method.

```python
for user_skill in toloka_client.[get_user_skills](*get_user_skills)(user_id='fac97860c7929add8048ed2ef63b66fd'):
    skill = toloka_client.[get_skill](*get_skill)(user_skill.skill_id)
    print(skill.name, user_skill.id, user_skill.value)
```

You should get an output with the skill names, "skill-Toloker" pair IDs, and values which looks like this.

```bash
Product Search Relevance 54116339 70
Programmer 54132692 50
```

{% note tip %}

The "skill-Toloker" pair ID allows you to get or remove the skill assigned to a specific Toloker.

{% endnote %}

## Complete code: List Tolokers with skills {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

for user_skill in toloka_client.get_user_skills(user_id='fac97860c7929add8048ed2ef63b66fd'):
    skill = toloka_client.get_skill(user_skill.skill_id)
    print(skill.name, user_skill.id, user_skill.value)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_user_skills()](../reference/toloka.client.TolokaClient.get_user_skills.md) method_
- _[get_skill()](../reference/toloka.client.TolokaClient.get_skill.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [Toloka API: Get list of Toloker skills](https://toloka.ai/docs/api/api-reference/#get-/user-skills)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_user_skills]: [get_user_skills()](../reference/toloka.client.TolokaClient.get_user_skills.md) method
[*get_skill]: [get_skill()](../reference/toloka.client.TolokaClient.get_skill.md) method