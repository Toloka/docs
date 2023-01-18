# add_message_thread_to_folders
`toloka.async_client.client.AsyncTolokaClient.add_message_thread_to_folders` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/async_client/client.py#L0)

```python
async add_message_thread_to_folders(
    self,
    message_thread_id: str,
    folders: Union[List[Folder], MessageThreadFolders]
)
```

Adds a message chain to one or more folders ("unread", "important" etc.)

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`message_thread_id`|**str**|<p>ID of message chain.</p>
`folders`|**Union\[List\[[Folder](toloka.client.message_thread.Folder.md)\], [MessageThreadFolders](toloka.client.message_thread.MessageThreadFolders.md)\]**|<p>List of folders, where to move chain.</p>

* **Returns:**

  Full object by ID with updated folders.

* **Return type:**

  [MessageThread](toloka.client.message_thread.MessageThread.md)

**Examples:**


```python
toloka_client.add_message_thread_to_folders(message_thread_id='1', folders=['IMPORTANT'])
```