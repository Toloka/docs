# SkillId
`toloka.client.conditions.SkillId` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/conditions.py#L467)

```python
SkillId(
    self,
    operator: IdentityOperator,
    value: Optional[str] = None
)
```

The ID of a changed skill which caused access blocking.


`SkillId` provides details if the [PoolAccessRevokedReason](toloka.client.conditions.PoolAccessRevokedReason.md) condition equals `SKILL_CHANGE`.

`SkillId` is used with collectors:
- [UsersAssessment](toloka.client.collectors.UsersAssessment.md)


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.quality_control.add_action(
    collector=toloka.client.collectors.UsersAssessment(),
    conditions=[toloka.client.conditions.PoolAccessRevokedReason ==
        toloka.client.conditions.PoolAccessRevokedReason.SKILL_CHANGE,
        toloka.client.conditions.SkillId == '11294'
    ],
    action=toloka.client.actions.ChangeOverlap(delta=1, open_pool=True),
)
```
