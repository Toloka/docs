# compose_message_thread
`toloka.client.TolokaClient.compose_message_thread` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/__init__.py#L896)

Sends a message to a Toloker.


The sent message is added to a new message thread.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`recipients_select_type`|**Union\[[RecipientsSelectType](toloka.client.message_thread.RecipientsSelectType.md), str, None\]**|<p>Method for specifying recipients</p>
`topic`|**Optional\[Dict\[str, str\]\]**|<p>Post title. You can provide a title in several languages (the message will come in the Toloker&#x27;s language). Format: &quot;&lt;language RU/EN/TR/ID/FR&gt;&quot;: &quot;&lt;topic text&gt;&quot;.</p>
`text`|**Optional\[Dict\[str, str\]\]**|<p>Message text. You can provide text in several languages (the message will come in the Toloker&#x27;s language). Format: &quot;&lt;language RU/EN/TR/ID/FR&gt;&quot;: &quot;&lt;message text&gt;&quot;.</p>
`answerable`|**Optional\[bool\]**|<p>Ability to reply to a message:</p> <ul> <li>`True` — The Toloker can respond to the message.</li> <li>`False` — The Toloker can&#x27;t respond to the message.</li> </ul>
`recipients_ids`|**Optional\[List\[str\]\]**|<p>List of IDs of Tolokers to whom the message will be sent.</p>
`recipients_filter`|**Optional\[[FilterCondition](toloka.client.filter.FilterCondition.md)\]**|<p>Filter to select recipients.</p>

* **Returns:**

  New created thread.

* **Return type:**

  [MessageThread](toloka.client.message_thread.MessageThread.md)

**Examples:**

If you want to thank Tolokers who have tried to complete your tasks, send them a nice message.

```python
message_text = "Amazing job! We've just trained our first model with the data YOU prepared for us. Thank you!"
toloka_client.compose_message_thread(
    recipients_select_type='ALL',
    topic={'EN': 'Thank you!'},
    text={'EN': message_text},
    answerable=False
)
```
