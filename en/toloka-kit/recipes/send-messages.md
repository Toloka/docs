# Send messages

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

## Complete code: Send messages

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

message_text = "Amazing job! We have just trained our first model."
toloka_client.compose_message_thread(
    recipients_select_type='ALL',
    topic={'EN': 'Thank you!'},
    text={'EN': message_text},
    answerable=False
)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class