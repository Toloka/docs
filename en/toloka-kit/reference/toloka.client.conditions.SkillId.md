# SkillId
`toloka.client.conditions.SkillId` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/conditions.py#L297)

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

