# UserSkillCursor
`toloka.streaming.cursor.UserSkillCursor` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/streaming/cursor.py#L363)

```python
UserSkillCursor(
    self,
    toloka_client: Union[TolokaClient, AsyncTolokaClient],
    event_type: Any,
    user_id: Optional[str] = None,
    skill_id: Optional[str] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    created_lt: Optional[datetime] = None,
    created_lte: Optional[datetime] = None,
    created_gt: Optional[datetime] = None,
    created_gte: Optional[datetime] = None,
    modified_lt: Optional[datetime] = None,
    modified_lte: Optional[datetime] = None,
    modified_gt: Optional[datetime] = None,
    modified_gte: Optional[datetime] = None,
    time_lag: timedelta = ...
)
```

Iterator over UserSkillEvent objects of a selected event_type.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`toloka_client`|**Union\[[TolokaClient](toloka.client.TolokaClient.md), [AsyncTolokaClient](toloka.async_client.client.AsyncTolokaClient.md)\]**|<p>TolokaClient object that is being used to search skills.</p>
`event_type`|**Any**|<p>Skill event type to search.</p>
`request`|**[UserSkillSearchRequest](toloka.client.search_requests.UserSkillSearchRequest.md)**|<p>Base request to search skills by.</p>
`_time_lag`|**-**|<p>Time lag between cursor time field upper bound and real time. Default is 1 minute. This lag is required to keep cursor consistent. Lowering this value will make cursor process events faster, but raises probability of missing some events in case of concurrent operations.</p>

**Examples:**

Iterate over skills acceptances events.

```python
it = UserSkillCursor(event_type='MODIFIED', toloka_client=toloka_client)
current_events = list(it)
# ... new skills could be set ...
new_events = list(it)  # Contains only new events, occurred since the previous call.
```
