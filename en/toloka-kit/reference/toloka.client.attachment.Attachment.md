# Attachment
`toloka.client.attachment.Attachment` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/attachment.py#L14)

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

An attachment.


Files attached to tasks by Tolokers are uploaded to Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The file ID.</p>
`name`|**Optional\[str\]**|<p>The file name.</p>
`details`|**Optional\[[Details](toloka.client.attachment.Attachment.Details.md)\]**|<p>Attachment details: a pool, task, and Toloker who uploaded the file.</p>
`created`|**Optional\[datetime\]**|<p>The date and time when the file was uploaded.</p>
`media_type`|**Optional\[str\]**|<p>The file [MIME](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types) data type.</p>
`owner`|**Optional\[[Owner](toloka.client.owner.Owner.md)\]**|<p>The owner of the attachment.</p>
