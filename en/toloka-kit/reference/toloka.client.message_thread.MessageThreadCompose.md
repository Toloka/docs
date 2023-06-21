# MessageThreadCompose
`toloka.client.message_thread.MessageThreadCompose` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/message_thread.py#L173)

```python
MessageThreadCompose(
    self,
    *,
    recipients_select_type: Union[RecipientsSelectType, str, None] = None,
    topic: Optional[Dict[str, str]] = None,
    text: Optional[Dict[str, str]] = None,
    answerable: Optional[bool] = None,
    recipients_ids: Optional[List[str]] = None,
    recipients_filter: Optional[FilterCondition] = None
)
```

Parameters for creating a message thread with the first message.


The `topic` and `text` parameters are dictionaries.
Two letter language code is a key in the dictionaries. If available, the text in a Toloker preferred language is used.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`recipients_select_type`|**Optional\[[RecipientsSelectType](toloka.client.message_thread.RecipientsSelectType.md)\]**|<p>The way of specifying message recipients.</p>
`topic`|**Optional\[Dict\[str, str\]\]**|<p>The message thread title.</p>
`text`|**Optional\[Dict\[str, str\]\]**|<p>The message text.</p>
`answerable`|**Optional\[bool\]**|<ul> <li>`True` — Tolokers can respond to your messages.</li> <li>`False` — Tolokers can&#x27;t respond to your messages.</li> </ul>
`recipients_ids`|**Optional\[List\[str\]\]**|<p>A list of Toloker IDs. It is filled if `recipients_select_type` is `DIRECT`.</p>
`recipients_filter`|**Optional\[[FilterCondition](toloka.client.filter.FilterCondition.md)\]**|<p>A filter for selecting Tolokers. It is set if `recipients_select_type` is `FILTER`.</p>
