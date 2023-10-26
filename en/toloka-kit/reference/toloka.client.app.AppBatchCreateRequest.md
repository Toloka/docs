# AppBatchCreateRequest
`toloka.client.app.AppBatchCreateRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/app/__init__.py#L397)

```python
AppBatchCreateRequest(
    self,
    *,
    name: Optional[str] = None,
    items: Optional[List[Dict[str, Any]]] = None,
    priority_order: Optional[AppBatch.PriorityOrder] = None,
    force_new_original: Optional[bool] = None,
    ignore_errors: Optional[bool] = None
)
```

Parameters of a request for creating multiple App task items in a batch.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`name`|**Optional\[str\]**|<p>The batch name.</p>
`items`|**Optional\[List\[Dict\[str, Any\]\]\]**|<p>A list with task items. The items must follow the solution schema described in the `App.input_spec`.</p>
`priority_order`|**Optional\[[AppBatch.PriorityOrder](toloka.client.app.AppBatch.PriorityOrder.md)\]**|<p>The batch priority. See [PriorityOrder](toloka.client.app.AppBatch.PriorityOrder.md) for details. Default is `FIVE`.</p>
`force_new_original`|**Optional\[bool\]**|<p>Whether to enable or disable the deduplication for all the items in the request. When set to true, all the items will be re-labeled regardless of whether pre-labeled duplicates exist. Default is `False`.</p>
`ignore_errors`|**Optional\[bool\]**|<p>Whether the data with incorrect items can be uploaded. Default is `False`.</p>
