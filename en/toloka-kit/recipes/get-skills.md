# Get skills

_Get all the skills available in your Toloka account._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Print skill IDs, names, and private comments {#step-three}

Iterate through all the skills calling the `get_skills()` method.

```python
for skill in toloka_client.[get_skills](*get_skills)():
    print(skill.id, skill.name, skill.private_comment)
```

You should get an output with the skill IDs, names, and private comments which looks like this.

```bash
12648 Programmer Got at least 5 right responses on control tasks with C++ or Python
37825 product search relevance
56673 my skill
```

## Complete code: Get skills {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

for skill in toloka_client.get_skills():
    print(skill.id, skill.name, skill.private_comment)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_skills()](../reference/toloka.client.TolokaClient.get_skills.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [Toloka API: Get list of skills](https://toloka.ai/docs/api/api-reference/#get-/skills)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_skills]: [get_skills()](../reference/toloka.client.TolokaClient.get_skills.md) method