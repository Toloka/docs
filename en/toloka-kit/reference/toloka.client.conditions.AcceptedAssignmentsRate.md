# AcceptedAssignmentsRate
`toloka.client.conditions.AcceptedAssignmentsRate` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/conditions.py#L104)

```python
AcceptedAssignmentsRate(
    self,
    operator: CompareOperator,
    value: Optional[float] = None
)
```

The percentage of accepted assignments out of all checked assignments from a Toloker.


`AcceptedAssignmentsRate` is used with collectors:
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
