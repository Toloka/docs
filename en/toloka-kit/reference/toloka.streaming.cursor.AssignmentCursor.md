# AssignmentCursor
`toloka.streaming.cursor.AssignmentCursor` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/streaming/cursor.py#L245)

```python
AssignmentCursor(
    self,
    toloka_client: Union[TolokaClient, AsyncTolokaClient],
    event_type: Any,
    status: Union[str, Assignment.Status, List[Union[str, Assignment.Status]], None] = None,
    task_id: Optional[str] = None,
    task_suite_id: Optional[str] = None,
    pool_id: Optional[str] = None,
    user_id: Optional[str] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    created_lt: Optional[datetime] = None,
    created_lte: Optional[datetime] = None,
    created_gt: Optional[datetime] = None,
    created_gte: Optional[datetime] = None,
    submitted_lt: Optional[datetime] = None,
    submitted_lte: Optional[datetime] = None,
    submitted_gt: Optional[datetime] = None,
    submitted_gte: Optional[datetime] = None,
    accepted_lt: Optional[datetime] = None,
    accepted_lte: Optional[datetime] = None,
    accepted_gt: Optional[datetime] = None,
    accepted_gte: Optional[datetime] = None,
    rejected_lt: Optional[datetime] = None,
    rejected_lte: Optional[datetime] = None,
    rejected_gt: Optional[datetime] = None,
    rejected_gte: Optional[datetime] = None,
    skipped_lt: Optional[datetime] = None,
    skipped_lte: Optional[datetime] = None,
    skipped_gt: Optional[datetime] = None,
    skipped_gte: Optional[datetime] = None,
    expired_lt: Optional[datetime] = None,
    expired_lte: Optional[datetime] = None,
    expired_gt: Optional[datetime] = None,
    expired_gte: Optional[datetime] = None,
    time_lag: timedelta = ...
)
```

Iterator over Assignment objects of selected AssignmentEventType.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`toloka_client`|**Union\[[TolokaClient](toloka.client.TolokaClient.md), [AsyncTolokaClient](toloka.async_client.client.AsyncTolokaClient.md)\]**|<p>TolokaClient object that is being used to search assignments.</p>
`event_type`|**Any**|<p>Assignments event&#x27;s type to search.</p>
`request`|**[AssignmentSearchRequest](toloka.client.search_requests.AssignmentSearchRequest.md)**|<p>Base request to search assignments by.</p>
`_time_lag`|**-**|<p>Time lag between cursor time field upper bound and real time. Default is 1 minute. This lag is required to keep cursor consistent. Lowering this value will make cursor process events faster, but raises probability of missing some events in case of concurrent operations.</p>

**Examples:**

Iterate over assignment acceptances events.

```python
it = AssignmentCursor(pool_id='123', event_type='ACCEPTED', toloka_client=toloka_client)
current_events = list(it)
# ... new events may occur ...
new_events = list(it)  # Contains only new events, occured since the previous call.
```
