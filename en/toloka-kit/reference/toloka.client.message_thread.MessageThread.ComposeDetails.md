# ComposeDetails
`toloka.client.message_thread.MessageThread.ComposeDetails` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/message_thread.py#L105)

```python
ComposeDetails(
    self,
    *,
    recipients_select_type: Union[RecipientsSelectType, str, None] = None,
    recipients_ids: Optional[List[str]] = None,
    recipients_filter: Optional[FilterCondition] = None
)
```

The details of selecting recipients.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`recipients_select_type`|**Optional\[[RecipientsSelectType](toloka.client.message_thread.RecipientsSelectType.md)\]**|<p>The way of specifying message recipients.</p>
`recipients_ids`|**Optional\[List\[str\]\]**|<p>A list of Toloker IDs. It is filled if `recipients_select_type` is `DIRECT`.</p>
`recipients_filter`|**Optional\[[FilterCondition](toloka.client.filter.FilterCondition.md)\]**|<p>A filter for selecting Tolokers. It is set if `recipients_select_type` is `FILTER`.</p>
