# Details
`toloka.client.attachment.Attachment.Details` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/attachment.py#L33)

```python
Details(
    self,
    *,
    user_id: Optional[str] = None,
    assignment_id: Optional[str] = None,
    pool_id: Optional[str] = None
)
```

Information about the pool, task, and the Toloker from which the file was received.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_id`|**Optional\[str\]**|<p>ID of the Toloker from whom the file was received.</p>
`assignment_id`|**Optional\[str\]**|<p>ID for issuing a set of tasks to the Toloker.</p>
`pool_id`|**Optional\[str\]**|<p>Pool ID.</p>
