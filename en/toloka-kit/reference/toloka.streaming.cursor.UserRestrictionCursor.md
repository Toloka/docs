# UserRestrictionCursor
`toloka.streaming.cursor.UserRestrictionCursor` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/streaming/cursor.py#L369)

```python
UserRestrictionCursor(
    self,
    toloka_client: Union[TolokaClient, AsyncTolokaClient],
    scope: Optional[UserRestriction.Scope] = None,
    user_id: Optional[str] = None,
    project_id: Optional[str] = None,
    pool_id: Optional[str] = None,
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

Iterator over Toloker restrictions by create time.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`toloka_client`|**Union\[[TolokaClient](toloka.client.TolokaClient.md), [AsyncTolokaClient](toloka.async_client.client.AsyncTolokaClient.md)\]**|<p>TolokaClient object that is being used to search Toloker restrictions.</p>
`request`|**[UserRestrictionSearchRequest](toloka.client.search_requests.UserRestrictionSearchRequest.md)**|<p>Base request to search Toloker restrictions.</p>

**Examples:**

Iterate over Toloker restrictions in a project.

```python
it = UserRestrictionCursor(toloka_client=toloka_client, project_id=my_proj_id)
current_restrictions = list(it)
# ... new restrictions could appear ...
new_restrictions = list(it)  # Contains only new restrictions, appeared since the previous call.
```
