# TaskCursor
`toloka.streaming.cursor.TaskCursor` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/streaming/cursor.py#L293)

```python
TaskCursor(
    self,
    toloka_client: Union[TolokaClient, AsyncTolokaClient],
    time_lag: timedelta = ...,
    pool_id: Optional[str] = None,
    overlap: Optional[int] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    created_lt: Optional[datetime] = None,
    created_lte: Optional[datetime] = None,
    created_gt: Optional[datetime] = None,
    created_gte: Optional[datetime] = None,
    overlap_lt: Optional[int] = None,
    overlap_lte: Optional[int] = None,
    overlap_gt: Optional[int] = None,
    overlap_gte: Optional[int] = None
)
```

Iterator over tasks by create time.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`toloka_client`|**Union\[[TolokaClient](toloka.client.TolokaClient.md), [AsyncTolokaClient](toloka.async_client.client.AsyncTolokaClient.md)\]**|<p>TolokaClient object that is being used to search tasks.</p>
`request`|**[TaskSearchRequest](toloka.client.search_requests.TaskSearchRequest.md)**|<p>Base request to search tasks by.</p>
`_time_lag`|**-**|<p>Time lag between cursor time field upper bound and real time. Default is 1 minute. This lag is required to keep cursor consistent. Lowering this value will make cursor process events faster, but raises probability of missing some events in case of concurrent operations.</p>

**Examples:**

Iterate over tasks.

```python
it = TaskCursor(pool_id='123', toloka_client=toloka_client)
current_tasks = list(it)
# ... new tasks could appear ...
new_tasks = list(it)  # Contains only new tasks, appeared since the previous call.
```
