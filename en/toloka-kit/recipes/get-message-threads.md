# Get list of message threads

_Get the list of all the message threads present in a specific folder in your account._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Print message thread IDs and topics {#step-three}

Iterate through all the message threads calling the `get_message_threads()` method.

```python
for message_thread in toloka_client.[get_message_threads](*get_message_threads)(folder=['INBOX', 'UNREAD']):
    topic=message_thread.topic
    print(message_thread.id, topic.get('EN') or list(topic.values())[0])
```

You should get an output with the message thread IDs and topics which looks like this.

```bash
63c00f08138adb3ab310b2a5 Perfect job!
63c1573b138adb3ab310b2af Thank you!
```

## Complete code: Get list of message threads {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

for message_thread in toloka_client.get_message_threads(folder=['INBOX', 'UNREAD']):
    topic=message_thread.topic
    print(message_thread.id, topic.get('EN') or list(topic.values())[0])
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[get_message_threads()](../reference/toloka.client.TolokaClient.get_message_threads.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [Toloka API:  Get list of message threads](https://toloka.ai/docs/api/api-reference/#get-/message-threads)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*get_message_threads]: [get_message_threads()](../reference/toloka.client.TolokaClient.get_message_threads.md) method