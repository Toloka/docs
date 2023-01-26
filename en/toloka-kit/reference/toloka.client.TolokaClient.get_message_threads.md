# get_message_threads
`toloka.client.TolokaClient.get_message_threads` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/__init__.py#L963)

Finds all message threads that match certain criteria.


`get_message_threads` returns a generator. You can iterate over all found message threads using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort message threads use the [find_message_threads](toloka.client.TolokaClient.find_message_threads.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`folder`|**Union\[str, [Folder](toloka.client.message_thread.Folder.md), List\[Union\[str, [Folder](toloka.client.message_thread.Folder.md)\]\], None\]**|<p>A folder where to search threads or a list of folders. Refer to the [Folder](toloka.client.message_thread.Folder.md) page for more information on the available `folder` values.</p>
`folder_ne`|**Union\[str, [Folder](toloka.client.message_thread.Folder.md), List\[Union\[str, [Folder](toloka.client.message_thread.Folder.md)\]\], None\]**|<p>A folder to skip or a list of folders. Supported values are the same as for `folder`.</p>
`id_lt`|**Optional\[str\]**|<p>Threads with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Threads with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Threads with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Threads with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Threads created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Threads created before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Threads created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Threads created after or on the specified date.</p>
`batch_size`|**Optional\[int\]**|<p>Returned message threads limit for each request. The default batch_size is 50. The maximum allowed batch_size is 300.</p>

* **Yields:**

  The next matching message thread.

* **Yield type:**

  Generator\[[MessageThread](toloka.client.message_thread.MessageThread.md), None, None\]

**Examples:**

How to get all unread incoming messages.

```python
message_threads = toloka_client.get_message_threads(folder=['INBOX', 'UNREAD'])
```
