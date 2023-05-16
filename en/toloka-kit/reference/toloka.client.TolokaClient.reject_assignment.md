# reject_assignment
`toloka.client.TolokaClient.reject_assignment` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/__init__.py#L759)

```python
reject_assignment(
    self,
    assignment_id: str,
    public_comment: str
)
```

Rejects an assignment.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`assignment_id`|**str**|<p>The ID of the assignment.</p>
`public_comment`|**str**|<p>A public comment visible to Tolokers.</p>

* **Returns:**

  Assignment object with updated fields.

* **Return type:**

  [Assignment](toloka.client.assignment.Assignment.md)

**Examples:**


```python
toloka_client.reject_assignment(assignment_id='1', 'Some questions skipped')
```
