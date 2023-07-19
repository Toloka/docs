# Send messages

_Compose and send messages to single or multiple recipients in Toloka._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Send message to Tolokers {#step-three}

Now compose a message for Tolokers. For this, you need the following information:

- the message text and topic
- whether the recipients can reply to the message or not

You also need to select the message recipients. If you choose to send the message to all the Tolokers, you will simply need to set the `recipients_select_type` value to `'DIRECT'`. Otherwise, you will need to specify the IDs of the Tolokers whom you want to receive the message.

```python
message_thread = toloka_client.[compose_message_thread](*compose_message_thread)(
    recipients_select_type='DIRECT',
    recipients_ids=['1ad097faba0eff85a04fe30bc04d53db'],
    topic={'EN': 'Thank you!'},
    text={'EN': 'Amazing job! We have just trained our first model.'},
    answerable=False
)
```

### 4. Display sent message info {#step-four}

The `compose_message_thread()` request will return the [MessageThread](../reference/toloka.client.message_thread.MessageThread.md) class object. You can use its attributes to print the information you need.

```python
print(message_thread.id, message_thread.topic.get('EN') or list(message_thread.topic.values())[0])
```

You should get an output with the message ID and topic which looks like this.

```bash
63c15866757a4a1adad1d632 Thank you!
```

## Complete code: Send messages {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

message_thread = toloka_client.compose_message_thread(
    recipients_select_type='DIRECT',
    recipients_ids=['1ad097faba0eff85a04fe30bc04d53db'],
    topic={'EN': 'Thank you!'},
    text={'EN': 'Amazing job! We have just trained our first model.'},
    answerable=True
)
print(message_thread.id, message_thread.topic.get('EN') or list(message_thread.topic.values())[0])
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[compose_message_thread()](../reference/toloka.client.TolokaClient.compose_message_thread.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [Toloka-Kit: MessageThread class](../reference/toloka.client.message_thread.MessageThread.md)
- [Toloka API: Send message](https://toloka.ai/docs/api/api-reference/#post-/message-threads/compose)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*compose_message_thread]: [compose_message_thread()](../reference/toloka.client.TolokaClient.compose_message_thread.md) method