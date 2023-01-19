# Captcha
`toloka.client.collectors.Captcha` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/collectors.py#L237)

```python
Captcha(
    self,
    *,
    uuid: Optional[UUID] = None,
    history_size: Optional[int] = None
)
```

Collects captcha statistics for every Toloker.


Captcha provides an advanced protection against robots. It is used with conditions:
* [StoredResultsCount](toloka.client.conditions.StoredResultsCount.md) — How many times the Toloker entered a captcha.
* [SuccessRate](toloka.client.conditions.SuccessRate.md) — The percentage of solved captchas.
* [FailRate](toloka.client.conditions.FailRate.md) — The percentage of unsolved captchas.

The collector can be used with actions:
* [RestrictionV2](toloka.client.actions.RestrictionV2.md) blocks access to projects or pools.
* [ApproveAllAssignments](toloka.client.actions.ApproveAllAssignments.md) accepts all Toloker's assignments.
* [RejectAllAssignments](toloka.client.actions.RejectAllAssignments.md) rejects all Toloker's assignments.
* [SetSkill](toloka.client.actions.SetSkill.md) sets Toloker's skill value.
* [SetSkillFromOutputField](toloka.client.actions.SetSkillFromOutputField.md) sets Toloker's skill value using an output field.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`uuid`|**Optional\[UUID\]**|<p>The ID of a collector. Note that when you clone a pool, both pools start using the same collector, because it is not cloned. Usually, it is not an intended behavior. For example, in this case one collector gathers history size from both pools.</p>
`history_size`|**Optional\[int\]**|<p>The maximum number of recent captchas used to calculate the statistics. If `history_size` is omitted, all captchas are counted.</p>

**Examples:**

The example shows how to block Toloker's access to the project for 15 days if they solve 60% of captchas or less.
The rule is applied after entering at least 3 captchas.

```python
new_pool = toloka.pool.Pool(....)
new_pool.set_captcha_frequency('MEDIUM')
new_pool.quality_control.add_action(
    collector=toloka.collectors.Captcha(history_size=5),
    conditions=[
        toloka.conditions.SuccessRate < 60,
        toloka.conditions.StoredResultsCount >= 3,
    ],
    action=toloka.actions.RestrictionV2(
        scope=toloka.user_restriction.UserRestriction.PROJECT,
        duration=15,
        duration_unit='DAYS',
        private_comment='Toloker often makes mistakes in captcha',
    )
)
```
