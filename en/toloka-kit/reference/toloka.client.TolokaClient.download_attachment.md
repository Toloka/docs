# download_attachment
`toloka.client.TolokaClient.download_attachment` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L960)

```python
download_attachment(
    self,
    attachment_id: str,
    out: BinaryIO
)
```

Downloads an attachment.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`attachment_id`|**str**|<p>The ID of the attachment.</p>
`out`|**BinaryIO**|<p>A file object used to save the downloaded file.</p>

**Examples:**

How to download an attachment.

```python
with open('my_new_file.txt', 'wb') as out_f:
    toloka_client.download_attachment(attachment_id='0983459b-e26f-42f3-a5fd-6e3feee913e7', out=out_f)
```
