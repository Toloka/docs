# reply_message_thread
`toloka.client.TolokaClient.reply_message_thread` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L1041)

```python
reply_message_thread(
    self,
    message_thread_id: str,
    reply: MessageThreadReply
)
```

Sends a reply message in a thread.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`message_thread_id`|**str**|<p>The ID of the thread.</p>
`reply`|**[MessageThreadReply](toloka.client.message_thread.MessageThreadReply.md)**|<p>The reply message.</p>

* **Returns:**

  The updated message thread.

* **Return type:**

  [MessageThread](toloka.client.message_thread.MessageThread.md)

**Examples:**

Sending a reply to all unread messages.

```python
message_threads = toloka_client.get_message_threads(folder='UNREAD')
message_reply = {'EN': 'Thank you for your message! I will get back to you soon.'}
for thread in message_threads:
    toloka_client.reply_message_thread(
        message_thread_id=thread.id,
        reply=toloka.client.message_thread.MessageThreadReply(text=message_reply)
    )
```
