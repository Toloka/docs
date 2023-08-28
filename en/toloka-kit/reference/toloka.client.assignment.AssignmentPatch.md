# AssignmentPatch
`toloka.client.assignment.AssignmentPatch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/assignment.py#L117)

```python
AssignmentPatch(
    self,
    *,
    public_comment: Optional[str] = None,
    status: Optional[Assignment.Status] = None
)
```

The new status of an assignment.


It is used in the [patch_assignment](toloka.client.TolokaClient.patch_assignment.md) method to accept or reject an assignment and to leave a comment.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`public_comment`|**Optional\[str\]**|<p>The public comment.</p>
`status`|**Optional\[[Assignment.Status](toloka.client.assignment.Assignment.Status.md)\]**|<p>The new status of an assignment:</p> <ul> <li>`ACCEPTED` — Accepted by the requester.</li> <li>`REJECTED` — Rejected by the requester.</li> </ul>
