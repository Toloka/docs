# Create global skill

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

## Complete code: Create global skill

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

new_skill = toloka_client.create_skill(
    name = 'Programmer',
    public_name = {'EN': 'Programmer'},
    public_requester_description = {
        'EN': 'You are an expert in programming languages'
    }
)
print(new_skill.id)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class