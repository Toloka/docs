# AssignmentsAcceptedCount
`toloka.client.conditions.AssignmentsAcceptedCount` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/conditions.py#L164)

```python
AssignmentsAcceptedCount(
    self,
    operator: CompareOperator,
    value: Optional[int] = None
)
```

The number of assignments accepted from a Toloker.


`AssignmentsAcceptedCount` is used with collectors:
- [AnswerCount](toloka.client.collectors.AnswerCount.md)

See also:
- [AcceptedAssignmentsCount](toloka.client.conditions.AcceptedAssignmentsCount.md) — The number of accepted assignments of a task suite.


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.quality_control.add_action(
    collector=toloka.client.collectors.AnswerCount(),
    conditions=[toloka.client.conditions.AssignmentsAcceptedCount > 0],
    action=toloka.client.actions.SetSkill(skill_id='11294', skill_value=1),
)
```
