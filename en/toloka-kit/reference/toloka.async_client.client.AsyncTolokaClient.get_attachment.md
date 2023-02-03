# get_attachment
`toloka.async_client.client.AsyncTolokaClient.get_attachment` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/async_client/client.py#L0)

```python
async get_attachment(self, attachment_id: str)
```

Gets attachment metadata without downloading it


To download attachments as a file use "TolokaClient.download_attachment" method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`attachment_id`|**str**|<p>ID of attachment.</p>

* **Returns:**

  The attachment metadata read as a result.

* **Return type:**

  [Attachment](toloka.client.attachment.Attachment.md)

**Examples:**

Specify an `attachment_id` to get the information about any attachment object.

```python
toloka_client.get_attachment(attachment_id='1')
```
