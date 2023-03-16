# Message
`toloka.client.message_thread.MessageThread.Message` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/message_thread.py#L121)

```python
Message(
    self,
    *,
    text: Optional[Dict[str, str]] = None,
    from_: Optional[Interlocutor] = None,
    created: Optional[datetime] = None
)
```

Message in the thread.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`text`|**Optional\[Dict\[str, str\]\]**|<p>Message text.</p>
`from_`|**Optional\[[Interlocutor](toloka.client.message_thread.Interlocutor.md)\]**|<p>Information about the sender.</p>
`created`|**Optional\[datetime\]**|<p>Date the message was created.</p>
