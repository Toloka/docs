# MessageThreadCursor
`toloka.streaming.cursor.MessageThreadCursor` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/streaming/cursor.py#L438)

```python
MessageThreadCursor(
    self,
    toloka_client: Union[TolokaClient, AsyncTolokaClient],
    time_lag: timedelta = ...,
    folder: Union[str, Folder, List[Union[str, Folder]], None] = None,
    folder_ne: Union[str, Folder, List[Union[str, Folder]], None] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    created_lt: Optional[datetime] = None,
    created_lte: Optional[datetime] = None,
    created_gt: Optional[datetime] = None,
    created_gte: Optional[datetime] = None
)
```

Iterator over messages by create time.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`toloka_client`|**Union\[[TolokaClient](toloka.client.TolokaClient.md), [AsyncTolokaClient](toloka.async_client.client.AsyncTolokaClient.md)\]**|<p>TolokaClient object that is being used to search messages.</p>
`request`|**[MessageThreadSearchRequest](toloka.client.search_requests.MessageThreadSearchRequest.md)**|<p>Base request to search messages.</p>
`_time_lag`|**-**|<p>Time lag between cursor time field upper bound and real time. Default is 1 minute. This lag is required to keep cursor consistent. Lowering this value will make cursor process events faster, but raises probability of missing some events in case of concurrent operations.</p>

**Examples:**

Iterate over all messages.

```python
it = MessageThreadCursor(toloka_client=toloka_client)
all_messages = list(it)
# ... new messages could appear ...
new_messages = list(it)  # Contains only new messages, appeared since the previous call.
```
