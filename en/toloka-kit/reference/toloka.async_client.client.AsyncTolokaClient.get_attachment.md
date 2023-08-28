# get_attachment
`toloka.async_client.client.AsyncTolokaClient.get_attachment` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/async_client/client.py#L0)

```python
async get_attachment(self, attachment_id: str)
```

Gets attachment metadata without downloading it.


To download an attachment use the [download_attachment](toloka.client.TolokaClient.download_attachment.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`attachment_id`|**str**|<p>The ID of the attachment.</p>

* **Returns:**

  The attachment metadata.

* **Return type:**

  [Attachment](toloka.client.attachment.Attachment.md)

**Examples:**


```python
attachment = toloka_client.get_attachment(attachment_id='0983459b-e26f-42f3-a5fd-6e3feee913e7')
```
