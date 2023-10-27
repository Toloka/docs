# Restriction
`toloka.client.actions.Restriction` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/actions.py#L38)

```python
Restriction(
    self,
    *,
    scope: Union[UserRestriction.Scope, str, None] = None,
    duration_days: Optional[int] = None,
    private_comment: Optional[str] = None
)
```

Restricts Toloker's access to projects or pools.


To have better control over restriction period use [RestrictionV2](toloka.client.actions.RestrictionV2.md).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`scope`|**Union\[[UserRestriction.Scope](toloka.client.user_restriction.UserRestriction.Scope.md), str, None\]**|<ul> <li>`POOL` — A Toloker can&#x27;t access the pool if the action is applied.</li> <li>`PROJECT` — A Toloker can&#x27;t access the entire project containing the pool.</li> <li>`ALL_PROJECTS` — A Toloker can&#x27;t access any requester&#x27;s project.</li> </ul>
`duration_days`|**Optional\[int\]**|<p>A blocking period in days. If the `duration_days` is omitted, then the block is permanent.</p>
`private_comment`|**Optional\[str\]**|<p>A private comment. It is visible only to the requester.</p>

**Examples:**


```python
new_pool = toloka.client.pool.Pool()    # pool creation is simplified
new_pool.quality_control.add_action(
    collector=toloka.client.collectors.AssignmentSubmitTime(history_size=5, fast_submit_threshold_seconds=20),
    conditions=[toloka.client.conditions.FastSubmittedCount > 1],
    action=toloka.client.actions.Restriction(
        scope='PROJECT',
        duration_days=10,
    )
)
```
