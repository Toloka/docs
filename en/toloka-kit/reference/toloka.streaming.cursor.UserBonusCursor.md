# UserBonusCursor
`toloka.streaming.cursor.UserBonusCursor` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/streaming/cursor.py#L297)

```python
UserBonusCursor(
    self,
    toloka_client: Union[TolokaClient, AsyncTolokaClient],
    user_id: Optional[str] = None,
    assignment_id: Optional[str] = None,
    private_comment: Optional[str] = None,
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

Iterator over `UserBonus` instances by create time.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`toloka_client`|**Union\[[TolokaClient](toloka.client.TolokaClient.md), [AsyncTolokaClient](toloka.async_client.client.AsyncTolokaClient.md)\]**|<p>TolokaClient object that is being used to search `UserBonus` instances.</p>
`request`|**[UserBonusSearchRequest](toloka.client.search_requests.UserBonusSearchRequest.md)**|<p>Base request to search `UserBonus` instances by.</p>

**Examples:**

Iterate over `UserBonus` instances.

```python
it = UserBonusCursor(toloka_client=toloka_client)
current_bonuses = list(it)
# ... new `UserBonus` instances could appear ...
new_bonuses = list(it)  # Contains only new `UserBonus` instances, appeared since the previous call.
```
