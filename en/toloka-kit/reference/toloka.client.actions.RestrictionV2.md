# RestrictionV2
`toloka.client.actions.RestrictionV2` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/actions.py#L70)

```python
RestrictionV2(
    self,
    *,
    scope: Union[UserRestriction.Scope, str, None] = None,
    duration: Optional[int] = None,
    duration_unit: Union[DurationUnit, str, None] = None,
    private_comment: Optional[str] = None
)
```

Restricts Toloker's access to projects or pools.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`scope`|**Union\[[UserRestriction.Scope](toloka.client.user_restriction.UserRestriction.Scope.md), str, None\]**|<ul> <li>`POOL` — A Toloker can&#x27;t access the pool if the action is applied.</li> <li>`PROJECT` — A Toloker can&#x27;t access the entire project containing the pool.</li> <li>`ALL_PROJECTS` — A Toloker can&#x27;t access any requester&#x27;s project.</li> </ul>
`duration`|**Optional\[int\]**|<p>The duration of the blocking period measured in `duration_unit`.</p>
`duration_unit`|**Union\[[DurationUnit](toloka.client.user_restriction.DurationUnit.md), str, None\]**|<ul> <li>`MINUTES`;</li> <li>`HOURS`;</li> <li>`DAYS`;</li> <li>`PERMANENT` — blocking is permanent. In this case the `duration` is ignored and may be omitted.</li> </ul>
`private_comment`|**Optional\[str\]**|<p>A private comment. It is visible only to the requester.</p>

**Examples:**

The following quality control rule blocks access to the project for 10 days, if a Toloker answers too fast.

```python
new_pool = toloka.client.pool.Pool()
new_pool.quality_control.add_action(
    collector=toloka.client.collectors.AssignmentSubmitTime(history_size=5, fast_submit_threshold_seconds=20),
    conditions=[toloka.client.conditions.FastSubmittedCount > 1],
    action=toloka.client.actions.RestrictionV2(
        scope='PROJECT',
        duration=10,
        duration_unit='DAYS',
        private_comment='Fast responses',
    )
)
```
