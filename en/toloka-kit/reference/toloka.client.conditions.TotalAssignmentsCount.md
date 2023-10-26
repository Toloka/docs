# TotalAssignmentsCount
`toloka.client.conditions.TotalAssignmentsCount` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/conditions.py#L589)

```python
TotalAssignmentsCount(
    self,
    operator: CompareOperator,
    value: Optional[int] = None
)
```

The number of checked assignments out of all assignments submitted by a Toloker.


`TotalAssignmentsCount` is used with collectors:
- [AcceptanceRate](toloka.client.collectors.AcceptanceRate.md)


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.quality_control.add_action(
    collector=toloka.client.collectors.AcceptanceRate(),
    conditions=[
        toloka.client.conditions.TotalAssignmentsCount > 10,
        toloka.client.conditions.AcceptedAssignmentsRate > 90,
    ],
    action=toloka.client.actions.SetSkill(skill_id='11294', skill_value=1)
)
```
