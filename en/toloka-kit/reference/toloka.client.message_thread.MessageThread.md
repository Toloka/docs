# MessageThread
`toloka.client.message_thread.MessageThread` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/message_thread.py#L77)

```python
MessageThread(
    self,
    *,
    id: Optional[str] = None,
    topic: Optional[Dict[str, str]] = None,
    interlocutors_inlined: Optional[bool] = None,
    interlocutors: Optional[List[Interlocutor]] = None,
    messages_inlined: Optional[bool] = None,
    messages: Optional[List[Message]] = None,
    meta: Optional[Meta] = None,
    answerable: Optional[bool] = None,
    folders: Optional[List[Folder]] = None,
    compose_details: Optional[ComposeDetails] = None,
    created: Optional[datetime] = None
)
```

A message thread.


A message thread is created when you send a new message. Then responses are placed to the thread.
Until the first response is received the message thread is in the `UNREAD` folder.

If the message has several recipients then a message thread is created for each recipient when they responds.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the thread.</p>
`topic`|**Optional\[Dict\[str, str\]\]**|<p>The message thread title. `topic` is a dictionary with two letter language codes as keys.</p>
`interlocutors_inlined`|**Optional\[bool\]**|<p>The way of accessing information about the sender and recipients:</p> <ul> <li>`True` — Information is available in the `interlocutors` list.</li> <li>`False` — Information is available on a separate request.</li> </ul>
`interlocutors`|**Optional\[List\[[Interlocutor](toloka.client.message_thread.Interlocutor.md)\]\]**|<p>A list with information about the sender and recipients, sorted by IDs.</p>
`messages_inlined`|**Optional\[bool\]**|<p>The way of accessing messages:</p> <ul> <li>`True` — The messages are in the `messages` list.</li> <li>`False` — The messages are available on a separate request.</li> </ul>
`messages`|**Optional\[List\[[Message](toloka.client.message_thread.MessageThread.Message.md)\]\]**|<p>A list with thread messages. The list is sorted by creation date: newer messages come first.</p>
`meta`|**Optional\[[Meta](toloka.client.message_thread.MessageThread.Meta.md)\]**|<p>Thread meta information.</p>
`answerable`|**Optional\[bool\]**|<ul> <li>`True` — Tolokers can respond to your messages.</li> <li>`False` — Tolokers can&#x27;t respond to your messages.</li> </ul>
`folders`|**Optional\[List\[[Folder](toloka.client.message_thread.Folder.md)\]\]**|<p>Folders containing the thread.</p>
`compose_details`|**Optional\[[ComposeDetails](toloka.client.message_thread.MessageThread.ComposeDetails.md)\]**|<p>The details of selecting recipients. This information is provided if the first message in the thread was yours.</p>
`created`|**Optional\[datetime\]**|<p>The date and time when the first message in the thread was created.</p>
