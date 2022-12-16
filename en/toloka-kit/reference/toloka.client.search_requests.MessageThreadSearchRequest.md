# MessageThreadSearchRequest
`toloka.client.search_requests.MessageThreadSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/search_requests.py#L796)

```python
MessageThreadSearchRequest(
    self,
    folder: Union[str, Folder, List[Union[str, Folder]], None] = None,
    folder_ne: Union[str, Folder, List[Union[str, Folder]], None] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    created_lt: Optional[datetime] = None,
    created_lte: Optional[datetime] = None,
    created_gt: Optional[datetime] = None,
    created_gte: Optional[datetime] = None
)
```

Parameters for searching message threads.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`folder`|**Optional\[List\[[Folder](toloka.client.message_thread.Folder.md)\]\]**|<p>A folder where to search threads or a list of folders. Refer to the [Folder](toloka.client.message_thread.Folder.md) page for more information on the available `folder` values.</p>
`folder_ne`|**Optional\[List\[[Folder](toloka.client.message_thread.Folder.md)\]\]**|<p>A folder to skip or a list of folders. Supported values are the same as for `folder`.</p>
`id_lt`|**Optional\[str\]**|<p>Threads with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Threads with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Threads with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Threads with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Threads created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Threads created before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Threads created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Threads created after or on the specified date.</p>
