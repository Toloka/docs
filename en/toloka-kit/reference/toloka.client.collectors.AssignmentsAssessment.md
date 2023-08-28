# AssignmentsAssessment
`toloka.client.collectors.AssignmentsAssessment` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/collectors.py#L165)

```python
AssignmentsAssessment(self, *, uuid: Optional[UUID] = None)
```

Counts accepted and rejected assignments for every task suite.


Collector use cases.
- To reassign rejected task suite to other Tolokers increase
the overlap of the task suite. It is essential if the default overlap value is 1.
- You accept an assignment and don't need to collect more responses for that task suite. To save money stop assigning the task suite.

The collector can be used with conditions:
* [PendingAssignmentsCount](toloka.client.conditions.PendingAssignmentsCount.md) — The number of pending assignments that must be checked.
* [AcceptedAssignmentsCount](toloka.client.conditions.AcceptedAssignmentsCount.md) — The number of accepted assignments for a task suite.
* [RejectedAssignmentsCount](toloka.client.conditions.RejectedAssignmentsCount.md) — The number of rejected assignments for a task suite.
* [AssessmentEvent](toloka.client.conditions.AssessmentEvent.md) — An assignment status change event.

The collector can be used with actions:
* [ChangeOverlap](toloka.client.actions.ChangeOverlap.md) changes the overlap of a task suite.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`uuid`|**Optional\[UUID\]**|<p>The ID of a collector. Note that when you clone a pool, both pools start using the same collector, because it is not cloned. Usually, it is not an intended behavior. For example, in this case one collector gathers history size from both pools.</p>

**Examples:**

The example shows how to reassign rejected task suites to other Tolokers.

```python
new_pool = toloka.client.pool.Pool()
new_pool.quality_control.add_action(
    collector=toloka.client.collectors.AssignmentsAssessment(),
    conditions=[toloka.client.conditions.AssessmentEvent == toloka.client.conditions.AssessmentEvent.REJECT],
    action=toloka.client.actions.ChangeOverlap(delta=1, open_pool=True),
)
```
