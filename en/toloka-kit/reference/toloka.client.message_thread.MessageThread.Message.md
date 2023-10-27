# Message
`toloka.client.message_thread.MessageThread.Message` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/message_thread.py#L123)

```python
Message(
    self,
    *,
    text: Optional[Dict[str, str]] = None,
    from_: Optional[Interlocutor] = None,
    created: Optional[datetime] = None
)
```

A message in a thread.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`text`|**Optional\[Dict\[str, str\]\]**|<p>The message text. The `text` is a dictionary with two letter language codes as keys.</p>
`from_`|**Optional\[[Interlocutor](toloka.client.message_thread.Interlocutor.md)\]**|<p>Information about the sender.</p>
`created`|**Optional\[datetime\]**|<p>The date and time when the message was created.</p>
