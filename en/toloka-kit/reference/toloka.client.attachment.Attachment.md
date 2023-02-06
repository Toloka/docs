# Attachment
`toloka.client.attachment.Attachment` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/attachment.py#L14)

```python
Attachment(
    self,
    *,
    id: Optional[str] = None,
    name: Optional[str] = None,
    details: Optional[Details] = None,
    created: Optional[datetime] = None,
    media_type: Optional[str] = None,
    owner: Optional[Owner] = None
)
```

Attachment


Files uploaded by Tolokers are saved in Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>File ID.</p>
`name`|**Optional\[str\]**|<p>File name.</p>
`details`|**Optional\[[Details](toloka.client.attachment.Attachment.Details.md)\]**|<p>Information about the pool, the task, and the Toloker who uploaded the file.</p>
`created`|**Optional\[datetime\]**|<p>Date the file was uploaded to Toloka.</p>
`media_type`|**Optional\[str\]**|<p>MIME data type.</p>
`owner`|**Optional\[[Owner](toloka.client.owner.Owner.md)\]**|<p>Owner</p>
