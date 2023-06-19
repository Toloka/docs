# compose_message_thread
`toloka.async_client.client.AsyncTolokaClient.compose_message_thread` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L0)

Creates a message thread and sends the first thread message to Tolokers.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`recipients_select_type`|**Union\[[RecipientsSelectType](toloka.client.message_thread.RecipientsSelectType.md), str, None\]**|<p>The way of specifying message recipients.</p>
`topic`|**Optional\[Dict\[str, str\]\]**|<p>The message thread title.</p>
`text`|**Optional\[Dict\[str, str\]\]**|<p>The message text.</p>
`answerable`|**Optional\[bool\]**|<ul> <li>`True` — Tolokers can respond to your messages.</li> <li>`False` — Tolokers can&#x27;t respond to your messages.</li> </ul>
`recipients_ids`|**Optional\[List\[str\]\]**|<p>A list of Toloker IDs. It is filled if `recipients_select_type` is `DIRECT`.</p>
`recipients_filter`|**Optional\[[FilterCondition](toloka.client.filter.FilterCondition.md)\]**|<p>A filter for selecting Tolokers. It is set if `recipients_select_type` is `FILTER`.</p>

* **Returns:**

  The created message thread.

* **Return type:**

  [MessageThread](toloka.client.message_thread.MessageThread.md)

**Examples:**

A message is sent to all Tolokers who have tried to complete your tasks.
The message is in english. Tolokers can't reply to your message.

```python
message_text = "Amazing job! We've just trained our first model with the data you prepared for us. Thank you!"
toloka_client.compose_message_thread(
    recipients_select_type='ALL',
    topic={'EN': 'Thank you!'},
    text={'EN': message_text},
    answerable=False
)
```
