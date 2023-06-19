# ApproveAllAssignments
`toloka.client.actions.ApproveAllAssignments` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/actions.py#L205)

```python
ApproveAllAssignments(self)
```

Accepts all Toloker's assignments in the pool.


**Examples:**

Accept all assignments if a Toloker gives correct responses for control tasks. Note, that the pool must be configured with non-automatic response acceptance.

```python
new_pool = toloka.pool.Pool(....)
new_pool.quality_control.add_action(
    collector=toloka.collectors.GoldenSet(history_size=5),
    conditions=[toloka.conditions.GoldenSetCorrectAnswersRate > 90],
    action=toloka.actions.ApproveAllAssignments()
)
```
