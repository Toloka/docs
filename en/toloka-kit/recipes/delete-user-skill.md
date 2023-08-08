# Remove skill from Toloker

_Remove the skill from the Toloker using the ID of the "skill-Toloker" pair._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Remove Toloker skill {#step-three}

[Find out](get-user-skills.md#step-three) the ID of the "skill-Toloker" pair. This ID is unique for each Toloker having a skill assigned to them. Use the `delete_user_skill()` method to remove the skill from the Toloker.

```python
toloka_client.[delete_user_skill](*delete_user_skill)(user_skill_id='54116339')
```

If everything goes as expected, the request will return an empty response.

## Complete code: Remove skill from Toloker {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealApiKey_Here', 'PRODUCTION')

toloka_client.delete_user_skill(user_skill_id='54116339')
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[delete_user_skill()](../reference/toloka.client.TolokaClient.delete_user_skill.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](get-user-skills.md)
- [Toloka API: Remove skill from Toloker](https://toloka.ai/docs/api/api-reference/#delete-/user-skills/-id-)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*delete_user_skill]: [delete_user_skill()](../reference/toloka.client.TolokaClient.delete_user_skill.md) method