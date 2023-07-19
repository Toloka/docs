# Reply to message thread

_Send a reply to a message thread in Toloka._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Send reply to thread {#step-three}

[Find out](get-message-threads.md) the ID of the message thread you want to reply to. Then compose a reply using the [MessageThreadReply](../reference/toloka.client.message_thread.MessageThreadReply.md) class object for that.

```python
message_reply = toloka.message_thread.[MessageThreadReply](*MessageThreadReply)(text={'EN': 'Thank you!'})
response_to_thread = toloka_client.[reply_message_thread](*reply_message_thread)(
    message_thread_id='63c15cfd757a4a1adad1d633',
    reply=message_reply
)
```

### 4. Display sent reply info {#step-four}

The `reply_message_thread()` request will return the [MessageThread](../reference/toloka.client.message_thread.MessageThread.md) class object. You can use its attributes to print the information you need.

```python
print(response_to_thread.id, response_to_thread.created)
```

You should get an output with the message ID and creation time which looks like this.

```bash
63c15cfd757a4a1adad1d633 2023-01-13 13:36:13.894000+00:00
```

## Complete code: Reply to message thread {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

message_reply = toloka.message_thread.MessageThreadReply(text={'EN': 'Thank you!'})
response_to_thread = toloka_client.reply_message_thread(
    message_thread_id='63c15cfd757a4a1adad1d633',
    reply=message_reply
)
print(response_to_thread.id, response_to_thread.created)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[MessageThreadReply](../reference/toloka.client.message_thread.MessageThreadReply.md) class_
- _[reply_message_thread()](../reference/toloka.client.TolokaClient.reply_message_thread.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](get-message-threads.md)
- [Toloka-Kit: MessageThread class](../reference/toloka.client.message_thread.MessageThread.md)
- [Toloka API: Reply to message thread](https://toloka.ai/docs/api/api-reference/#post-/message-threads/-id-/reply)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*MessageThreadReply]: [MessageThreadReply](../reference/toloka.client.message_thread.MessageThreadReply.md) class
[*reply_message_thread]: [reply_message_thread()](../reference/toloka.client.TolokaClient.reply_message_thread.md) method