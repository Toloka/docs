# AppItem
`toloka.client.app.AppItem` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/app/__init__.py#L125)

```python
AppItem(
    self,
    *,
    batch_id: Optional[str] = None,
    input_data: Optional[Dict[str, Any]] = None,
    id: Optional[str] = None,
    app_project_id: Optional[str] = None,
    status: Union[Status, str, None] = None,
    output_data: Optional[Dict[str, Any]] = None,
    errors: Optional[List[_AppError]] = None,
    created_at: Optional[datetime] = None,
    started_at: Optional[datetime] = None,
    finished_at: Optional[datetime] = None
)
```

A task item.


Items are uploaded to Toloka and are grouped in batches. After uploading the status of items is set to `NEW`. Items with that status can be edited. Then entire batches are sent for labeling.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the item.</p>
`app_project_id`|**Optional\[str\]**|<p>The ID of the project that contains the item.</p>
`batch_id`|**Optional\[str\]**|<p>The ID of the batch that contains the item.</p>
`input_data`|**Optional\[Dict\[str, Any\]\]**|<p>Input data. It must follow the solution schema described in `App.input_spec`.</p>
`status`|**Optional\[[Status](toloka.client.app.AppItem.Status.md)\]**|<p>The item status:</p> <ul> <li>`NEW` — The item is uploaded to Toloka and ready for processing.</li> <li>`PROCESSING` — The item is being processed by Tolokers.</li> <li>`COMPLETED` — Item annotation is completed.</li> <li>`ERROR` — An error occurred during processing.</li> <li>`CANCELLED` — Item processing cancelled.</li> <li>`ARCHIVE` — The item is archived.</li> <li>`NO_MONEY` — There are not enough money for processing.</li> </ul>
`output_data`|**Optional\[Dict\[str, Any\]\]**|<p>Annotated data.</p>
`errors`|**Optional\[List\[[_AppError](toloka.client.app._AppError.md)\]\]**|<p>Errors occurred during annotation.</p>
`created_at`|**Optional\[datetime\]**|<p>The date and time when the item was created.</p>
`started_at`|**Optional\[datetime\]**|<p>The date and time when the item processing started.</p>
`finished_at`|**Optional\[datetime\]**|<p>The date and time when the item processing was completed.</p>
