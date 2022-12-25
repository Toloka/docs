# PoolAccessRevokedReason
`toloka.client.conditions.PoolAccessRevokedReason` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/conditions.py#L252)

```python
PoolAccessRevokedReason(
    self,
    operator: IdentityOperator,
    value: Union[Type, str, None] = None
)
```

The reason why a Toloker has lost access to a pool.


Possible values:
    * `SKILL_CHANGE` — The Toloker no longer meets one or more filters.
    * `RESTRICTION` — The Toloker's access to tasks is blocked by a quality control rule.

`PoolAccessRevokedReason` is used with collectors:
- [UsersAssessment](toloka.client.collectors.UsersAssessment.md)

