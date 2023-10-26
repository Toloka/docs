# AppItemsCreateRequest
`toloka.client.app.AppItemsCreateRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/app/__init__.py#L258)

```python
AppItemsCreateRequest(
    self,
    *,
    batch_id: Optional[str] = None,
    items: List[Dict[str, Any]],
    force_new_original: Optional[bool] = None,
    ignore_errors: Optional[bool] = None
)
```

Parameters of a request for creating multiple items.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`batch_id`|**Optional\[str\]**|<p>The ID of the batch to place items to.</p>
`items`|**List\[Dict\[str, Any\]\]**|<p>A list with items. The items must follow the solution schema described in `App.input_spec`.</p>
`force_new_original`|**Optional\[bool\]**|<p>Whether to enable or disable the deduplication for all the items in the request. When set to true, all the items will be re-labeled regardless of whether pre-labeled duplicates exist. Default is `False`.</p>
`ignore_errors`|**Optional\[bool\]**|<p>Whether the data with incorrect items can be uploaded. Default is `False`.</p> <ul> <li>`True` — If incorrect task items are present, they will be skipped and the response will contain the information about errors.</li> <li>`False` — If incorrect task items are present, the data will not be uploaded and the response will contain the information about the errors. You can only use this parameter if batch_id is specified in the request.</li> </ul>
