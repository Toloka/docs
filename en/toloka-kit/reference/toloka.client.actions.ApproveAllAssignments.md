# ApproveAllAssignments
`toloka.client.actions.ApproveAllAssignments` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/actions.py#L217)

```python
ApproveAllAssignments(self)
```

Accepts all Toloker's assignments in the pool.


**Examples:**

Accept all assignments if a Toloker gives correct responses for control tasks. Note, that the pool must be configured with non-automatic response acceptance.

```python
new_pool = toloka.client.pool.Pool()
new_pool.quality_control.add_action(
    collector=toloka.client.collectors.GoldenSet(history_size=5),
    conditions=[toloka.client.conditions.GoldenSetCorrectAnswersRate > 90],
    action=toloka.client.actions.ApproveAllAssignments()
)
```
