# Create skill

_Create a skill that you can assign to Tolokers._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Create skill {#step-three}

Create a skill specifying:

- the skill public visibility
- the skill short name for you to distinguish it from other skills
- the skill name visible to Tolokers in the selected languages
- the skill description for other Tolokers in the selected languages

You can choose your own values or have your own set of the skill parameters. Refer to the [Skill](../reference/toloka.client.skill.Skill.md) class page for more details.

```python
new_skill = toloka_client.[create_skill](*create_skill)(
    hidden=False,
    name='Programmer',
    public_name={'EN': 'Programmer'},
    public_requester_description={
        'EN': 'You are an expert in programming languages'
    }
)
```

### 4. Print created skill ID {#step-four}

The `create_skill()` request will return the [Skill](../reference/toloka.client.skill.Skill.md) class object. You can use its attributes to print the information you need.

```python
print(new_skill.id)
```

You should get an output with the created skill ID which looks like this.

```bash
12648
```

## Complete code: Create skill {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealApiKey_Here', 'PRODUCTION')

new_skill = toloka_client.create_skill(
    hidden=False,
    name='Programmer',
    public_name={'EN': 'Programmer'},
    public_requester_description={
        'EN': 'You are an expert in programming languages'
    }
)
print(new_skill.id)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[create_skill()](../reference/toloka.client.TolokaClient.create_skill.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [Toloka API: Create skill](https://toloka.ai/docs/api/api-reference/#post-/skills)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*create_skill]: [create_skill()](../reference/toloka.client.TolokaClient.create_skill.md) method