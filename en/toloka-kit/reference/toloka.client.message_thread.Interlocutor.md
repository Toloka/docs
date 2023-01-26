# Interlocutor
`toloka.client.message_thread.Interlocutor` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/message_thread.py#L47)

```python
Interlocutor(
    self,
    *,
    id: Optional[str] = None,
    role: Union[InterlocutorRole, str, None] = None,
    myself: Optional[bool] = None
)
```

Information about the sender or recipient.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>ID of the sender or recipient.</p>
`role`|**Optional\[[InterlocutorRole](toloka.client.message_thread.Interlocutor.InterlocutorRole.md)\]**|<p>Role of the sender or recipient in Toloka.</p>
`myself`|**Optional\[bool\]**|<p>Marks a sender or recipient with your ID. f the ID belongs to you, the value is specified true.</p>
