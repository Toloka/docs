# SkippedInRowCount
`toloka.client.conditions.SkippedInRowCount` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/conditions.py#L491)

```python
SkippedInRowCount(
    self,
    operator: CompareOperator,
    value: Optional[int] = None
)
```

The number of tasks skipped in a row by a Toloker.


`SkippedInRowCount` is used with collectors:
- [SkippedInRowAssignments](toloka.client.collectors.SkippedInRowAssignments.md)


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.quality_control.add_action(
    collector=toloka.client.collectors.SkippedInRowAssignments(),
    conditions=[toloka.client.conditions.SkippedInRowCount > 3],
    action=toloka.client.actions.RestrictionV2(
        scope='PROJECT', duration=15, duration_unit='DAYS'
    )
)
```
