# Edit skill

_Modify an existing skill._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Get skill {#step-three}

[Find out](get-skills.md) the ID of the skill which you want to modify. Then create a local copy of the project object calling the `get_skill()` method.

```python
skill = toloka_client.[get_skill](*get_skill)('11294')
```

{% note alert "Important" %}

All the code manipulations at steps 3–4 occur in your device memory. The data will only be sent to the server after calling the `update_skill()` method at [step 5](#step-five).

{% endnote %}

### 4. Set skill new private comment {#step-four}

Specify a new private comment for the skill. You can choose to change some other skill data. Refer to the [Skill](../reference/toloka.client.skill.Skill.md) class to see what other attributes it has.

```python
skill.private_comment = 'Got at least 5 right responses on control tasks with C++ or Python'
```

### 5. Modify skill on platform {#step-five}

This actually updates the project data in Toloka.

```python
updated_skill = toloka_client.[update_skill](*update_skill)(skill.id, skill)
```

### 6. Display modifications {#step-six}

The `update_skill()` request will return the [Skill](../reference/toloka.client.skill.Skill.md) class object. You can use its attributes to print the information you need.

```python
print(updated_skill.id, updated_skill.private_comment)
```

You should get an output with the updated skill private comment which looks like this.

```bash
12648 Got at least 5 right responses on control tasks with C++ or Python
```

## Complete code: Edit skill {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealApiKey_Here', 'PRODUCTION')

skill = toloka_client.get_skill('11294')
skill.private_comment = 'Got at least 5 right responses on control tasks with C++ or Python'

updated_skill = toloka_client.update_skill(skill.id, skill)
print(updated_skill.id, updated_skill.private_comment)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_skill()](../reference/toloka.client.TolokaClient.get_skill.md) method_
- _[update_skill()](../reference/toloka.client.TolokaClient.update_skill.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](get-skills.md)
- [Toloka-Kit: Skill class](../reference/toloka.client.skill.Skill.md)
- [Toloka API: Update skill](https://toloka.ai/docs/api/api-reference/#put-/skills/-id-)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_skill]: [get_skill()](../reference/toloka.client.TolokaClient.get_skill.md) method
[*update_skill]: [update_skill()](../reference/toloka.client.TolokaClient.update_skill.md) method