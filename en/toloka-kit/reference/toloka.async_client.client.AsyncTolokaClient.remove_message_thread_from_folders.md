# remove_message_thread_from_folders
`toloka.async_client.client.AsyncTolokaClient.remove_message_thread_from_folders` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/async_client/client.py#L0)

```python
async remove_message_thread_from_folders(
    self,
    message_thread_id: str,
    folders: Union[List[Folder], MessageThreadFolders]
)
```

Removes a message thread from folders.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`message_thread_id`|**str**|<p>The ID of the message thread.</p>
`folders`|**Union\[List\[[Folder](toloka.client.message_thread.Folder.md)\], [MessageThreadFolders](toloka.client.message_thread.MessageThreadFolders.md)\]**|<p>A list of folders.</p>

* **Returns:**

  The updated message thread.

* **Return type:**

  [MessageThread](toloka.client.message_thread.MessageThread.md)

**Examples:**


```python
toloka_client.remove_message_thread_from_folders(message_thread_id='1', folders=['IMPORTANT'])
```
