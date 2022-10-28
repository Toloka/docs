# RejectAllAssignments
`toloka.client.actions.RejectAllAssignments` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.0.2/src/client/actions.py#L183)

```python
RejectAllAssignments(self, *, public_comment: Optional[str] = None)
```

Rejects all Toloker's assignments in the pool. This action is available for pools with non-automatic acceptance.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`public_comment`|**Optional\[str\]**|<p>The reason of the rejection. It is visible both to the requester and to the Toloker.</p>

**Examples:**

Reject all assignments if a Toloker sends responses too fast. Note, that the pool must be configured with non-automatic response acceptance.

```python
new_pool = toloka.pool.Pool(....)
new_pool.quality_control.add_action(
    collector=toloka.collectors.AssignmentSubmitTime(history_size=5, fast_submit_threshold_seconds=20),
    conditions=[toloka.conditions.FastSubmittedCount > 3],
    action=toloka.actions.RejectAllAssignments(public_comment='Too fast responses.')
)
```
