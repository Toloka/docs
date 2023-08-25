# get_assignment
`toloka.async_client.client.AsyncTolokaClient.get_assignment` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/async_client/client.py#L0)

```python
async get_assignment(self, assignment_id: str)
```

Gets an assignment from Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`assignment_id`|**str**|<p>The ID of the assignment.</p>

* **Returns:**

  The assignment.

* **Return type:**

  [Assignment](toloka.client.assignment.Assignment.md)

**Examples:**


```python
assignment = toloka_client.get_assignment(
    assignment_id='00001092da--61ef030400c684132d0da0de'
)
```
