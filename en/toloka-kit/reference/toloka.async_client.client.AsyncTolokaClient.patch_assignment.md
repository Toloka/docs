# patch_assignment
`toloka.async_client.client.AsyncTolokaClient.patch_assignment` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L0)

Changes an assignment status and associated public comment.


See also [reject_assignment](toloka.client.TolokaClient.reject_assignment.md) and [accept_assignment](toloka.client.TolokaClient.accept_assignment.md).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`assignment_id`|**str**|<p>The ID of the assignment.</p>
`public_comment`|**Optional\[str\]**|<p>The public comment.</p>
`status`|**Optional\[[Assignment.Status](toloka.client.assignment.Assignment.Status.md)\]**|<p>The new status of an assignment:</p> <ul> <li>`ACCEPTED` — Accepted by the requester.</li> <li>`REJECTED` — Rejected by the requester.</li> </ul>

* **Returns:**

  Assignment object with updated fields.

* **Return type:**

  [Assignment](toloka.client.assignment.Assignment.md)

**Examples:**


```python
toloka_client.patch_assignment(assignment_id='00001092da--61ef030400c684132d0da0de',
    public_comment='Accepted. Good job.',
    status='ACCEPTED'
)
```
