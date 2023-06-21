# find_message_threads
`toloka.async_client.client.AsyncTolokaClient.find_message_threads` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/__init__.py#L0)

Finds message threads that match certain criteria.


The number of returned message threads is limited. To find remaining threads call `find_message_threads` with updated search criteria.

To iterate over all matching threads you may use the [get_message_threads](toloka.client.TolokaClient.get_message_threads.md) method.

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
`sort`|**Union\[List\[str\], [MessageThreadSortItems](toloka.client.search_requests.MessageThreadSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned message threads limit. The default limit is 50. The maximum allowed limit is 300.</p>

* **Returns:**

  Found message threads and a flag showing whether there are more matching threads.

* **Return type:**

  [MessageThreadSearchResult](toloka.client.search_results.MessageThreadSearchResult.md)

**Examples:**

Finding all message threads in the `INBOX` folder.

```python
toloka_client.find_message_threads(folder='INBOX')
```
