# Interlocutor
`toloka.client.message_thread.Interlocutor` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/message_thread.py#L47)

```python
Interlocutor(
    self,
    *,
    id: Optional[str] = None,
    role: Union[InterlocutorRole, str, None] = None,
    myself: Optional[bool] = None
)
```

Information about a message sender or recipient.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the sender or recipient.</p>
`role`|**Optional\[[InterlocutorRole](toloka.client.message_thread.Interlocutor.InterlocutorRole.md)\]**|<p>The role in Toloka.</p>
`myself`|**Optional\[bool\]**|<p>A flag that is set to `True` when the ID is yours.</p>
