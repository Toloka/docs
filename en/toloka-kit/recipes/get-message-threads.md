# Get list of message threads

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

## Complete code: Get list of message threads

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE', 'PRODUCTION')

for message_thread in toloka_client.get_message_threads(folder=['INBOX', 'UNREAD']):
    topic=message_thread.topic
    print(topic.get('EN') or list(topic.values())[0])
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class