# add_message_thread_to_folders
`toloka.async_client.client.AsyncTolokaClient.add_message_thread_to_folders` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/async_client/client.py#L0)

```python
async add_message_thread_to_folders(
    self,
    message_thread_id: str,
    folders: Union[List[Folder], MessageThreadFolders]
)
```

Adds a message thread to folders.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`message_thread_id`|**str**|<p>The ID of the message thread.</p>
`folders`|**Union\[List\[[Folder](toloka.client.message_thread.Folder.md)\], [MessageThreadFolders](toloka.client.message_thread.MessageThreadFolders.md)\]**|<p>A list of folders where to add the thread.</p>

* **Returns:**

  The updated message thread.

* **Return type:**

  [MessageThread](toloka.client.message_thread.MessageThread.md)

**Examples:**


```python
toloka_client.add_message_thread_to_folders(message_thread_id='1', folders=['IMPORTANT'])
```
