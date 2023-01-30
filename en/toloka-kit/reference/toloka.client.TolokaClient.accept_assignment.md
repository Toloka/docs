# accept_assignment
`toloka.client.TolokaClient.accept_assignment` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/__init__.py#L635)

```python
accept_assignment(
    self,
    assignment_id: str,
    public_comment: str
)
```

Accepts an assignment.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`assignment_id`|**str**|<p>The ID of the assignment.</p>
`public_comment`|**str**|<p>A comment visible to Tolokers.</p>

* **Returns:**

  The assignment object with the updated status field.

* **Return type:**

  [Assignment](toloka.client.assignment.Assignment.md)

**Examples:**

Accepting an assignment.

```python
toloka_client.accept_assignment(assignment_id, 'Well done!')
```
